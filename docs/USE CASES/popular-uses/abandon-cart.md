---
title: Abandon Cart
excerpt: >-
  Use Redfast to make it easy for returning visitors to resume sign up and
  checkout
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
More than 95% of the visitors to your website will not convert into paying customers. Redfast makes it easy to convert more of these visitors into paying customers by targeting visitors with abandoned carts and presenting them with a prompt to resume the checkout process.

Using this approach, your business can recover 40% or more of users with abandoned carts that return to the site.

<br />

<Image align="center" className="border" border={true} src="https://files.readme.io/50f04cb-Screenshot_2024-04-30_at_4.09.36_PM.png" />

<br />

***

> 👍 For best results, consider providing an incentive to complete the checkout process

## Step-by-step

* [ ] If you maintain visitor attributes related to cart abandonment, sync those attributes and create an `Abandoned Cart` segment. Otherwise, you may utilize the built in `Anonymous Users` segment.

* [ ] Follow these instructions to [Create a Popup Prompt](create-a-pop-up) 

* [ ] Modify the headline and message, including any dynamic variables for personalization, such as first name

* [ ] Under Add Action, set a redirect to the cart URL

* [ ] Set the segment to **Test Users**.

* [ ] Set the trigger to activate while on the checkout flow of the site (example "/checkout/\*"). Utilize the "Exit Intent" advanced trigger to recognize when anonymous users are attempting to leave the checkout process.

* [ ] Start the prompt

* [ ] Add your user ID to the Test Users segment (Settings > Users > Test Users)

* [ ] Confirm that the prompt is triggered when exhibiting Exit Intent while in the checkout flow

* [ ] Update the targeted segment to the one identified in Step 1
