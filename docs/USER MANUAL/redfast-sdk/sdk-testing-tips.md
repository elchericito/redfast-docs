---
title: Testing Tips
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
### Setup Test Users

You may whitelist specific user IDs to be part of the "Test Users" segment. This allows you to test various prompts that are seen only by users within this group. See [here](test-users) for instructions on setting up test users.

### Test Cases

When testing, we recommend the following tips as you perform your test cases:

* Wait 5 seconds or so after starting the app before performing the test. Due to network connectivity, it may take a few seconds for the SDK to retrieve the prompt data.
* Perform the following steps to ensure the test user reset process completes properly:
  * Reset Test User from web interface
  * Start the app, wait a few seconds, close the app (this allows the SDK to completely reset the user)
  * Start the app, wait a few seconds and perform the test
* Note that pausing and starting prompt may take a few minutes to take effect due to propagation time. Leaving your test app open for a bit will help reduce propagation time.
