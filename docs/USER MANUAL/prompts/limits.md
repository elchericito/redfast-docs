---
title: Limits
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
**A limit allows you to restrict the number of users that receive a prompt.**\
You can limit each of your prompts separately or apply [global limits](global-limits) per account. 

## Impression limit

Impression limit allows you to restrict the total number of times a prompt can be shown to the targeted segment with no regard to a specific user. For example, setting it to 100 impressions, will limit the system to only show the prompt the first 100 times it's triggered.

<Image align="center" className="border" border={true} src="https://files.readme.io/a7d13f1-image.png" />

## Frequency Cap

Frequency Cap allows you to restrict the total number of times a user can be shown a prompt with a specified number of time. For example, setting it to 2 impressions over 30 days allows a particular user to see the prompt twice over a 30 day period. The 30 day period would start when the first impression is shown.

<Image align="center" className="border" border={true} src="https://files.readme.io/fb6c9f7-image.png" />

## Budget limit

Budget limit allows you to specify a consumable quantity that is decreased with each user action for a prompt. Budgets may be specified on a stand alone basis or in concert with user limits. This is useful when working with a financial budget. For example, if the budget is set to 10,000 with a decrement of 10; it is equivalent to a $10,000 budget that is reduced $10 at a time.

<Image align="center" className="border" border={true} src="https://files.readme.io/42214b6-image.png" />

## User Limit

User Limit allows you to restrict the total number of users that can take action on the prompt presented to them. For example, setting this to 1,000 will limit the total number of users that receive the prompt or segment to the first 1,000 users from the specified segments.

<Image align="center" className="border" border={true} src="https://files.readme.io/b726d62-image.png" />

## Delivery limit

Delivery limit allows you to set the maximum number of unique deliveries (times when a user is eligible to see the prompt should they satisfy the condition of the trigger). For example, if it is set to 1,000, we will deliver the prompt to 1,000 unique users and then stop.

<Image align="center" className="border" border={true} src="https://files.readme.io/9a7bf89-image.png" />

To learn about Global limits check [here](global-limits).
