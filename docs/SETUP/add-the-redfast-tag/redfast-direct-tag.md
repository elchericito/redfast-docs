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

The snippet can be found within Redfast > Settings > Usage Tracking.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/2c35d83-Screenshot_2024-05-23_at_16.23.58.png",
        "",
        ""
      ],
      "align": "center",
      "border": true
    }
  ]
}
[/block]


### Copy code snippet

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/9e21b53-Screenshot_2024-05-23_at_16.25.30.png",
        "",
        ""
      ],
      "align": "center",
      "border": true
    }
  ]
}
[/block]


### Locate the root html file

Open the project that you are integrating and locate the root html file with all the scripts. In our example it is called index.html.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/3520de0-js-tag-direct-3.png",
        "",
        ""
      ],
      "align": "center",
      "border": true
    }
  ]
}
[/block]


### Paste the code snippet

The snippet should be located right above the closing </head> tag. You may use the "defer" attribute if needed; it will not interfere with the operation of the Redfast JS SDK.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/5bffbbf-js-tag-direct-4.png",
        "",
        ""
      ],
      "align": "center",
      "border": true
    }
  ]
}
[/block]


### That's it! Save and deploy your project.