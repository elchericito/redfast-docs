---
title: Piano
excerpt: Connecting Redfast with Piano
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
Connecting and syncing Redfast with Piano is done by setting up a periodic sync of user information from Piano to Redfast and configuring available 1-click actions.

## Sync subscriber info

### Using Piano Console

To export users from Piano software, please follow the below steps:

1. Log in to your Piano account.
2. Navigate to Reports → Logs → Subscriptions
3. Click on 'Export'
4. Once the export file has been prepared, it will be available in the Download Center

Please note that these steps might slightly vary based on the version of Piano software you are using. Please refer to this page for additional information: [Link](https://docs.piano.io/subscription-log-report/)

### Using Piano API

To export the subscription log, make use of the Piano Export API. Following the API's guidelines and documentation, you can export the subscription log which can then be further manipulated or analyzed as per your requirements.

Link: [Subscription Log Export API](https://docs.piano.io/api/?endpoint=post~2F~2Fexport~2Fschedule~2Fvx~2FsubscriptionLog)

Use the above API to schedule a Subscription Log export. Your Customer Success Manager can work with you to automate this process.

### Information synced

The following traits will be synced over for targeting purposes (this list may be updated depending on targeted use cases):

```
Subscription ID
Create date
Start date
End date
Days subscribed
Subscription status
Upgrade status
Trial status
Trial period end date
Auto-renew
Auto-renew disablement date
Billing period
Total charged
Next billing date
Renewed
Currently in grace period
Grace period start date
Grace period extended to
User ID (UID)
Access expiration date
Resource ID (RID)
Resource name
Term ID
Term name
Term type
Template ID
Template name
Offer ID
Offer name
Promo code
```

## 1-Click Actions

The following actions require the following to be configured with your Pulse instance:

* Piano Publisher API Token / API Key
* `aid` - Piano Application ID

### Resubscribe

In the event a subscription is marked to be cancelled, a 1-click action will invoke the [Resume Subscription API](https://docs.piano.io/api?endpoint=post~2F~2Fpublisher~2Fsubscription~2Fresume) to disable the cancellation and instead resume the subscription. In the event that the `subscription_id` is not specified. Redfast will automatically retrieve the required information through the List Subscriptions API.

### Upgrade Subscription

The [Upgrade Subscription API](https://docs.piano.io/api?endpoint=post~2F~2Fpublisher~2Fterm~2Fchange~2Fdo) is utilized to upgrade the term of the subscription. The “from” and “to” subscription IDs must be selected from the dropdown within Pulse. Before the transaction is completed, a check for the availability of the term change must return true.

The subscription term upgrade may take some time to be fulfilled, so it is suggeted that you include some language in the prompt indicating as such.

## Promo Codes

While there is currently no API to apply a promo code via 1-click action, the following integrations are available to support this use case.

* List and select from available promo codes
* Setup user segments targeting audiences for specific types of promo codes
* Auto-fill promo code during checkout process
* Conversion tracking from successful checkout process
* A/B testing performance across different promo codes
