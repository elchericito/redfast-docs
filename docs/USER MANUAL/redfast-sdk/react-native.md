---
title: React Native
deprecated: false
hidden: true
metadata:
  robots: index
---
The Redfast React Native SDK provides the ability to render Redfast configured prompts within your React Native apps. The SDK automatically handles display of modals (popups, bottom banners, mobile interstitials) and the related user interaction events. Inline prompts can be rendered using a prebuilt view.

## Install the SDK

Add the following to your `.npmrc` or `.yarnrc.yml` file. Contact your Customer Success Manager for the AUTHTOKEN.

```
# .npmrc
@redfast:registry=https://npm.pkg.github.com
//npm.pkg.github.com/:_authToken=AUTHTOKEN

# .yarnyc.yml
npmAuthToken: "AUTHTOKEN"
```

### Install the package

Using npm

```shell
npm install @redfast/redfast-core
npm install @redfast/react-native-redfast
```

or yarn

```shell
yarn add @redfast/redfast-core
yarn add @redfast/react-native-redfast
```

## Initialize Redfast

Initialize the SDK in your AppRoot.

```javascript
// Initialize the SDK, polling until init is complete
React.useEffect(() => {
  if (dispatch) {
    const promptMgr = new PromptManager(
      'YOUR_APP_ID',
      'INITIAL_USER_ID'
    );
    const intervalId = setInterval(() => {
      if (promptMgr.isInitialized()) {
        dispatch({
          type: PromptAction_Init,
          data: promptMgr,
        });
        setReady(true);
        clearInterval(intervalId);
      }
    }, 1000);
    return () => clearInterval(intervalId);
  }
  return () => {};
}, [dispatch]);
```

## Set UserId

You may change the userID after the SDK has been initialized, for example, when the user authenticates mid session. Note that it may take several seconds for the user's prompts to refresh.

```javascript
promptMgr.setUserId(userId)
```

## Trigger Modals

Interstitial (mobile only), Popup and Bottom Banner modals may be triggered upon entering a screen and/or the user registering a click on an element. Add the following code to screens that are eligible to show a modal.

```javascript
// Import from Redfast SDK
import {
  usePrompt,
  displayPrompt, // Modal prompts
  RedfastInline, // Inline prompts
} from '@redfast/react-native-redfast';

// Trigger when entering the "home" screen
const { path, delaySeconds } = await promptMgr.onScreenChanged("home");
if (path) {
  setTimeout(() => {
    setPathItem(path);
    setShowModal(true);
  }, delaySeconds);
}

// Or, trigger when "clickId" is clicked
const { path, delaySeconds } = await promptMgr.onButtonClicked("clickId");
if (path) {
  setTimeout(() => {
    setPathItem(path);
    setShowModal(true);
  }, delaySeconds);
}

// Display the UI for the path object returned above.
// params:
//   - showModal: a boolean to stipulate showing or hiding a Prompt
//   - path: a path object retruned from one of the trigger calls above
//   - result: a callback to return the result of how a user interacts with a Redfast Prompt
displayPrompt(showModal, path, (result) => {
  console.log(JSON.stringify({ ...result, source: 'modal' }, null, 2));
  setShowModal(false);
})

// Data schema of the result callback
interface PromptResult {
  code: PromptResultCode;
  value?: { [key: string]: any };
  meta?: { [key: string]: any };
}
```

## Render Inline Prompts

You may utilize the `RedfastInline` view to render an inline prompt, if one is available for the current user. Note the inline prompt will scale to fit within its container.

```javascript
<RedfastInline
  zoneId="myZoneId" // ZoneID as specified in Pulse
  closeButtonColor="#000000" // Hex color for close button, if enabled
  closeButtonBgColor="#FFFFFF" // Hex background color for close button
  closeButtonSize="20" // Close button height and width, in pixels
  timerFontSize="14" // Countdown timer font size, if enabled
  timerFontColor="#FFFFFF" // Countdown timer font hex color
  onEvent={(result) =>}
/>

```

## Actions

The following can be utilized to perform client-side actions when the main prompt CTA is selected.

### Deeplink

You can insert deeplink key-value pairs in Pulse. When the user invokes the CTA, you can utilize these key-value pairs to send the user to a specific media asset within the app.

TODO: Code example

### In-App Purchase

An In-App Purchase product SKU may be configured on the prompt, which indicates that the user should be sent to the In-App Purchase flow for the specified SKU  once the primary CTA has been selected.

TODO: Code example

### Custom Metadata

Custom key-value pairs can be added to an item via Pulse. These values may be used to perform an action that is not the typical media asset deep link, like sending the user to a registration screen or performing an operation on behalf of the user.

TODO: Code example

## Send Usage Tracking Event

Your app can send custom track events using the SDK. If configured as a tracker within Pulse, these custom events can be used to target prompts at specific sets of users.

```javascript
promptMgr.customTrack(customFieldId)
```

## Debugging

You may reset the current user's prompt status, such that previously suppressed prompts will now be made available.

```javascript
promptMgr.resetGoal()
```