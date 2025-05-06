---
title: Roku
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
The Redfast Roku SDK provides the ability to monitor consumption and show prompts within your native Roku app. The SDK automatically handles the display of the prompt and the associated user trigger events.

## Install the SDK

Download the latest Roku SDK (v1.0.25) with Roku Pay support [here](https://assets.redfastlabs.com/sdk/roku-sdk-1.0.25.zip) and without Roku Pay support [here](https://assets.redfastlabs.com/sdk/roku-sdk-noiap-1.0.25.zip). A demo app featuring an example integration can be provided by request.

To build a project using the RedFast SDK for Roku, your project must have been built with the Scenegraph SDK.\
Unzip the SDK into the app `components` directory.

## Initialize SDK

1. Initialize the SDK within the main scene XML (initial screen) file.

```
 < PromotionManager id="promoMgr" />
```

2. Within the main scene BrightScript (.brs) file, add the following lines into the `sub init()` function and specify the values for the appId and userId. The userId may be changed later on.

```
sub init()
  // other app initialization code
  m.promoMgr = m.top.findNode("promoMgr")
  m.promoMgr.observeField("result", "onInitialized")
  m.promoMgr.callFunc("initPromotion", {appId: "[YOUR APP ID]", userId: "[USER ID]"})
end sub
// ...
sub onInitialized()
  m.promoMgr.unobserveField("result")
  m.sceneStack = m.top.findNode("sceneStack")
  scene = createObject("RoSGNode", "[YOUR FIRST SCREEN OF THE APP]")
  m.sceneStack.appendChild(scene)
end sub
```

Note that it may take a few seconds after app start for the SDK initialization to complete, after which prompts will be available to present to the user.

Obtain the Promotion Manager instance. In the `sub init()` function, add the following code:

```
sub init()
  // ...
  m.promoMgr = m.top.GetScene().findNode("promoMgr")
  // ...
end sub
```

## Set UserId

You may change the userId after the SDK has been initialized. The function will return instantly, however all prompts relevant to the updated userId may take a few seconds to be ready.

```
m.promoMgr.callFunc("setUserId", {userId: "[new user id]"})
```

## Trigger Popup via Screen Name

Allow the Redfast SDK to display a popup on the specified screen. If the prompt also requires a button click, the trigger will not occur until the associated `onButtonClicked` function is called.

Add the following line in the screen init function:

```
sub init()
  ...
  m.promoMgr = m.top.GetScene().findNode("promoMgr")
  // Make sure a callback function is registed (and registed for only once) here to receive any status from m.promoMgr
  // A sample onPromotionEvent is provided in the next section
  m.promoMgr.observeField("result", "onPromotionEvent")
  m.promoMgr.callFunc("onScreenChanged", {root: m.viewRoot, screenName: "ViewController" })
  ...
end sub
```

Ensure that you add an event listener before calling any function on `m.promoMgr` so that you can observe the result from a screen change, button click, popup and inline item:

```
  m.promoMgr.observeField("result", "onPromotionEvent")
```

## Trigger Popup via Button Click

The sample code below demonstrates:

1. Tracking a button click event
2. Displaying a popup if applicable to the button.

Note that a previous `onScreenChanged` call is required if the prompt trigger is configured to be invoked only when the button click occurs on a specified screen name.

```
sub onButtonClicked()
  m.promoMgr.callFunc("onButtonClicked", {root: m.viewRoot 'the root component of the screen, id: "[Optional button ID]"}) 
end sub
                                          
'Note: If the prompt is displayed and dismissed, the result will be passed back to:
sub onModalDismissed()
  if m.promoMgr.result.value = 101 'button1
    dialog = createObject("roSGNode", "Dialog")
    dialog.title = "Thank you"
    dialog.optionsDialog = true
    dialog.message = "Thanks for accepting"
    m.top.dialog = dialog
  end if
end sub

// Note: The full set of status codes can be found in the SDK `const.brs` file:
' Success codes
m.ok = 1

' Error codes
m.error = -100
m.notApplicable = -101
m.disabled = -102
m.suppressed = -103

' Interactions
m.impression = 100
m.button1 = 101
m.button2 = 102
m.button3 = 103
m.dismissed = 110
m.timerExpired = 111
m.holdout = 120

```

## Retrieve Inline Prompts

The SDK provides a method to retrieve inline prompts within the specified Zone ID that are eligible for the current userId. You may access the properties of the inline prompts to render in the appropriate locations within the app.

```
inlineItems = m.promoMgr.callFunc("getInlines", {type: "myZoneId"})
```

The following is example code demonstrating accessing attributes of the prompt for rendering. A full list of attributes can be found [here](/reference/prompt-attributes#/).

```
featured = createObject("RoSGNode", "ContentNode")
di = CreateObject("roDeviceInfo")
displaySize = di.GetDisplaySize()
for ii = 0 To inlineItems.count() - 1
    item = featured.createChild("ContentNode")
    inlineItem = inlineItems[ii]
    heightSuffix = ""
    if displaySize.h = 480
        heightSuffix = "&screen_size=480"
    else if displaySize.h = 720
        heightSuffix = "&screen_size=720"
    end if
    item.HDPOSTERURL = inlineItem.actions.rf_settings_bg_image_roku_os_tv_composite + heightSuffix
    item.Title = inlineItem.actions.rf_retention_title
    item.Message = inlineItem.actions.rf_retention_message
    item.Description = inlineItem.actions.rf_settings_roku_product_operation
    item.ButtonText = inlineItem.actions.rf_retention_confirm_button_text
end for
featured.title = "Featured"
contentNode.insertChild(featured, 2)
```

## Send Usage Tracking Event

Your app can report custom tracker events through the SDK. If configured as a tracker within Pulse, these custom events can be used to target prompts at specific sets of users. The custom tracker must first be created within the Redfast console so that the `customFieldId` value may be retrieved.

```
m.promoMgr.callFunc("customTrack", {customFieldId: "my-usage-event"})
```

## Deep Link to a Media Asset

Invoke the Roku app [deep linking](https://developer.roku.com/docs/developer-program/discovery/implementing-deep-linking.md) functionality by specifying the mediaType and contentId for the prompt in the Redfast console. When the user invokes the CTA on the prompt, you may utilize these parameters to send the user to a specific media asset within the app. The following is an example on how to invoke deep linking after the user invokes the call to action.

```
sub onPromotionEvent()
  if m.promoMgr.result.value = 0 // m.accepted from `const.brs` file
    deeplink = m.promoMgr.result.extra.deeplink
    [your deeplink handler function](deeplink)
  end if
end sub
```

## Access Device Metadata

Device key-value pair metadata can be added to an Prompt via the Redfast console. The app will receive these values per the examples below. These values may be used to perform an action that is not the typical media asset deep link, like sending the user to a registration screen.

### Popup

When a popup is dismissed by either an Accept, Decline, or Timeout action by the user, the custom metadata will be saved in the `extra.meta` field.

```
sub onPromotionEvent()
  metadata = m.promoMgr.result.extra.meta
end sub
```

### Inline Item

When the `onInlineClicked` API is invoked with the current selected inline item:

```
sub onPromotionEvent()
  metadata = m.promoMgr.result.extra.meta
end sub
```

## Disable SDK

There may be cases in which the Redfast SDK should be temporarily disabled for the current session. When disabled, popups are not triggered, and API communication between the SDK and Redfast servers are paused.

```
// To disable
m.promoMgr.callFunc("enablePromotion", {enabled: false})

// To re-enable
m.promoMgr.callFunc("enablePromotion", {enabled: true})
```

## Debug View

The SDK provides a debug view modal in which you can use the onscreen keyboard to either reset all prompts for the current user or set a new userId.

To trigger the debug view for a specific screen, add the `DebugView` component and connect it to a local variable on the screen,

```
<DebugView id="debugView" />

m.debugView = m.top.findNode("debugView")
```

In the screen's `onKeyEvent` function:

```
m.debugView.callFunc("onKeyDetection", {key: key, screen: m.top})
```

When the `*` key on the remote control is pressed, the debug view will be displayed.