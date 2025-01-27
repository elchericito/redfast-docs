---
title: Adobe Dynamic Tag Manager
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
You can integrate the Redfast javascript client into your web application via Adobe DTM with the tutorial below. Once you've finished this step Redfast will begin connecting our data with your imported data to learn about your customers.

### Configure Embed Code

There are three hosting options available with DTM:

* Akamai
* FTP Delivery
* Library Download

Location options are:

* Header
* Footer

We recommend that you choose Akamai hosting and placing the embed tag in the Header section. For greater control Redfast can work with your IT team to support the Library Download option.

#### Rules

In most cases the Page-Load rule is most appropriate when targeting areas of the site.

<Image align="center" className="border" border={true} src="https://files.readme.io/b53b37f-rules2.png.img.png" />

#### Workflows

We recommend that you configure a workflow such that the tag can be propagated from a non production (i.e. Staging) to the production environment utilizing the approval workflow made available in DTM.

<Image align="center" className="border" border={true} src="https://files.readme.io/77107ad-image_8.png.img.png" />

#### Installation

The DTM header code that is needed to load the Redfast tag should be added to all pages of the site./

<Image align="center" className="border" border={true} src="https://files.readme.io/cdc7383-image_11.png.img.png" />
