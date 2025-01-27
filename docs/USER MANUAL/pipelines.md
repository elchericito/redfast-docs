---
title: Pipelines
excerpt: Lifecycle driven approach to prompts and guides
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
Redfast pipelines is a unique way to manage your users across various lifecycle stages. It is also a way to create and reinforce positive behavior loops with your audience.

### Lifecycle

Redfast provides three lifecycle-based pipelines:

* Member pipeline: This pipeline segments active users into five stages.
  * Anonymous: Visitors to your marketing landing pages.
  * Trial: Users in the trial phase of their subscription.
  * Monthly: Users on the monthly plan.
  * Premium: Users on the premium plan.
  * Pending Cancel: Users that have canceled their subscription but continue to have access.
  * Cancelled: Users that have churned.
* Engagement pipeline: This pipeline segments active users into the following stages:
  * New users
  * Repeat users
  * Regular users
  * Frequent users
  * Heavy users  
    Each stage's default settings can be modified to match your organization's definitions.
* E-commerce pipeline: 
  * Visitor: Users that have not yet commenced checkout
  * Shopper: Users with an item added to their cart
  * Checkout: Users in the checkout process
  * Customer: Users that have completed checkout

Each stage of every pipeline automatically further segments the users into:

* Engaged: users whose visits and minutes are on an increasing trajectory
* At Risk: users whose visits and minutes are on a decreasing trajectory
* Everyone else

### Behavior

Custom pipelines can be used to reinforce LTV-enhancing usage patterns. For example, if your analytics suggest that users who watch more episodic content have a higher LTV, you can set a 'Watch more episodic content' pipeline comprised of the following stages:

* Users who have watched one episode
* Users who have watched two episodes
* Users who have watched three or more episodes

### Moving users from one stage to the next

While a pipeline can give you a bird's-eye view of your active users, it can also be an invaluable tool for moving users from one stage to the next.

<br />

<Image align="center" className="border" border={true} src="https://files.readme.io/effdb79-Screenshot_2024-04-30_at_6.53.20_PM.png" />

For example, you can encourage engaged trial users to become members before their trial ends with a prompt that provides a one-time offer to a membership plan. Click on Add Prompt on the stage to select a prompt style for your prompt

Next, specify the sub-segments of users within this stage that will see the prompt as well as the goal for this prompt as shown below.

<br />

<Image align="center" src="https://files.readme.io/05d43d1-Screenshot_2024-04-30_at_7.00.32_PM.png" />

The remaining steps are identical to those for [creating a prompt](prompts).

<br />