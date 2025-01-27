---
title: Chargify
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

* Api Key 
* Domain 

## Data Integration

* Products and coupons are refreshed periodically 
* Chargify ID must be synced to Redfast 

## Supported Actions

| Action              | Description                                              | User Dependencies | Additional Instructions                              |
| ------------------- | -------------------------------------------------------- | ----------------- | ---------------------------------------------------- |
| Create subscription | Subscribes a user to a product                           | chargify\_id      | Select the plan on the prompt screen                 |
| Cancel subscription | Cancels a user's subscription to a product               | chargify\_id      | Select the plan on the prompt screen                 |
| Add coupon code     | Adds a coupon code to a user's subscription to a product | chargify\_id      | Select the plan and coupon code on the prompt screen |
