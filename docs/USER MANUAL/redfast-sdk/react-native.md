---
title: React Native
deprecated: false
hidden: true
metadata:
  robots: index
---
The Redfast React Native SDK provides the ability to render Redfast configured prompts within your React Native apps. The SDK automatically handles display of modals (popups, bottom banners, mobile interstitials) and the related user interaction events. Inline prompts can be rendered using a prebuilt view.

## Install the SDK

Add the following to your .npmrc file. Contact your Customer Success Manager for the AUTHTOKEN.

```
@redfast:registry=https://npm.pkg.github.com
//npm.pkg.github.com/:_authToken=AUTHTOKEN
```

Install the package

```shell
npm install @redfast/react-native-redfast
```

Add the SDK dependency to your package.json

```json
  "dependencies": {
    "@redfast/react-native-redfast": "^1.0.0"
  }
```

<br />

## Initialize Redfast

Initialize the SDK in your AppRoot.

```javascript
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

<br />

## Set UserId

## Trigger Modals

## Render Inline Prompts

## Actions

### Deeplink

### In-App Purchase

### Custom Metadata

## Send Usage Tracking Event