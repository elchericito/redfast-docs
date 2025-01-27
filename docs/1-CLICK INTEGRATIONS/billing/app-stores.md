---
title: App Stores
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
# Introduction

When utilizing the Redfast SDK on devices, you may specify that the main CTA within the prompt should initiate the in-app purchase flow for a specific in-app product. Instructions for each platform are below.

# Roku App Store

1. Go to Prompt Edit Screen
2. Specify Product ID within In-App Purchase section (should match Roku In-Channel Product Identifiers)
3. Select from Dropdown whether In-App purchase is an Upgrade or Downgrade

<Image align="center" width="500px" src="https://files.readme.io/a4de93b-roku-inapp.png" />

4. When end user clicks on the CTA, the app will initiate the appropriate upgrade or downgrade purchase flow

# Apple App Store

## Add In-App Product IDs

1. Go to Settings → Actions → Apple
2. Define one or more Product IDs (should match those configured within App Store Connect)

   <Image align="center" width="600px" src="https://files.readme.io/d01be52-apple-add-inapp-product.png" />
3. Go to Prompt Edit Screen and specify Product ID within In-App Purchase section

   <Image align="center" width="500px" src="https://files.readme.io/f500c36-appstore-select-inapp.png" />
4. When end user clicks on the CTA, the app will initiate the In-App purchase flow

# Google Play Store

1. Go to Prompt Edit Screen
2. Specify Product ID within In-App Purchase section
3. When end user clicks on the CTA, the app will initiate the In-App purchase flow
