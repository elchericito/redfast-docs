---
title: Braintree
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

* Merchant ID
* Public key
* Secret key

## Supported Actions

| Action         | Description                           | User Dependencies               | Additional Instructions            |
| -------------- | ------------------------------------- | ------------------------------- | ---------------------------------- |
| Subscribe Plan | Subscribe the user to a specific plan | braintree or email\_address     | Select plan from dropdown          |
| Add Discount   | Add discount to the user subscription | braintree\_id or email\_address | Select discount code from dropdown |

## Additional Information

[Braintree API keys](https://developer.paypal.com/braintree/articles/control-panel/important-gateway-credentials)
