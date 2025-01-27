---
title: Goals
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
# Custom Goals

Custom goals allow you to specify conversion goals outside of the Redfast system. Normally, Redfast defines a conversion as the total number of users that have accepted a prompt. If your prompt uses an action such as Stripe to upgrade/modify a user's plan then that would be perfectly acceptable. 

Your actual conversion goal can be one of many things. Here are some examples:

* Visit to a particular page on your webapp
* Visit to a particular screen on your device (TV, tablet, phone)
* Payment processed in your backend payment system
* Activity in a disparate system that Redfast cannot access

To add a custom goal you must create a [usage tracker](usage-tracking-1) first and then continue with this guide. Your usage tracker does not have to be integrated into your system at the outset. You can complete this guide without issue.

## Step-by-step

* [ ] Find a usage tracker you're interested in\
  In this example we are interested in when a user updates their payment method on the Redflix demo site and lands on the confirmation page` /payment-updated`. 

  <Image align="center" className="border" border={true} src="https://files.readme.io/c80c651-image.png" />
* [ ] Create or go to a prompt that you want to add the custom goal to.
* [ ] Go to to the **Custom Goal** section and click the **Add custom goal** button

  <Image align="center" className="border" border={true} src="https://files.readme.io/ea36176-image.png" />
* [ ] Select the goal tracker from the drop-down list, set the attribution duration and hit **Save**

  <Image align="center" className="border" border={true} src="https://files.readme.io/075d4bd-image.png" />
* [ ] Publish your prompt.
* [ ] A new **Custom goal** bar will appear under **Performance** to give you the number of users who performed your usage activity/completed the custom goal after interacting with the Redfast prompt.

  ![](https://files.readme.io/f478e3a-image.png)

<br />
