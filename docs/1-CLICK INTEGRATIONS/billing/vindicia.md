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

* API Username
* API Password

## Data Integration

* Vindicia billing traits are automatically ingested when connector is activated
* Products and campaigns are refreshed periodically
* Vindicia subscription or account ID must be synced to Redfast

## Supported Actions

| Action          | Description                                             | User Dependencies                                   | Additional Instructions         |
| --------------- | ------------------------------------------------------- | --------------------------------------------------- | ------------------------------- |
| Replace product | Replace a product in the user subscription with another | vindicia\_subscription\_id or vindicia\_account\_id | Select Product(s) from dropdown |
| Add campaign    | Add a campaign to a product in the user subscription    | vindicia\_subscription\_id vindicia\_account\_id    | Select Campaign from dropdown   |
| Add product     | Add a product to the user subscription                  | vindicia\_subscription\_id vindicia\_account\_id    | Select Product from dropdown    |
