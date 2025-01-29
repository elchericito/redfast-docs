---
title: Zuora
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

* API URL
* Client ID
* Client Secret

## Data Integration

### 1-Click Actions

Once Activation is complete, Zuora product rate plans are refreshed periodically for use in the Redfast Console. In order to utilize 1-Click actions, the Zuora account number must be synced to Redfast.

### Automated Data Sync

Contact your customer success manager to activate an automated data sync of the following traits.

| Trait Name                | Values                                                                                                                                                   |
| :------------------------ | :------------------------------------------------------------------------------------------------------------------------------------------------------- |
| account\_number           | \<Zuora account number>                                                                                                                                  |
| status                    | Active, Canceled, Draft                                                                                                                                  |
| payment\_term             | \<configured payment term>                                                                                                                               |
| balance                   | \<outstanding account balance>                                                                                                                           |
| total\_invoice\_balance   | \<invoice balance>                                                                                                                                       |
| credit\_balance           | \<credit balance>                                                                                                                                        |
| contracted\_mrr           | \<contracted MRR>                                                                                                                                        |
| term\_type                | TERMED, EVERGREEN                                                                                                                                        |
| subscription\_start\_date | \<date when the subscription term starts>                                                                                                                |
| subscription\_end\_date   | \<date when the subscription term starts>                                                                                                                |
| term\_start\_date         | \<The date when the subscription term begins. If this is a renewal subscription, then this date is different from the subscription start date.>          |
| term\_end\_date           | \<The date when the subscription term ends. If the subscription is evergreen, the TermEndDate value is null or is the cancelation date, as appropriate.> |
| auto\_renew               | true, false                                                                                                                                              |
| rate\_plan\_name          | \<name of most recent rate plan>                                                                                                                         |

<br />

## Supported Actions

| Action               | Description                                       | Additional Instructions                                                                                         |
| -------------------- | ------------------------------------------------- | --------------------------------------------------------------------------------------------------------------- |
| Add Plan             | Add selected product rate plan                    | Select Product Rate Plan from dropdown                                                                          |
| Remove Plan          | Remove selected product rate plan                 | Select Product Rate Plan from dropdown                                                                          |
| Cancel Subscription  | Cancels the active subscription on the account    | Select Cancellation Policy (EndOfCurrentTerm, EndOfLastInvoicePeriod, SpecificDate), Apply Credit (true, false) |
| Suspend Subscription | Suspends the active subscription on the account   | Specify Suspend Policy (Today, EndOfLastInvoicePeriod, SpecificDate, FixedPeriodsFromToday)                     |
| Resume Subscription  | Resumes the suspended subscription on the account | Select Resume Policy (Today, FixedPeriodsFromSuspendDate, FixedPeriodsFromToday, SpecificDate, suspendDate)     |
| Change Auto Renewal  | Update whether subscription automatically renews  | Select Auto Renwal (true, false)                                                                                |
| Create Subscription  | Create new subscription with specified rate plan  | Select contractEffectiveDate, renewalTerm, ratePlan and termType                                                |

## Step by Step

Steps to configure a one-click subscription within a personalization

1. Go to Personalization. Select "Add Action"
2. Select Zuora → Subscribe Plan
3. Select product rate plan from dropdown

   ![subscribe-plan](https://files.readme.io/f6b632e-Zuora_action.png)

## Additional References

[Zuora API Info](https://www.zuora.com/developer/api-reference/)