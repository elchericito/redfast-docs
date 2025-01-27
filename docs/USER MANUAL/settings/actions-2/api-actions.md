---
title: APIs
excerpt: Private or public APIs you have access to
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
You may define custom API actions to leverage existing backend endpoints, specifying to send send dynamic user data and secure credentials as required.

### Add Credentials

Credentials data is stored in a secure, encrypted location that is only accessible to components tasked with perofrming the action. The most common credentials are API keys or client secrets.

Add a new credential and specify the name, and the value.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/faeced9-Screenshot_2024-05-02_at_15.50.02.png",
        "",
        ""
      ],
      "align": "center",
      "border": true
    }
  ]
}
[/block]


### Add Actions

Define a custom API action - specify the url, HTTP Method, request headers, query string, and request payload (if necessary).

Static and dynamic values are supported. Use the special character (%) and placeholders to specify dynamic values. The placeholders will be replaced with the dynamic values associated with the end user triggering the action. Credentials that were previously configured, such as %provider.api_key% or %provider.client_secret%, user traits that were ingested, and [form inputs](forms) are supported. Dynamic values are supported in the url, payload, headers, and query string.

Note - payload does not support complex json structures. Only a single level of keys and simple values is supported.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/8a45296-Screenshot_2024-05-02_at_15.52.36.png",
        "",
        ""
      ],
      "align": "center",
      "border": true
    }
  ]
}
[/block]