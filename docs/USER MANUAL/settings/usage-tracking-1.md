---
title: Usage tracking
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
# Usage Tracking

### Redfast usage tracking allows you to track individual consumption of value-creating elements of your app or site.

A trait is an individual user attribute or behavior that can be targeted, such as their device, location, or even business metrics (e.g. lifetime value or satisfaction score). Redfast allows you to track traits based on how frequently a user has engaged a specific feature or section of your app. It allows you to target users based on frequency and recency of engagement for maximum impact. By default, usage traits automatically tracks visits and minutes but can be configured to track additional behaviors on your apps, such as specific pages/screens visited or buttons clicked.

Usage traits can be normalized on a 0-10 scale, with the lowest value in the dataset normalized to 0 and the highest value normalized to 10. The normalization is performed in real-time as new low-values and high-values are recorded. It enables business teams to easily define ‘Heavy users’ as those users whose minutes per visit are growing by 30% or more week over a week without any need to understand site-wide averages or highs and lows.

***

## Understanding Usage Tracking

Below are the types of usage trackers that are available. A newly added tracker will begin collecting information immediately, and it may take up to 24 hours before it can produce meaningful targeting options.

### Visit Duration

Time spent by the user in the app in MM:SS. Visit duration is recorded at the user level on a daily, weekly, and monthly basis.

### Visits

The number of times a user visits your site/ app. Visits are recorded on a daily, weekly, and monthly basis. The default visit length is 10 minutes, which is extended in 10-minute increments for as long as the user is using the app.

<Image align="center" className="border" border={true} src="https://files.readme.io/6af03f8-image.png" />

For day-over-day comparison purposes, Redfast compares data from **midnight to midnight on one day versus the previous day**. For week-over-week comparison, Redfast compares data from **midnight Sunday to midnight Sunday**.

In addition to visits and minutes, Redfast automatically tracks or creates:

* **Churn Score** – A number between 0-1 indicates the probability that a user will churn derived using machine learning. Find more on Churn Score.
* **Device Type** – Phone, tablet, laptop, desktop, TV, watch. Also includes full user agent string.
* **Device OS** – iOS, Android, Windows, MacOS, other. Also includes full user agent string.
* **Device Browser** – Chrome, Chrome Mobile, Safari, Edge, other. Also includes full user agent string.
* **Device Manufacturer** – Apple Iphone, Apple Ipad, Nexus, Samsung, other. Also includes full user agent string.
* **Device SDK** – Android Phone, Android Tablet, Google TV, Roku, other. Also includes full user agent string.

The following optional items require the processing of the end user’s IP address. IP addresses are never stored by Redfast. Your agreement specifies whether these additional items have been enabled for your app. Please contact your application administrator for details.

* **Fraud score** – A number between 0-10 ranking the user’s likelihood of being a fraudulent user derived using machine learning.

See [privacy](/overview/privacy.html) for more information on how process end-user information.

In addition, you can customize the tracker to collect information on specific pages or button clicks.

## Page Tracker

A page tracker allows you to track specific pages or groups of pages (by using wild cards or regex). Here are two examples.

<Image align="center" className="border" border={true} src="https://files.readme.io/166e7b8-Screenshot_2024-04-25_at_15.03.06.png" />

## Button Tracker (Web only)

A button tracker allows you to track specific elements that a user clicks using CSS.

<Image align="center" className="border" border={true} src="https://files.readme.io/ee7d53f-Screenshot_2024-04-25_at_15.06.07.png" />

## Custom Tracker

A custom tracker allows you to send tracking information from any external system to Redfast via API or SDK (available on Roku, Apple Tv, Android, and iOS). For example, if a user’s payment has failed, you can send an event from your backend, allowing you to target user’s to update their credit card via Redfast.

<Image align="center" className="border" border={true} src="https://files.readme.io/2db110e-image.png" />

# How to setup a tracker

Redfast comes with the ability to track your users’ behaviors across your applications. By default we automatically track user visits and minutes, but you can also add other trackers such as button clicks and views. Once you’ve added a new Redfast tracker you can use them to target segments such as top 20% of users who have downloaded a video.

This article will teach you to setup a new tracker.

Start by heading over to Settings > Usage Tracking > Add New Tracker

<Image align="center" className="border" border={true} src="https://files.readme.io/4a51089-Screenshot_2024-04-25_at_15.40.54.png" />

## Web Usage

For web apps you can create two types of trackers: page and track.

* **page** - refers to visits to a particular page such as /settings, /signup
* **track** - refers to a CSS id such as #download-btn or CSS class such as .download-btn

<br />

### Page Example

To track a user’s visits to the Settings page do the following.

1. Click “Add a tracker” and change the value to match your apps URL path. In addition to actual URLs, you may also use a regular expression to specify wildcard matches and other advanced URL configurations.

<Image align="center" className="border" border={true} src="https://files.readme.io/1363ad0-image.png" />

2. Click “Save Changes”

<Image align="center" className="border" border={true} src="https://files.readme.io/78b62f2-Screenshot_2024-04-25_at_15.46.49.png" />

3. Go to add a new segment

<Image align="center" className="border" border={true} src="https://files.readme.io/4c6e5ea-Screenshot_2024-04-25_at_15.47.45.png" />

4. Now under the “Usage” tab you can see the newly added Redfast trait you can target

<Image align="center" className="border" border={true} src="https://files.readme.io/dd7b0a2-Screenshot_2024-04-25_at_15.49.32.png" />

### Track Example

To track a user’s clicks of a particular button you do the following.

1. Click “Add a tracker” and change the value to match your HTML button id or button class 

<Image align="center" className="border" border={true} src="https://files.readme.io/d35ff75-image.png" />

<br />

2. Click “Save Changes”

<Image align="center" className="border" border={true} src="https://files.readme.io/319b3dc-Screenshot_2024-04-25_at_15.52.46.png" />

3. Go to add a new segment

<Image align="center" className="border" border={true} src="https://files.readme.io/a953556-Screenshot_2024-04-25_at_15.47.45.png" />

4. Now under the “Usage” tab you can see the newly added Redfast trait you can target

<Image align="center" className="border" border={true} src="https://files.readme.io/6d939dd-image.png" />

<br />

### Tracking Web Actions from Other Sites

A common example of tracking external conversions is the need to track links that refer users offsite. In many cases it’s difficult to see if the user actually converted (e.g. signed up, paid) after they land on the partner page. The following method requires you to add your user id to the url when you redirect to your partner. The partner site should save the user id. Then on completion of the conversion the partner needs to notify Redfast. Here is how to configure:

#### Custom Website Action

1. Create a redirect url using a custom website action which includes a rf\_uid parameter

```
 // https://example.com?campaign_id=456&rf_uid=123
 // rf_uid=123 is the important piece
 if (Redfast.anonymousUserId) {
return window.location.href = "https://example.com?campaign_id=456&rf_uid=" + Redfast.anonymousUserId;
 } else if (Redfast.userId) {
return window.location.href = "https://example.com?campaign_id=456&rf_uid=" + Redfast.userId;
 }
```

<br />

2. Go to Settings > Actions > Website Actions > Add New Action 

<Image align="center" className="border" border={true} src="https://files.readme.io/28e316d-Screenshot_2024-04-25_at_15.57.56.png" />

<br />

3. Add the code from step 1, make sure to change the url and parameters to your partner url, but make sure to keep rf\_uid intact. 

<Image align="center" className="border" border={true} src="https://files.readme.io/90e6242-image.png" />

<br />

4. Save the changes 

<Image align="center" className="border" border={true} src="https://files.readme.io/cda656e-image.png" />

<br />

5. Go to the prompt that you wish to redirect your from and click Website Actions > Add Action. 

<Image align="center" className="border" border={true} src="https://files.readme.io/f86eb59-Screenshot_2024-04-25_at_16.18.56.png" />

<br />

6. Add the custom website action 

<Image align="center" className="border" border={true} src="https://files.readme.io/09e2cab-Screenshot_2024-04-25_at_16.21.49.png" />

<br />

### Custom Tracker

1. Go to Settings > Usage Tracking > Add New Tracker 

<Image align="center" className="border" border={true} src="https://files.readme.io/5ab5bc5-Screenshot_2024-04-25_at_15.40.54.png" />

<br />

2. Add a new custom tracker 

<Image align="center" className="border" border={true} src="https://files.readme.io/b5a1e44-image.png" />

3. Click "Save Changes"

<Image align="center" className="border" border={true} src="https://files.readme.io/60b07dd-Screenshot_2024-04-25_at_17.08.08.png" />

<br />

4. Click the code icon \<> 

<Image align="center" className="border" border={true} src="https://files.readme.io/b2d3783-Screenshot_2024-04-25_at_17.09.47.png" />

<br />

5. Click External Web Tracker 

<Image align="center" className="border" border={true} src="https://files.readme.io/435b19a-Screenshot_2024-04-25_at_17.10.47.png" />

<br />

6. Your partner should add the first code block onto their landing page. This saves the referred user id. Usage→External

<Image align="center" className="border" border={true} src="https://files.readme.io/f3193d3-Screenshot_2024-04-25_at_17.12.33.png" />

<br />

6. Your partner should add the second code block onto their conversion page. This notifies Redfast of a successful conversion.

<Image align="center" src="https://files.readme.io/d61c1ac-Screenshot_2024-04-25_at_17.53.16.png" />

8. Add the tracker as a Custom Goal to your prompt (no need to wait for steps 6 and 7). This will allow you to see how your prompt is doing.

<Image align="center" className="border" border={true} src="https://files.readme.io/529a107-Screenshot_2024-04-25_at_17.14.04.png" />

<br />

9. Save the prompt 

<Image align="center" className="border" border={true} src="https://files.readme.io/e76c311-image.png" />

<br />

10. Once your partner has implemented steps 6 and 7 start the prompt to see results.

## Device Usage (Roku, Apple TV, Android, iPhone, iPad, Web)

For TVs, tablets, and phones you can create one type of tracker - custom. You will likely need your app developer’s help to do the following as it requires you to integrate a snippet of code that we provide you directly from Pulse.

NOTE: If you do not have the device SDK integrated or you are tracking from a 3rd party you will only be able to track via the cURL option as seen in step 4

### Custom Example

This example will show you how to add a custom tracker. You can use it to track anything on your client such as a click of a button, visits to different screens, payment, etc.

1. Click “Add a tracker” and name your tracker 

<Image align="center" className="border" border={true} src="https://files.readme.io/94cdc46-image.png" />

<br />

2. Click “Save Changes” Settings→Integrations

<Image align="center" className="border" border={true} src="https://files.readme.io/06d104c-Screenshot_2024-04-25_at_17.18.20.png" />

3. Now click the symbol \<> to see the devices you can integrate on and pick yours.

<Image align="center" className="border" border={true} src="https://files.readme.io/cc791c2-Screenshot_2024-04-25_at_17.19.13.png" />

4. Now select the programming language for your particular device. Here are reference examples. You may want your developer to read this section.

NOTE: You can continue this guide and have the integration completed later.

* **CURL** - Can be used in any system just provide the associated ENDUSER\_ID in your system. Make sure the rf-app set to the actual app id. This can be found in your browser url upon logging into Pulse e.g. /apps/fd07587a-dfac-47ef-a3db-789e57305ef1.

```
curl -H 'rf-app: xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxx' -H 'user-id: ENDUSER_ID' 'https://conduit.redfast.com/ping/?type=custom&custom_field_id=fc4ccd34-7876-430b-8b64-65ac7c19a505
```

* **Javascript** - For web or javascript clients. You might use this to track a payment or some other kind of activity that isn’t click or page based (if it’s outside of your app you must use the cURL option above).

```
Redfast.customTrack("fc4ccd34-7876-430b-8b64-65ac7c19a505");
```

* **External Web Tracker** - For 3rd party websites. You may want to track conversions such as signups that you’ve referred to a partner application. The tutorial can be found [here](https://dash.readme.com/project/redfast/v100.7/docs/user-traits)
* **HTML** - Tracking pixel for emails, web or javascript clients.

```
<img src="https://conduit.redfast.com/ping/?type=custom&custom_field_id=fc4ccd34-7876-430b-8b64-65ac7c19a505" />
```

* **SWIFT** - For Apple devices

```
PromotionManager.customTrack("fc4ccd34-7876-430b-8b64-65ac7c19a505")
```

* **KOTLIN** - For Android devices

```
PromotionManager.customTrack("fc4ccd34-7876-430b-8b64-65ac7c19a505")
```

* **ROKU** - For Roku devices

```
m.promoMgr.callFunc("customTrack", { custom_field_id: "fc4ccd34-7876-430b-8b64-65ac7c19a505" })
```

<Image align="center" className="border" border={true} src="https://files.readme.io/820a739-image.png" />

<br />

5. Go to add a new segment

<Image align="center" className="border" border={true} src="https://files.readme.io/36a5782-Screenshot_2024-04-25_at_15.47.45.png" />

<br />

6. Now under the “Usage” tab you can see the newly added Redfast trait you can target. Once the custom tracker from step 4 is integrated your users will automatically be segmented according to your needs

<Image align="center" className="border" border={true} src="https://files.readme.io/0cdc7c3-image.png" />

## Using events in Google Tag Manager

There may be cases in which GTM events can be used to perform certain actions with the Redfast SDK. Here is a quick primer on how to set it up.

### GTM Setup

* Setup a new Trigger that responds to an event. This example trigger looks for an event called `test` 

<Image align="center" src="https://files.readme.io/830c245-Screenshot_2024-04-29_at_2.51.28_PM.png" />

* Associate a tag with the trigger

<Image align="center" src="https://files.readme.io/5004849-Screenshot_2024-04-29_at_2.52.26_PM.png" />

* Publish the latest changes to production

<br />

### Testing

To test, send an event via the GTM dataLayer. Contents of the custom HTML tag will be executed.

```jsx
> dataLayer.push({'event': 'test'});

Test Event for anon user: c7c02a061db6aba3adae5263523005b57a8f90f16cf59d46fe036191213be5dd, user: 123
```
