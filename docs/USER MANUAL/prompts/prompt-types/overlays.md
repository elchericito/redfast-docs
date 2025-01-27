---
title: Overlay
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
Overlay prompts appear on top of your site/ application content and may (interstitial, pop-up, video) or may not (notification, bottom banner) block your user's interaction with your site.

<Image align="center" className="border" border={true} src="https://files.readme.io/eb0dc55-image.png" />

## Interstitial

This prompt type typically appears before or after your page content. It occupies all or most of the available real estate on the screen and is defined based on popular device screen height and width aspects.\
Although full page prompts are defined by the device aspect ratios, full screen may not be always available for display or the device may not be exact aspect ratio. To address this, print industry practices can be followed to ensure the main creative is always viewable on the screen. 

![](https://files.readme.io/0ab0f6f-image.png)

## Pop up, Video

These prompts typically hide the page content and occupy most of the available real estate on the screen. They can be utilized to interrupt the user allowing you to meet important objectives.

### Pop Up

A horizontal image with text and one or more calls to action. It is possible to close this messaging type.

Size: 1200px x 800px (large), 960px x 640px (medium), or 750px x 500px (small)  (configurable)

![](https://files.readme.io/d2cb3d2-image.png)

### Video

A video with text and one or more calls to action.

Size: 1100px x 619px (configurable)

![](https://files.readme.io/5b26f7a-image.png)

## Notification

This one here is a subtle prompt on the lower left or lower right of the screen with a single call to action, short headline, and background image.

<Image align="center" className="border" border={true} src="https://files.readme.io/45dbbcc-image.png" />

## Bottom Banner

This prompt is a banner image with text that spans the bottom portion of the screen with variable height.

![](https://files.readme.io/1500b39-image.png)

## How-to-video

Here is a video tutorial that shows how to create a single popup. The instructions for creating interstitial, notification, video prompt are exactly the same.

<Embed url="https://www.loom.com/embed/37d0ba60b71e4444be6ddcfe14e56add?sid=77dddded-5f13-4cd0-899b-9105cde9f286 nJvsnLtmKCrXY4dDsfkpywOr4wmdOyAf" title="iframe" provider="loom.com" href="https://www.loom.com/embed/37d0ba60b71e4444be6ddcfe14e56add?sid=77dddded-5f13-4cd0-899b-9105cde9f286 nJvsnLtmKCrXY4dDsfkpywOr4wmdOyAf" typeOfEmbed="iframe" height="480px" width="100%" iframe="true" />

***

## Step-by-step

* [ ] Go to Prompts > +New Prompt Button
* [ ] Select 'Desktop and Mobile' since we are creating a prompt for the browser. Then select the pop up.
* [ ] Add a name and description (optional)
* [ ] Add one or more segments.\
  Adding the 'Test Users' segment allows you to view the prompt as if you were a targeted user. If you haven't created any segments yet you can just add the 'Test Users' segment.
* [ ] Add a trigger.\
  Adding a trigger allows you to decide where you want to show your prompt. Learn more about triggers [here](triggers).
* [ ] Set a limit (optional).\
  If you have a budget or want to set a limit on how many prompts can be claimed you can do it here. There are multiple types of[ limits](limits-1) you can choose from.
* [ ] Set a schedule (optional).\
  If you want to schedule your prompt to run at a certain time you can do so by clicking [Schedule](schedule-1).
* [ ] Set an action (optional).\
  If you want to redirect a user to a new page/ apply a coupon to their account, etc., after they accept the prompt you can do so by setting up [Actions](actions-1).
* [ ] Select 'Edit prompt design' to design the prompt.
* [ ] Design the prompt.\
  This is where the magic happens. Feel free to tinker with the settings and see your changes live in the preview at the top. If you don't want to change any settings you can leave it as is and click 'Continue'.
* [ ] Once you have saved your changes, you can preview your prompt on your live site.
* [ ] Once you are satisfied with your design, hit 'Save' to apply the changes.  Your prompt has been created and you can set its status to 'Start'. 

### Test the prompt

A prompt can be tested before it is published to all users. These tests are useful for refining triggers, creative, schedules, and actions. You can learn to do so by following the [test user guide](test-users).

### Activate the prompt

Activation of prompts has two phases:

1. **Review phase** - this refers to activating your prompt on an internal segment, generally “Test Users.” You should use this time to QA and perform a final review of your prompt before launching to a broader audience. Adding[ test users](test-users) will allow you to live preview your prompts to make adjustments and changes.

2. **Active phase**  - this refers to deployment at scale to your specified audience. In this phase you should attach all segments to the prompt that you wish to engage with.

Once a prompt is started it can be paused, restarted or ended as long as there is no active experiment. If you have an active experiment it must be ended before you can pause the prompt.