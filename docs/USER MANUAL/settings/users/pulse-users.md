---
title: Pulse Users
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
When procurred with an application, Redfast will set up an admin user account(s) for your team to access the Pulse app. Usually, the first account is created with a **Company admin** or **App admin** permission level. Only Company and App admins can modify settings and invite new users.

## Permission levels

### Company admin

**Company admins** can **create and change** all of a specific company's apps and add new apps (i.e., staging environment app) within the same company.

### App admin

**App admins** have the same ability to alter app settings as company admins, but only for a specific app and cannot create new apps. If you'd like your staging and production apps to have different admins, you should set the company settings to **Member** and the corresponding app settings to **Admin**.

<Image align="center" className="border" border={true} src="https://files.readme.io/7b25a52-image.png" />

### App Member

**App Members** can see the dashboard and modify prompts and segments, but they cannot edit the app "Settings" section.

### Read only

**Read only** users can view the dashboard but cannot modify any of the prompt/app settings.

## How-to-guide

To add a user:

* [ ] Go to Settings > Users > Add user

  <Image align="center" className="border" border={true} src="https://files.readme.io/8080696-image.png" />
* [ ] Input user name and email along with permissions level. To learn more about permission levels check [here](pulse-users).

  <Image align="center" className="border" border={true} src="https://files.readme.io/9bca05b-image.png" />
* [ ] The invitee will now receive an email invitation to create their login credentials

  <Image align="center" className="border" border={true} src="https://files.readme.io/9f75c54-image.png" />