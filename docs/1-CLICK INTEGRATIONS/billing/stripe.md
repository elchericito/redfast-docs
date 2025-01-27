---
title: Stripe
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

You may activate the Stripe connector utilizing one of two methods: Stripe Connect or API Key. Stripe Connect allows integration with Redfast by authenticating with an existing Stripe user account. Alternatively, you may opt to generate a new API Key.

### Option 1: Stripe Connect

Visit Settings → Actions → Stripe and click on the following button. You will be taken to the Stripe.com site to complete authentication.\
![stripe-connect](https://files.readme.io/c2a06fc-Stripe_Connect.png)

### Option 2: API Key

Within the Stripe portal, visit the Developers → API Keys screen and look for the section as depicted below. Create a new Restricted Key and set the following permissions.\
![stripe-key](https://files.readme.io/3020621-Stripe_key.png)

| Resource Type   | Permissions | Connect Permissions |
| --------------- | ----------- | ------------------- |
| Customers       | Write       | None                |
| Subscriptions   | Write       | None                |
| Products        | Read        | None                |
| Prices          | Read        | None                |
| Coupons         | Read        | None                |
| Promotion Codes | Read        | None                |

Finally, copy the resulting token into the Stripe setup form located in the Settings → Actions → Stripe screen.

## Data Integration

### 1-Click Actions

Once Activation is complete, Stripe Plans and Coupons are refreshed periodically for use in the Redfast Console. In order to utilize 1-Click actions, the stripe ID or email address must be synced to Redfast.

### Automated Data Sync

When utilizing Stripe Connect, a webhook will be activated to sync changes to a user's subscription status with Redfast. The following traits will be automatically synced in real-time and available for use within Pulse.

Contact your customer success manager if you need instructions on how to setup a webhook to activate the automated data sync.

Note that there must be a separate CSV sync that maps your userID to the Stripe Customer ID.

| Trait Name                  | Values                                                                                                          |
| :-------------------------- | :-------------------------------------------------------------------------------------------------------------- |
| subscription\_status        | incomplete, incomplete\_expired, trialing, active, past\_due, canceled, unpaid, paused or NONE                  |
| delinquent                  | true, false (set to true when there is a payment failure)                                                       |
| current\_period\_start      | \< Start date of current billing period >                                                                       |
| current\_period\_end        | \< End date of current billing period >                                                                         |
| canceled\_at                | \< Date of cancellation >                                                                                       |
| cancel\_at\_period\_end     | true, false                                                                                                     |
| trial\_start                | \< Start date of trial >                                                                                        |
| trial\_end                  | \< End date of trial >                                                                                          |
| subscription\_plan          | \< Name of current or most recent subscription plan >                                                           |
| recurring\_interval         | day, week, month or year                                                                                        |
| coupon                      | \< Coupon name >                                                                                                |
| payment\_card\_brand        | \< Payment card brand > - amex, diners, discover, eftpos\_au, jcb, link, mastercard, unionpay, visa, or unknown |
| payment\_card\_country      | \< Payment card country - 2 char country code >                                                                 |
| payment\_card\_expiration   | \< Payment card expiration date >                                                                               |
| payment\_card\_wallet\_type | \< Payment card wallet type, if applicable > - apple\_pay, google\_pay, etc                                     |

## Supported Actions

| Action                                    | Description                                                | User Dependencies                       | Additional Instructions                                                                                                                                                    |
| ----------------------------------------- | ---------------------------------------------------------- | --------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Update existing subscription              | Subscription updated to switch user to a different product | stripe\_id or email\_address            | Multiple proration options available. Refer to Stripe's [documentation](https://stripe.com/docs/billing/subscriptions/upgrade-downgrade#proration) for additional details. |
| Extend trial                              | Extend the user's trial for a specific plan                | stripe\_id (customer) or email\_address | Select the plan and configure the length of the extension on the prompt screen                                                                                             |
| Apply coupon code                         | Applies a coupon to the customer account                   | stripe\_id or email\_address            | Select coupon code from the dropdown. Manage coupon codes in the Stripe dashboard under Billing > Coupons.                                                                 |
| Subscribe the user to a specific plan     | Creates a subscription for the user to the selected plan   | stripe\_id or email\_address            | Select which plan to subscribe the user to on the prompt screen. Manage plans in the Stripe dashboard under Billing > Products                                             |
| Unsubscribe the user from a specific plan | Cancels a subscription for the user to the selected plan   | stripe\_id or email\_address            | Select which plan to cancel on the prompt screen. Manage plans in the Stripe dashboard under Billing > Products                                                            |

## Additional Information

* [Stripe API Key Setup](https://docs.stripe.com/keys)
* [Stripe Proration](https://stripe.com/docs/billing/subscriptions/upgrade-downgrade#proration)
