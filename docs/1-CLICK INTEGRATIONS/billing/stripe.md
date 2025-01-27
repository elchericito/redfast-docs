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

Visit Settings → Actions → Stripe and click on the following button. You will be taken to the Stripe.com site to complete authentication.  
![stripe-connect](https://files.readme.io/c2a06fc-Stripe_Connect.png)

### Option 2: API Key

Within the Stripe portal, visit the Developers → API Keys screen and look for the section as depicted below. Create a new Restricted Key and set the following permissions.  
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

| Trait Name               | Values                                                                                                         |
| :----------------------- | :------------------------------------------------------------------------------------------------------------- |
| subscription_status      | incomplete, incomplete_expired, trialing, active, past_due, canceled, unpaid, paused or NONE                   |
| delinquent               | true, false (set to true when there is a payment failure)                                                      |
| current_period_start     | \< Start date of current billing period >                                                                      |
| current_period_end       | \< End date of current billing period >                                                                        |
| canceled_at              | \< Date of cancellation >                                                                                      |
| cancel_at_period_end     | true, false                                                                                                    |
| trial_start              | \< Start date of trial >                                                                                       |
| trial_end                | \< End date of trial >                                                                                         |
| subscription_plan        | \< Name of current or most recent subscription plan >                                                          |
| recurring_interval       | day, week, month or year                                                                                       |
| coupon                   | \< Coupon name >                                                                                               |
| payment_card_brand       | \< Payment card brand > - amex, diners, discover, eftpos_au, jcb, link, mastercard, unionpay, visa, or unknown |
| payment_card_country     | \< Payment card country - 2 char country code >                                                                |
| payment_card_expiration  | \< Payment card expiration date >                                                                              |
| payment_card_wallet_type | \< Payment card wallet type, if applicable > - apple_pay, google_pay, etc                                      |

## Supported Actions

| Action                                    | Description                                                | User Dependencies                     | Additional Instructions                                                                                                                                                    |
| ----------------------------------------- | ---------------------------------------------------------- | ------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Update existing subscription              | Subscription updated to switch user to a different product | stripe_id or email_address            | Multiple proration options available. Refer to Stripe's [documentation](https://stripe.com/docs/billing/subscriptions/upgrade-downgrade#proration) for additional details. |
| Extend trial                              | Extend the user's trial for a specific plan                | stripe_id (customer) or email_address | Select the plan and configure the length of the extension on the prompt screen                                                                                             |
| Apply coupon code                         | Applies a coupon to the customer account                   | stripe_id or email_address            | Select coupon code from the dropdown. Manage coupon codes in the Stripe dashboard under Billing > Coupons.                                                                 |
| Subscribe the user to a specific plan     | Creates a subscription for the user to the selected plan   | stripe_id or email_address            | Select which plan to subscribe the user to on the prompt screen. Manage plans in the Stripe dashboard under Billing > Products                                             |
| Unsubscribe the user from a specific plan | Cancels a subscription for the user to the selected plan   | stripe_id or email_address            | Select which plan to cancel on the prompt screen. Manage plans in the Stripe dashboard under Billing > Products                                                            |

## Additional Information

- [Stripe API Key Setup](https://docs.stripe.com/keys)
- [Stripe Proration](https://stripe.com/docs/billing/subscriptions/upgrade-downgrade#proration)