---
title: Google
excerpt: ''
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
### Firebase Cloud Messaging (FCM)

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
