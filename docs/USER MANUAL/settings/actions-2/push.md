---
title: Push
excerpt: Configuration information for push providers and syncing endpoint information
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
## Add Endpoint Addresses

Share a CSV with Redfast that includes the following columns: 

1. `Id`: the id of the device (aka endpoint) 
2. `ChannelType`: the push channel of this endpoint. Allowed values: `FCM`, `ADM`, `APNS`
3. `Address`: The device token 
4. `User.UserId`: the id of the user. This should be the same id that Redfast uses

This CSV can be used as a one time to do an initial load of endpoint information. To keep this information updated, you may: 

1. Upload an updated CSV periodically into your S3 bucket from Redfast OR 
2. Call the [Device Registration](ref:device-registration) API with the device token from your client application 

Registration API details: 

**POST** \<base\_url>/ingest/update\_push\_endpoint 

Body: 

```Text json
{
   "token": "4d5e6f1a2b3c4d5e6f7g8h9i0j1a2b3c",
   "channel_type": "GCM",
   "endpoint_id": "eqmj8wpxszeqy/b3vch04sn41yw"
}

```

Headers: 

Rf-App: \<app\_slug> 

User-Id: \<user\_id> 

Content-Type: application/json

### Amazon Device Messaging

Required information: `ADM Client ID`, `ADM Client Secret` 

Follow the instructions in this [document](https://developer.amazon.com/docs/adm/obtain-credentials.html) on Amazon's website

<br />

### Apple Push Notification Service (APNs)

Required information: `Apple Push Notifications Service Bundle ID`, `Apple Push Notifications Service Team ID`, `Apple Push Notifications Service Token Key`, `Apple Push Notifications Service Token Key ID`

Steps: 

1. Log in to [https://developer.apple.com/account](https://developer.apple.com/account) 
2. Retrieve the bundle id by navigating to Certificates, Ids & Profiles -> Identifiers. Click on the desired app and view the bundle id.
3. Retrieve the team id by navigating to Membership Details 
4. Create (or retrieve) the token key and token key id by navigating to Certificates, Ids & Profiles -> Keys. Create a new key with APNs authorized. View the key name and key id

<br />

### Google Firebase Cloud Messaging (FCM)

Required information: `FCM service json`

Steps:

1. Select your project from [https://console.firebase.google.com/](https://console.firebase.google.com/), and click the gear icon on the top of the sidebar.
2. Navigate to Project Settings -> Service Account tab 
3. Generate New Private Key
4. Download the JSON file 

Sample payload: 

```Text json
{
  "type": "service_account",
  "project_id": "PROJECT_ID",
  "private_key_id": "PRIVATE_KEY_ID",
  "private_key": "PRIVATE_KEY",
  "client_email": "FIREBASE_ADMIN_SDK_EMAIL",
  "client_id": "CLIENT_ID",
  "auth_uri": "https://accounts.google.com/o/oauth2/auth",
  "token_uri": "https://oauth2.googleapis.com/token",
  "auth_provider_x509_cert_url": "https://www.googleapis.com/oauth2/v1/certs",
  "client_x509_cert_url": "CLIENT_X509_CERT_URL"
}

```

### Upload file to Redfast

Uploaded the saved JSON file.
