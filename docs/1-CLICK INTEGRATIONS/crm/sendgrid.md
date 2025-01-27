---
title: Sendgrid
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
## Required Settings

* API key

[Sendgrid API Keys](https://sendgrid.com/docs/ui/account-and-settings/api-keys/)

## Supported Actions

| Action                      | Description                                 | User Dependencies         | Additional Instructions                                                                                        | Form Inputs |
| --------------------------- | ------------------------------------------- | ------------------------- | -------------------------------------------------------------------------------------------------------------- | ----------- |
| Send dynamic template email | Sends a dynamic templated email to the user | email\_address (optional) | Select which dynamic template to use on the prompt screen. Set up dynamic templates in the Sendgrid dashboard. | optional    |
| Add user to list            | Adds the user to a Sendgrid list            | email\_address            | Select which list to use on the prompt screen. Set up lists in the Sendgrid dashboard.                         | n/a         |

## Additional Information

[Sendgrid lists](https://www.twilio.com/docs/sendgrid/api-reference/lists/create-list)

<Image align="center" src="https://files.readme.io/b2d12bf-sendgrid-lists-1.png" />

<Image align="center" src="https://files.readme.io/ea49a4a-sendgrid-dynamic-templates-2.png" />
