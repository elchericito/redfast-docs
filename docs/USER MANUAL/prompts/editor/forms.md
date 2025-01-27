---
title: Forms
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
You can include up to three input fields or up to five survey options in your prompt. 

## Step-by-step

* [ ] Go to **Prompts** and select your prompt

  <Image align="center" className="border" border={true} src="https://files.readme.io/ce4a893-image.png" />
* [ ] Click **Edit prompt design**

  <Image align="center" className="border" border={true} src="https://files.readme.io/5477d38-image.png" />

### Adding an input field

* [ ] Select **Forms** and check **Enable Inputs** 
* [ ] Configure the input. The changes are reflected in the preview 

  <Image align="center" className="border" border={true} src="https://files.readme.io/70ea517-image.png" />

### Adding a survey

* [ ] Select **Forms** and toggle on **Survey** 
* [ ] Configure the options. The changes are reflected in the preview

  <Image align="center" className="border" border={true} src="https://files.readme.io/bb79ff4-image.png" />

## Set up Actions

Form input and survey option values can be sent to Connector Actions, API Actions, and Website Actions.

Connector actions that support form inputs: SendGrid, Braze, Freshdesk, Iterable.

How to use form inputs in website actions: When website action code is called, it will have access to an object variable called `args`. A sample value for args:

```
{  
  promoInput1Value: "[john@smith.com](mailto:john@smith.com)"  
}
```

Form inputs may be utilized in Connector Actions. An example is capturing an email address via form field and sending a predefined [Sendgrid](sendgrid) template to that contact.
