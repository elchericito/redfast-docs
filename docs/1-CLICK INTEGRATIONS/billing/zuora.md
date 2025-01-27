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

- API URL
- Client ID
- Client Secret

## Data Integration

- Billing traits are automatically ingested when connector is activated
- Product Rate Plans are refreshed periodically
- Zuora account number must be synced to Redfast

## Supported Actions

| Action               | Description                                                     | User Dependencies | Additional Instructions                |
| -------------------- | --------------------------------------------------------------- | ----------------- | -------------------------------------- |
| Subscribe Plan       | Creates subscription associated with selected product rate plan | Account Number    | Select Product Rate Plan from dropdown |
| Cancel Subscription  | Cancels the active subscription on the account                  | Account Number    |                                        |
| Suspend Subscription | Suspends the active subscription on the account                 | Account Number    |                                        |
| Resume Subscription  | Resumes the suspended subscription on the account               | Account Number    |                                        |

## Step by Step

Steps to configure a one-click subscription within a personalization

1. Go to Personalization. Select "Add Action"
2. Select Zuora → Subscribe Plan
3. Select product rate plan from dropdown

   ![subscribe-plan](https://files.readme.io/f6b632e-Zuora_action.png)

## Additional References

[Zuora API Info](https://www.zuora.com/developer/api-reference/)