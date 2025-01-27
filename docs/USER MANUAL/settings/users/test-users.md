---
title: Test Users
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
## Setup Test Users

Redfast automatically creates a Test Users segment when your app is created. This allows you to test a prompt in your production environment in a fully published state but only visible to a small group of users.

You may whitelist specific user IDs to be part of the "Test Users" segment. This allows you to test various prompts that are seen only by users within this group. 

To add a test users: 

* [ ] Go to Settings > Users > Test Users

<Image align="center" className="border" border={true} src="https://files.readme.io/9c4e603-Screenshot_2024-05-22_at_15.20.44.png" />

* [ ] Designate a test user. Enter the User ID of a test account. User IDs can sometimes be a long alpha-numeric or hex string so make sure you copy the user id correctly from your source reference before entering it here.
* [ ] Hit 'Add'

<Image align="center" className="border" border={true} src="https://files.readme.io/85a7cff-Screenshot_2024-05-22_at_15.22.28.png" />

Once a test user is added, you can log in to your site/app with this user's credentials, and you will be eligible to see all active prompts targeted at the Test Users segment.

You can also preview prompts targeted at Test Users using our Live tool. To test using the Live tool:

* [ ] Click the Live Preview button. This will open your site and emulate your selected user.

<Image align="center" className="border" border={true} src="https://files.readme.io/2714f17-Screenshot_2024-05-22_at_15.23.56.png" />

* [ ] Open the Redfast Preview tool

<Image align="left" className="border" border={true} src="https://files.readme.io/0543e15-Screenshot_2024-05-22_at_15.25.01.png" />

* [ ] Notice your user ID is automatically set. Also notice the prompt status. If the status is 'Inactive' go to the page that the prompt is supposed to be active on.

<Image align="center" className="border" border={true} src="https://files.readme.io/5deb9c6-Screenshot_2024-05-22_at_15.35.23.png" />

<Image align="center" className="border" border={true} src="https://files.readme.io/a7583fa-Screenshot_2024-05-22_at_15.39.40.png" />

<Image align="center" className="border" border={true} src="https://files.readme.io/0eb2ab1-Screenshot_2024-05-22_at_15.40.24.png" />

* [ ] The prompt will now open
* [ ] The prompt has now been seen/ interacted with. To re-open the prompt hit the 'Reset' button. If it's not showing up click the Reset Clicks and Refresh button.

<Image align="center" className="border" border={true} src="https://files.readme.io/91b3825-Screenshot_2024-05-22_at_15.46.19.png" />

* [ ] Once you are satisfied you can exit
