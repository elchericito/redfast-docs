---
title: Direct
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
You can integrate the Redfast JS SDK into your web application with the steps below. Once you've finished this step Redfast will begin connecting our data with your imported data to learn about your customers.

### Login to redfast and go to your app

Make sure you are on the right app.

### Retrieve the JS code snippet

The snippet can be found within Redfast &gt; Settings &gt; Usage Tracking.

<Image align="center" className="border" border={true} src="https://files.readme.io/2c35d83-Screenshot_2024-05-23_at_16.23.58.png" />

### Copy code snippet

<Image align="center" className="border" border={true} src="https://files.readme.io/9e21b53-Screenshot_2024-05-23_at_16.25.30.png" />

### Locate the root html file

Open the project that you are integrating and locate the root html file with all the scripts. In our example it is called index.html.

<Image align="center" className="border" border={true} src="https://files.readme.io/3520de0-js-tag-direct-3.png" />

### Paste the code snippet

The snippet should be located right above the closing &lt;/head&gt; tag. You may use the "defer" attribute if needed; it will not interfere with the operation of the Redfast JS SDK.

<Image align="center" className="border" border={true} src="https://files.readme.io/5bffbbf-js-tag-direct-4.png" />

### That's it! Save and deploy your project.