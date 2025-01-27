---
title: Website
excerpt: >-
  Javascript snippets that can connect with your website code to unlock 1-click
  capabilities
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
Website actions allow the Redfast tool to call custom client side code, optionally passing information from form inputs. This page describes how to set up and use website actions.

### Add a simple action

Several simple actions such as redirecting to a new URL or opening a URL in a new tab are readily available. For example, to add a website action that opens a new tab with the specified URL:

1. From the prompt detail page, add a new website action
2. Select ‘Open URL on New Tab’
3. Click Add action
4. Click on the edit / pencil icon
5. Add a new argument with key=url and value equal to the link you want to take the user to

### Add custom Javascript code

1. Visit Settings → Actions → Website Actions 

<Image align="center" className="border" border={true} src="https://files.readme.io/9e361b2-Screenshot_2024-04-30_at_22.47.54.png" />

2. Create a website action. Specify the name of the action and write the code. See [form inputs](https://dash.readme.com/project/redfast/v100.7/docs/forms) for more information on accessing user input.

<Image align="center" className="border" border={true} src="https://files.readme.io/2272dcc-Screenshot_2024-04-30_at_22.51.56.png" />

3. Save the changes 

<Image align="center" className="border" border={true} src="https://files.readme.io/a30b0cb-Screenshot_2024-04-30_at_22.53.42.png" />

4. Go to Prompts and select your prompt 

<Image align="center" className="border" border={true} src="https://files.readme.io/6354038-Screenshot_2024-04-30_at_22.55.04.png" />

5. Add the website action

<Image align="center" className="border" border={true} src="https://files.readme.io/1928bd0-Screenshot_2024-05-01_at_21.30.27.png" />

<Image align="center" className="border" border={true} src="https://files.readme.io/921f4c4-Screenshot_2024-05-01_at_21.31.29.png" />
