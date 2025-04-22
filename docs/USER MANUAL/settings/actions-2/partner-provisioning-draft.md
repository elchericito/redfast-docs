---
title: Partner Provisioning
deprecated: false
hidden: true
metadata:
  robots: index
---
# Introduction

The Provisioning API allows for the creation and modification of a Redfast tenant via server-side integration with partners. It also allows you to provision users just in time (JIT) and redirect them into pulse.redfast.com with a logged  in session. Please work with your partnership manager if you require access to this API.

## Endpoint Info

<br />

**Base URL**: `https://<subdomain>.redfast.com`

<br />

# Get Tenant

<br />

This API should be invoked to retrieve an existing tenant.

<br />

## Endpoint

<br />

**GET /v1/tenants/\<external\_tenant\_id>**

<br />

## Headers

<br />

* **Content-Type**: `application/json`
* **rf-secret**: Shared secret provided by Redfast (separate secrets for Test and Production)
  <br />

## Query Params

<br />

The request should include the following query params:

* **partner\_code**: Partner Code assigned by Redfast
  <br />

## Response

<br />

```json json
{
  "success": true,
  "external_tenant_id": "<external_tenant_id>",
  "app_id": "<app_id>",
  "tag_url": "https://<app_id>.redfastlabs.com/assets/redfast.js",
  "user_first_name": "John",
  "user_last_name": "Smith",
  "user_email": "jsmith@myemail.com",
  "app_name": "My App",
  "company_name": "My Company",
  "app_domain": "myco.com",
  "test_mode": false,
  "jwt_public_key_updated_at": "2025-02-18T17:02:26.000Z"
}
```

<br />

# Create Tenant

<br />

This API should be invoked to create a new tenant on the Redfast platform.

<br />

## Endpoint

<br />

**POST /v1/tenants**

<br />

## Headers

<br />

* **Content-Type**: `application/json`
* **rf-secret**: Shared secret provided by Redfast (separate secrets for Test and Production)
  <br />

## Body

<br />

The request body should be a JSON including the following properties (all required):

* **company\_name**: Company name
* **external\_tenant\_id**: Unique Partner Tenant ID
* **app\_name**: Name of the app/site utilizing Redfast platform
* **app\_domain**: Top level domain
* **user\_email**: Email address of initial Admin user
* **user\_first\_name**: First name of Admin user
* **user\_last\_name**: Last name of Admin user
* **partner\_code**: Partner Code assigned by Redfast
* **api\_key**: API key utilized for integration with partner for the tenant
* **jwt\_public\_key**: Public key utilized for provisioning and authenticating users. Must be an RSA public key in PEM format, between 2048–4096 bits. Use newline characters for each line.
  <br />

## Response

<br />

```json
{
  "success": true,
  "status": "provisioning_started",
  "external_tenant_id": "<external_tenant_id>",
  "app_id": "<app_id>",
  "tag_url": "https://<app_id>.redfastlabs.com/assets/redfast.js",
  "test_mode": false,
  "jwt_public_key": "-----BEGIN PUBLIC KEY-----\n...",
  "jwt_public_key_updated_at": "2025-02-18T17:02:26.000Z"
}
```

<br />

# Update Tenant

<br />

This API should be invoked to update an existing tenant on the Redfast platform.

<br />

## Endpoint

<br />

**PATCH /v1/tenants**

<br />

## Headers

<br />

* **Content-Type**: `application/json`
* **rf-secret**: Shared secret provided by Redfast (separate secrets for Test and Production)
  <br />

## Body

<br />

The request body should be a JSON including the following properties:

* **external\_tenant\_id**: Unique Partner Tenant ID
* **partner\_code**: Partner Code assigned by Redfast
* **app\_domain**: (optional) Top level domain
* **api\_key**: (optional) API key utilized for integration with partner for the tenant
* **jwt\_public\_key**: (optional) Public key utilized for provisioning and authenticating users. Must be an RSA public key in PEM format, between 2048–4096 bits. Only displayed if updated. Use newline characters for each line.
  <br />

## Response

<br />

```json
{
  "success": true,
  "status": "updated",
  "external_tenant_id": "<external_tenant_id>",
  "app_id": "<app_id>",
  "tag_url": "https://<app_id>.redfastlabs.com/assets/redfast.js",
  "test_mode": false,
  "jwt_public_key": "-----BEGIN PUBLIC KEY-----\n...",
  "jwt_public_key_updated_at": "2025-02-18T17:02:26.000Z"
}
```

<br />

# User provisioning and session token

This API should be invoked to create a user session. If a user does not already exist, they will be provisioned first and then a session will be created upon JWT validation.

## Endpoint

**POST /v1/jwt\_session**

## Body

The request body should be a JSON including the following properties:

* **jwt\_token**: A jwt token that will be used to verify and create the user session. Below is the payload

<br />

```json
{
  "sub": "<partner_user_id>,                          // Unique partner user ID
  "external_tenant_id": "<external_tenant_id>",       // Tenant they belong to
  "app_id": "<app_id>",                               // App they belong to
  "role": "admin",                                    // "admin" or "member", defaults to "member"
  "exp": 1712800000,                                  // Expiry 
  "iat": 1712796400,                                  // Issued at
  "iss": "<partner_code>"                             // Partner Code
  "email": "<email>",
  "first_name": "<first_name>",
  "last_name": "<last_name>"
}
```

<br />

## Response

```json
{
  "success": true,
  "external_tenant_id": "<external_tenant_id>",
  "session_token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...",
  "session_token_expires_at": "2025-02-18T17:02:26.000Z"
}
```

<br />

# User redirect

This API should be invoked to redirect a user to pulse.redfast.com.

## Endpoint

**GET /v1/session/redirect**

## Query Params

The request should include the following query params:

* **redirect\_url**: (optional) Pulse URL to redirect the user to. Only requires the relative path, the domain pulse.redfast.com is optional. If not included will redirect the user to pulse.redfast.com.
* **session\_token**: A Redfast session token that will be used to redirect the user to a logged in page.

<br />

## Response

Redirects the user to pulse.redfast.com. When the user does not have a valid session it redirects the user to the login page.

# Testing

<br />

Authentication utilizes a shared secret (both Test and Production secrets will be provided). When utilizing the Test secret, a valid API response is returned but a new tenant will not be provisioned.

<br />

# Error Responses

<br />

Redfast uses conventional HTTP response codes indicating success or failure of an API request. Codes in the 2xx range indicate success while codes in the 4xx or 5xx ranges indicate an error.

<br />

* 200 OK - Normal response
* 401 Unauthorized - Shared secret is incorrect

<br />

```json
{
  "success": false,
  "status": "invalid_secret"
}
```

<br />

* 404 Not Found - Requested resource was not found

<br />

```json
{
  "success": false,
  "status": "not_found",
  "message": "resource not found"
}
```

<br />

<br />

* 409 Conflict - Tenant has already been provisioned

<br />

```json
{
  "success": false,
  "status": "already_provisioned",
  "external_tenant_id": "<external_tenant_id>"
}
```

<br />

* 422 Unprocessable Entity - Invalid or missing information

<br />

```json
{
  "success": false,
  "status": "missing_or_invalid_info",
  "message": "partner_code missing"
  "external_tenant_id": "<external_tenant_id>"
}
```

<br />

* 5xx - Something went wrong with the Redfast endpoint (rare)