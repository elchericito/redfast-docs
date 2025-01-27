---
title: Segments
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
A segment is a group of users joined by a common set of [traits.](user-traits)  Traits can be combined to create a segment.

There is a list of dynamic traits we offer out of the box, such as usage (visits/minutes), device, location, or a user's interactions with other prompts, but you can also import any additional user traits to target users based on characteristics beyond site/app usage.  User traits can be imported either by bulk ingest, using AWS S3 or uploading a CSV in Pulse, or by sending event data from your application.

A user may belong to more than one segment. There are no limits on the number of segments that may be created.

## Examples of commonly created segments:

* Monthly Plan members whose visits are trending down.
* Trial users.
* Payment failed users.

Segments can be combined with [Usage Tracking](usage-tracking-1)  to unlock additional functionality.  

Examples of commonly created usage segments:

* Users who have never visited a specific part of your app.
* Users who have never visited a specific piece of content in your app.
* Users who have visited the account or cancellation page.
* Users who have clicked the payment button.

## How to create a segment

Think of the users you'd like to target for your selected use cases and create the desired segments. You should determine if there are any additional user traits to be synced into Redfast and import them. 

For example you may want to create a segment for “Engaged premium plan users.” 

* You can configure what “Engaged” means, such as: number of minutes per day, episodes watched, or any other behavior in your app using default 'Usage' trait

* With respect to the “premium plan” it’s best to send in the information on a periodic (daily, weekly, or realtime) basis for accuracy since users can change their plan over email, or calling. 

<br />

### How-to video

Here is a video tutorial that shows how to set up an example Segment. 

<Embed url="https://www.loom.com/embed/5e730b455754424fa13f1f282bcaafe6?sid=669292ce-0cd1-4d29-960a-ad13a1aebd5c" provider="loom.com" href="https://www.loom.com/embed/5e730b455754424fa13f1f282bcaafe6?sid=669292ce-0cd1-4d29-960a-ad13a1aebd5c" typeOfEmbed="iframe" height="480px" width="100%" iframe="true" title="undefined" />

***

<br />

### Step-by-step

Here is a step-by-step guide on how to set up an example segment of **Engaged US-based iOS Premium plan users who have not redeemed the iOS prompt**.

* [ ] Go to Segments > New Segment
* [ ] Configure the segment by giving it a name and description (optional)
* [ ] For 'Engaged', select 'Usage' -> 'Visits' -> '**Greater than or equal to**' -> '2' -> over the last '**7 days**' which will give you users who visited your site at least two times per last 7 days.
* [ ] For 'US-based', select 'Location' -> 'Countries' -> 'Include' -> 'United States of America'
* [ ] For 'iOS', select 'Device' -> 'OS' -> 'iOS'
* [ ] For 'Premium plan', select 'Custom'\* -> 'Plan' -> 'Include' -> 'Premium'\
  \***Note**: The custom section stands for additional user traits imported into Redfast to target users based on characteristics beyond site/app usage. You can learn more about importing custom traits from your app [here.](user-traits)
* [ ] For 'users who have not redeemed the iOS prompt', select 'Interactions' -> User 'has not' -> 'accepted (primary)' ->  'iOS popup'. You can select any of your created prompts from the dropdown to establish dependancy on the user's interaction with the prompt.
* [ ] Hit 'Save' to apply settings
* [ ] Hit 'Enable' to set the segment live for the system to start monitoring users with the matching traits set.

Redfast is now configured to receive and process data from your site and allow you to target the users from the defined segment. Allow for a few hours for data to collect metrics and monitor it for the desired date range by clicking in to your saved segment.
