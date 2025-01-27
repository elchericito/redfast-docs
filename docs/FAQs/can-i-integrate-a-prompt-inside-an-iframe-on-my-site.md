---
title: Can I integrate a prompt inside an iFrame on my site?
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
In some cases you may need to trigger Redfast from a child iframe. For example, you might have a billing gateway that opens an iframe, but you still want buttons within the iframe to trigger Redfast. Here is an example of what that might look like.

![](https://files.readme.io/09bd1e4-image.png)

Now let’s say that you want to open a popup notifying the user about new content or feature after they click Submit Payment. Today you wouldn’t be able to do this unless the Redfast SDK is also inside of the iframe, which may not be possible or necessary. Below is a lightweight integration which does not require adding the SDK into the iframe.

Integration process\
The integration uses the native browser postMessage API which allows your iframe to communicate with the parent HTML document and trigger a popup or interstitial of your choice.

Find the prompt that you would like to trigger from inside your iframe\
For this usecase, we want the user to book a session with Buff the trainer. Note the ID: 66bc51c0-9829-4c4a-8697-223d0fff860a for this example.

![](https://files.readme.io/32501c2-image.png)

<br />

Now go to your iframe code and add a click handler. It should send a postMessage to the parent iframe\
Our goal is to open a popup to let the user know about a prompt once they have submitted their payment. We can do this by attaching a click handler to the Submit Payment button. We will replace ID\_HERE below with the ID we collected in previous step. The code below will send a message to the parent container and Redfast will be listening for this specific event.

![](https://files.readme.io/c0d9abb-image.png)

<br />

```javascript
<button onclick="postSubmitPayment()">Submit Payment</button>

<script>
  function postSubmitPayment() {
    // parent.postMessage("rf_prompt_ID_HERE", "*");
    parent.postMessage("rf_prompt_66bc51c0-9829-4c4a-8697-223d0fff860a", "*");
  }
</script>
```

What happens next\
Once the Redfast SDK receives the message it will open up the prompt. You can trigger the prompt with the postMessage command as may times as you desire. All interactions such as accept, decline, dismiss continue to behave as they normally do.

multi-site
