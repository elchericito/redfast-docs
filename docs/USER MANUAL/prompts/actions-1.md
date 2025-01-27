---
title: Actions
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
Actions are events you can assign to a user's interaction with a prompt. For example, with a redirect action you can take the user to a specific area within your site as a result of the user clicking a prompt button. There are five possible user interactions that can be associated with one or more actions:

1. Accept: when the user clicks on the Accept button. 
2. Secondary Accept: when the user clicks on the secondary button (not available on all prompt types)
3. Decline: when the user clicks on the Decline button.
4. Dismiss: when the user clicks on the close button.
5. Timeout: when the prompt is closed due to a timeout timer.

A common use for a prompt with two buttons (accept and decline) is to have the accept button perform the affirmative action and the decline button perform the negative action. 

<Image align="center" className="border" border={true} src="https://files.readme.io/dbba980-image.png" />

**However, you may also use the two buttons to perform related actions**. The accept button can be configured to perform the primary action associated with the prompt while decline can be configured to perform a secondary action. For example, a prompt promoting the new release of content may set the accept button to the "Sign me up" action and the decline button to the "Add to watchlist" action.

<Image align="center" className="border" border={true} src="https://files.readme.io/ae7b5ec-image.png" />

<br />

## Configure an Action on a prompt

Actions are what happen when a user clicks on a button in a prompt. One or more actions can be performed. A simple action could be to subscribe a user to a mailing list or apply a discount to a user's account. Redfast comes with actions for a variety of platforms: billing, CMS, marketing, etc.

***

## Built-in Actions

<Image align="center" className="border" border={true} src="https://files.readme.io/48dd9f9-image.png" />

Built in actions are available with every prompt you create.

* Send an email. Sends an email to the specified address when the user accepts the prompt.
* Send an SMS. Sends a prompt-specific SMS message to the specified mobile number when the user accepts the prompt.
* Redirect the user. Redirects the user to the specified url when the user accepts the prompt.

## Connector actions

<Image align="center" className="border" border={true} src="https://files.readme.io/87d7647-image.png" />

Connector actions are actions that can be performed within third party business systems or backends. To use them all you need to do is add the respective credentials of the third party system. Refer to the following table for more information on connector actions.

* [ ] Go to prompts and select your prompt

  <Image align="center" className="border" border={true} src="https://files.readme.io/aace646-image.png" />
* [ ] Add an action to a prompt

  <Image align="center" className="border" border={true} src="https://files.readme.io/d186553-image.png" />
* [ ] Configure the action settings.\
  Select the Action type (i.e., External & API Actions), a user interaction that'll trigger the action (i.e., Sign Me Up button click), Connector (i.e., Zuora), a specific action (i.e., Subscribe a user to a specific plan), Plan value and Error Behavior:\
  **"Stop"** means downstream actions WILL NOT be executed.\
  **"Continue"** means downstream actions WILL be executed.

  <Image align="center" className="border" border={true} src="https://files.readme.io/4b6e880-image.png" />

  When you have a single action enabled it doesn't matter which Error Behavior option is selected. However, if you enable multiple actions it may matter. For example, you may need to unsubscribe a user before adding a new subscription plan. If the unsubscribe fails you most likely don't want to subscribe the user to the new plan or they may end up with 2 plans. In this case you would want to set the Cancel user subscription error action to "Stop" which will prevent the email from sending.
* [ ] Click Add Action

  <Image align="center" className="border" border={true} src="https://files.readme.io/09969e8-image.png" />
* [ ] You can repeat this process to add as many actions as you like for one or more interactions. Additionally you can re-order the actions by dragging and dropping.

  ![](https://files.readme.io/44de77d-image.png)

<br />

## Creating custom actions

You can create actions to: 

1. Connect to external marketing, support, and billing systems. [More info](connector-actions)
2. Perform custom API driven actions. [More info](api-actions)
3. Perform custom JS website actions. [More info](website-actions)

<br />

In some cases such as “1-click save offers,” assistance from the Redfast technical team may be helpful in getting things up and running quicker. Please reach out on the Slack channel for hands-on assistance.
