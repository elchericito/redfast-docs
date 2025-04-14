---
title: Partner APIs
deprecated: false
hidden: true
metadata:
  robots: index
---
# Introduction

The Partner APIs allows for the creation and modification of Redfast prompts via server-side integration with partners.

## Endpoint Info

**Base URL**: `https://<subdomain>.redfast.com`

<br />

# Get Prompts by Tag Name

<br />

This API should be invoked to retrieve a list of prompts based on tag name.

<br />

## Endpoint

**GET /v1/apps/\<app\_id>/paths?tag\_name=involuntary\_churn**

<br />

## Headers

* **Content-Type**: `application/json`
* **Authorization**: Bearer \<jwt\_token>

## Query Params

The request should include the following query params:

* **tag\_name**: (optional) Get prompts by tag\_name
  <br />

## Response

<br />

```json json
[{
  "id": "c6e948dd-06ec-4d10-acc9-a6b4ba2823ff",
  "name": "Sample Prompt",
  "description": "This is an example prompt",
  "start_date": "2025-02-18T00:00:00.000Z",
  "end_date": "2026-02-18T23:59:59.000Z",
  "is_enabled": false,
  "is_expired": false,
  "actions": {
    "rf_retention_title": "Movies without limits",
    "rf_retention_message": "Download New Episodes. Brand new full length episodes you can watch while offline. Free for 1 month.",
    "rf_retention_button1_text": "Accept",
    "rf_retention_button2_text": "Maybe Later",
    "rf_retention_button3_text": "No thanks",
    "rf_settings_bg_image": "https://assets.redfastlabs.com/videos/cover.jpg",
    "rf_settings_mobile_bg_image": "https://assets.redfastlabs.com/videos/mweb_video_bg.jpg",
    "rf_mobile_title": "Movies without limits",
    "rf_mobile_message": "Download New Episodes. Brand new full length episodes you can watch while offline. Free for 1 month.",
  }
}]
```

# Update Prompt

This API should be invoked to update an existing prompt. Omitted attributes will be ignored.

## Endpoint

**PUT /v1/apps/\<app\_id>/paths/\<path\_id>**

## Headers

* **Content-Type**: `application/json`
* **Authorization**: Bearer \<jwt\_token>

<br />

## Body

The request body should be a JSON including the following properties. All fields are optional except for actions:

* **id**: (required) Prompt id
* **name**: Prompt name
* **description**: Prompt description
* **start\_date**: Start date
* **end\_date**: Start date
* **is\_enabled**: Enable prompt
* **actions**: Prompt attributes. All attributes are strings.

## Response

```json json
{
  "id": "c6e948dd-06ec-4d10-acc9-a6b4ba2823ff",
  "name": "Sample Prompt",
  "description": "This is an example prompt",
  "start_date": "2025-02-18T00:00:00.000Z",
  "end_date": "2026-02-18T23:59:59.000Z",
  "is_enabled": false,
  "is_expired": false,
  "actions": {
    "rf_retention_title": "Movies without limits",
    "rf_retention_message": "Download New Episodes. Brand new full length episodes you can watch while offline. Free for 1 month.",
    "rf_retention_button1_text": "Accept",
    "rf_retention_button2_text": "Maybe Later",
    "rf_retention_button3_text": "No thanks",
    "rf_settings_bg_image": "https://assets.redfastlabs.com/videos/cover.jpg",
    "rf_settings_mobile_bg_image": "https://assets.redfastlabs.com/videos/mweb_video_bg.jpg",
    "rf_mobile_title": "Movies without limits",
    "rf_mobile_message": "Download New Episodes. Brand new full length episodes you can watch while offline. Free for 1 month.",
  }
}
```

<br />

# GenAI Generator

This API should be invoked to generate prompt titles and descriptions.

<br />

## Endpoint

**POST /v1/apps/\<app\_id>/ai/inference**

## Headers

* **Content-Type**: `application/json`
* **Authorization**: Bearer \<jwt\_token>

## Body

The request body should be a JSON including the following properties. All fields are optional except for type:

* **session\_id**: Prompt session ID to persist chat.
* **type**: title, description, accept\_button, cancel\_button.
* **custom\_content**: Additional context for the AI agent. If session\_id is set previously submitted content will be kept as part of the overall context.

## Response

```
{ result: "Your credit card has expired!" }
```

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

```
{
  "success": false,
  "status": "invalid_token"
}
```

<br />

* 404 Not Found - Requested resource was not found

<br />

```
{
  "success": false,
  "status": "not_found",
  "message": "resource not found"
}
```

<br />

<br />

* 422 Unprocessable Entity - Invalid or missing information

<br />

```
{
  "success": false,
  "status": "missing_or_invalid_info",
  "message": "id missing"
}
```

<br />

* 5xx - Something went wrong with the Redfast endpoint (rare)