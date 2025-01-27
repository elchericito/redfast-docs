---
title: Salesforce
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
The Redfast Salesforce connector integrates with Support Cloud as well as Marketing Cloud. In order to activate the connector, go to Pulse → Settings → Actions, then select the Salesforce connector. Required connector credentials are below.

## Support Cloud Credentials

* username
* password
* security token
* client id
* client secret

## Marketing Cloud Credentials

* client id
* client secret
* from email address
* base url
* auth base url
* soap base url

## Supported Connector Actions

| Action                                                        | Description                                                                                                                                 | User Dependencies                | Additional Instructions                                                                                   | Form Inputs |
| ------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------- | --------------------------------------------------------------------------------------------------------- | ----------- |
| Create a Case (Support)                                       | Creates a support case within Salesforce with information about the user and prompt                                                         | n/a                              | n/a                                                                                                       | n/a         |
| Post offer acceptance to feed of all existing cases (Support) | Adds a feed item with information about the user and prompt to all support cases within Salesforce that have the user listed as the Contact | salesforce\_id or email\_address | n/a                                                                                                       | n/a         |
| Triggered Send (Marketing Cloud)                              | Sends a templated email to the user                                                                                                         | email\_address (optional)        | Select the email template on the prompt screen. Set up dynamic templates in the Marketing Cloud dashboard | optional    |
| Add Subscriber to List (Marketing Cloud)                      | Adds an existing subscriber to the specified list                                                                                           | n/a                              | Select the list on the prompt screen. Set up lists in the Marketing Cloud dashboard                       | n/a         |
| Add User to List with form input (Marketing Cloud)            | Creates a subscriber based on the input email address and adds them to the specified list                                                   | n/a                              | Select the list on the prompt screen. Set up lists in the Marketing Cloud dashboard                       | required    |

## Installing Journey Builder Activity

1. Go to Marketing Cloud Setup screen
2. Within Apps → Installed Packages, click on "New"
3. Specify Name "Redfast"
4. Click "Add Component", select `Journey Builder Activity` and click "Next"
5. Specify Name `Redfast`, Category `Messages` and Endpoint URL `https://jbuilder.redfast.com>/<appid>/` (AppID can be found within Pulse → Settings → Application)

Once completed, Redfast will appear as a Message activity within Journey Builder.

## Additional Information

* [Salesforce Credentials](https://developer.salesforce.com/forums/?id=906F0000000AfcgIAC)
* [Salesforce Client ID and Secret](https://salesforce.stackexchange.com/questions/40346/where-do-i-find-the-client-id-and-client-secret-of-an-existing-connected-app/224659#224659)
