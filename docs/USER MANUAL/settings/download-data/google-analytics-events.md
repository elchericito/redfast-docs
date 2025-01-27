---
title: Google Analytics
excerpt: ''
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
# Google Analytics

API actions can be used to send data to the Google Analytics Measurement Protocol.

### Create an action

Follow the steps to create an API action. This action should be a POST request. The required url is listed here.

<Image align="center" src="https://files.readme.io/ebf7cc4-Google_Analytics_Custom_Action.png" />

### Specify the payload

Add parameters to the payload. These values can be static or dynamic. Supported parameters are described [here](https://developers.google.com/analytics/devguides/collection/protocol/v1/parameters). Required parameters include `v` (protocol version), `tid` (web property ID), and `t` (hit type). Optional parameters include `cid` (client id), `ea` (event action), and `el` (event label).

### Add action to prompt or experience

Follow the steps here to [add the action](actions-1) to a prompt or experience.
