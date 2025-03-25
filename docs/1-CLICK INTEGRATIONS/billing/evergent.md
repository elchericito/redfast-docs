---
title: Evergent
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
## Activation

Provide the following to activate the Evergent integration. Note the integration utilizes the Evergent REST API - contact your Customer Success Manager if you utilize legacy platforms such as the SOAP API.

* Domain
* apiKey
* channelPartnerID

## Data Integration

Evergent can be configured to sync a daily CSV report with Redfast, which include the following subscriber traits that can be utilized for audience targeting. Reach out to your Customer Success Manager for details of the AWS S3 bucket destination for file sync operations.

| Trait Name                    | Description                                                                 |
| :---------------------------- | :-------------------------------------------------------------------------- |
| customer\_id                  | Customer/User ID                                                            |
| business\_unit                | Business unit owning subscription                                           |
| country                       | Billing country                                                             |
| current\_payment\_method      | \[Google Wallet, App Store Billing, Credit Card, Roku Payment, Coupon, etc] |
| pack\_id                      | Package ID                                                                  |
| package                       | Package Name                                                                |
| pack\_price                   | Package Price                                                               |
| pack\_type                    | Package Type                                                                |
| currency\_code                | 3 character currency code                                                   |
| valid\_from\_date             | Billing period start                                                        |
| valid\_to\_date               | Billing period end                                                          |
| payment\_status               | \[Declined, Posted]                                                         |
| payment\_type                 | \[Renewal, Purchase]                                                        |
| payment\_date                 | Date of most recent payment                                                 |
| declined\_reason              | Reason for payment decline                                                  |
| promotion\_amount             | Promotion Amount, if applicable                                             |
| promotion\_code               | Promotion Code, if applicable                                               |
| coupon\_code                  | Coupon code, if applicable                                                  |
| cancellation\_requested\_date | Date of cancellation request, if applicable                                 |
| classification                | Subscription classification status: \[Paid, Free Trial, Retail, etc]        |

## Supported Actions

> 📘 Evergent configuration varies from one instance to another. Not all of the below mentioned actions may be supported with your instance.

| Action                  | Description                                                                   | API Integration        |
| :---------------------- | :---------------------------------------------------------------------------- | :--------------------- |
| Redeem Coupon           | Apply coupon code to on existing package/product                              | redeemCoupon           |
| Change Service          | Upgrade or downgrade existing service on specified services (from and to)     | changeService          |
| Pause Subscription      | Pause active subscription for configurable number of days (max 90)            | pauseSubscription      |
| Resume Subscription     | Resume previously paused subscription                                         | resumeSubscription     |
| Reactivate Subscription | Reactivate previously removed subscription - subject to package/product terms | reactivateSubscription |
| Remove Subscription     | Remove active subscription as of billing period end date                      | removeSubscription     |