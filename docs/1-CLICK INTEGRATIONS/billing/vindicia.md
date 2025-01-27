---
title: Vindicia
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

- API Username
- API Password

## Data Integration

- Vindicia billing traits are automatically ingested when connector is activated
- Products and campaigns are refreshed periodically
- Vindicia subscription or account ID must be synced to Redfast

## Supported Actions

| Action          | Description                                             | User Dependencies                               | Additional Instructions         |
| --------------- | ------------------------------------------------------- | ----------------------------------------------- | ------------------------------- |
| Replace product | Replace a product in the user subscription with another | vindicia_subscription_id or vindicia_account_id | Select Product(s) from dropdown |
| Add campaign    | Add a campaign to a product in the user subscription    | vindicia_subscription_id vindicia_account_id    | Select Campaign from dropdown   |
| Add product     | Add a product to the user subscription                  | vindicia_subscription_id vindicia_account_id    | Select Product from dropdown    |