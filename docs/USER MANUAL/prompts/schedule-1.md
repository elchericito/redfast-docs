---
title: Schedule
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
**A schedule allows you to restrict a prompt or guide to a specific time schedule.** For example, you can restrict a prompt or guide to be active between May 1st, 2024 to December 31st, 2024 and further limited to Thursdays, Fridays, and Saturdays between 6 pm and 11 pm.

A time schedule consists of:

## Date Window

This is an overall start date and end date setting for the prompt or path. The prompt or path will only be active between 12:01 am on the start date and 11:59 pm on the end date. This is an optional setting. If it is not set, the prompt or path will be shown on all dates.

<Image align="center" className="border" border={true} src="https://files.readme.io/bc5ca6e-image.png" />

## Day Part

This setting allows you to specify specific days of the week when the prompt or path is active. This is an optional setting. If it is not set, the prompt or path will be shown on all days.

<Image align="center" className="border" border={true} src="https://files.readme.io/bfd314d-image.png" />

### Time Part

This setting allows you to set specific times of the day when the prompt is active. A time part is treated as a sub setting of the day part which means that in order to specify a time window, you will also need to specify the days. You are required to also specify whether the schedule is enforced on the user's timezone or the app's timezone.

<Image align="center" className="border" border={true} src="https://files.readme.io/a77ae00-image.png" />

![](https://files.readme.io/fcbe451-image.png)

<br />