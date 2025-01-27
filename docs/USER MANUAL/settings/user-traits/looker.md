---
title: Looker
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
# Export Looker CSV data to Redfast AWS S3 bucket

Rather than manually creating a CSV to import [traits](user-traits) to Redfast you can export it from Looker instead. This guide will help you create a daily export of your data.

1. Go to Settings > Custom Traits

   [block:image]{"images":[{"image":["https://files.readme.io/c23d4a0-settings-integrations.png","",""],"align":"center","sizing":"700px"}]}[/block]

2. Select "Click here for AWS S3 credentials"

   [block:image]{"images":[{"image":["https://files.readme.io/3ab86ef-settings-aws-modal.png","",""],"align":"center","sizing":"700px"}]}[/block]

3. Check the show credentials box to view your credentials. You will need to use the AWS Bucket, Access Key and Secret Key to login and securely upload via AWS. Keep this information handy, you will need it to upload the CSV.

   [block:image]{"images":[{"image":["https://files.readme.io/7b8d41a-aws-settings-1.png","",""],"align":"center","sizing":"700px"}]}[/block]

4. In another tab login to your [Looker account](https://looker.com/login)

   [block:image]{"images":[{"image":["https://files.readme.io/a91f5e4-looker-1.png","",""],"align":"center","sizing":"700px"}]}[/block]

5. Select your folder with your user data

   [block:image]{"images":[{"image":["https://files.readme.io/2d62fee-looker-2.png","",""],"align":"center","sizing":"700px","border":true}]}[/block]

6. Select an existing look from your list of files

   [block:image]{"images":[{"image":["https://files.readme.io/7d73497-looker-3.png","",""],"align":"center","sizing":"700px","border":true}]}[/block]

7. Make sure the first column of your data contains your customer IDs, if it does not please edit your Look and move it to the first column

   [block:image]{"images":[{"image":["https://files.readme.io/844acc0-looker-4a.png","",""],"align":"center","sizing":"700px","border":true}]}[/block]

8. Select "Create Schedules"

   [block:image]{"images":[{"image":["https://files.readme.io/90c9d44-looker-4.png","",""],"align":"center","sizing":"700px","border":true}]}[/block]

9. Select "Amazon S3" and copy over your credentials from Pulse and hit save. If you want you can also update the schedule from the default 6am at this time

   [block:image]{"images":[{"image":["https://files.readme.io/d2a0178-looker-5.png","",""],"align":"center","sizing":"700px"}]}[/block]

10. Redfast will now receive your user traits on a daily basis.