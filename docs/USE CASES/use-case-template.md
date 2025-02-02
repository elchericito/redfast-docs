---
title: Use Case Template
excerpt: A sample document to outline a use case
deprecated: false
hidden: true
metadata:
  robots: index
---
This document may be used to create a structured definition of the use case you wish to implement.

### Business Objective

Describe the primary outcome desired from the implementation of this use case.

Example. Reduce cancellations from monthly subscribers

### Outline

In a few sentences describe the end user experience that will achieve the desired outcome.

Example. When a member clicks on the 'Cancel' button on the Account page, show a multi-step guide to understand and mediate their reason for canceling.

The first step is to ask them the reasons for cancellation. Three options should be provided:

1. Too expensive
2. Not enough content
3. Not using it

The second step is conditional on the option selected.

If 'Too expensive' was selected, offer next month at no cost. Experiment between next month free, 50% off for two months.

If 'Not enough content' was selected, display upcoming new releases.

If 'Not using it' was selected, offer to pause the subscription for three months. Experiment between one, two, and three months.

Every path must include the option to 'Cancel anyway'.

### [Segment](/docs/segments#)

Describe the characteristics of the target users who should receive this experience.

Example. Members on the monthly plan with a non-IAP payment method and at least three months of successful rebills.

Required User Traits (attributes) :

* Plan type
* Payment method
* Lifetime (in months) or Member since (date)

### [Trigger](/docs/triggers#/)

Describe the end user action that will initiate the prompt or guide.

Example. When the member clicks on the 'Cancel' link on the /accounts page.

### [Schedule](/docs/schedule-1#/)

Optional. Specify a start and end date for this campaign.

### Design

<Cards columns={4}>
  <Card title="First Card" href="https://readme.com" icon="fa-home" target="_blank">
    Neque porro quisquam est qui dolorem ipsum quia
  </Card>

  <Card title="Second Card" icon="fa-user">
    *Lorem ipsum dolor sit amet, consectetur adipiscing elit*
  </Card>

  <Card title="Third Card" icon="fa-star">
    > Ut enim ad minim veniam, quis nostrud ullamco
  </Card>

  <Card title="Fourth Card" icon="fa-question">
    **Excepteur sint occaecat cupidatat non proident**
  </Card>
</Cards>

Optional:

* Legal disclaimer text
* Timer
* Customize the CSS to match your look and feel

### [Experiment](/docs/create-an-experiment#/)

### [Call to Action](/docs/actions-1#/)

Reasons for cancellations prompt: Select Option, Cancel Anyway.

Too expensive prompt: Accept Offer, Cancel Anyway

Not enough content prompt: See more, Cancel Anyway

Not using prompt: Pause my subscription, Cancel Anyway