---
title: User ID Matching
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
When authenticated users visit your site, a unique identifier (User ID) is typically stored in their browsers. Redfast needs to access this to differentiate between visitors for customizing actions, and for downstream reporting. 

You may need to work with your developers to determine the best method to identify users. The most common methods to retrieve a User ID are from within:

* localStorage item 
* sessionStorage item
* browser cookie
* accessing an item stored in the browser's dataLayer

Please specify the storage location and key in the User ID Matching configuration.

<Image align="center" className="border" border={true} src="https://files.readme.io/997b754b9eca52a38e829bfb135e3a944f21ae3abdcb7736520990b6561e118c-image.png" />

If the resulting value is encoded, please specify how it should be decoded. 

<Image align="center" className="border" border={true} src="https://files.readme.io/a10af0c7a355927ec26e1db6537ebf1727b49ac6d90a2486d9fb6a5b52d4213a-image.png" />

Finally, if the resulting value is a JSON object, specify a path to access the desired property.

<Image align="center" className="border" border={true} src="https://files.readme.io/40644c7db538ade718d1542656d22f4a71f2330860e791905b935daa6ea1c894-image.png" />

Once the form is filled in, scroll down to the bottom and hit the Save button.

![](https://files.readme.io/935237ece01241309498a59cc33773274673fd51a06cf21dee221983a34202ce-image.png)

Please reach out to Redfast Support if you need assistance.

# fetchUserId Examples

While we provide a UI for User ID matching, sometimes you will need to write your own JS function for more complex cases. In this case, select the 'Custom JS Snippet' option in the form, and input the function code under Settings -> Custom JS Snippet. 

Below are some fetchUserId examples to help you configure this function.

For your convenience, we also include a number of helper functions under `RFHelpers` that you can use in the function to solve common use cases. You can view the full source code and docs of the available `RFHelpers` functions [here](https://gist.github.com/peter-redfast/24555da8e489a0278bda2c29f8092f3c).

## Basic Example

This is the most basic and common example when you are using [Twilio Segment](https://segment.com/):

```jsx
static fetchUserId() {
  // Get value from localstorage
  const value = window.localStorage.getItem('ajs_user_id'); // '"user123"'
 
  // Parses JSON if it is parseable 
  return RFHelpers.tryParseJSON(value); // 'user123'
}
```

First, the function gets the stored value of `ajs_user_id` from localStorage (`"user123"`). This value is wrapped in quotations, so to return the actual string, we have to use `JSON.parse()`. 

We then use `RFHelpers.tryParseJSON()` — it does the same as `JSON.parse()` if the value is a JSON string, otherwise, it simply returns the original value instead of an error.

## Cookies and Decoding

In a slightly more complex example, we have a Base64-encoded value stored in a cookie:

```jsx
static fetchUserId() {
  // Get value from cookie
  const value = RFHelpers.getCookie('encoded_user'); // 'dXNlcjEyMw=='
 
  // Decode the value using Base64
  return RFHelpers.decodeBase64(value); // 'user123'
}
```

The document cookie value here might look like `'foo=bar; encoded_user=dXNlcjEyMw==; something=else;'`. As above, instead of writing your own code, we can utilise `RFHelpers.getCookie` to get the cookie value, and then `RFHelpers.decodeBase64` to decode it into a human-recognisable user value.

## Javascript Object Digging

Finally, we have a value stored in global window variable, but it is encoded as a JWT token, and the user ID is deeply nested in a Javascript object:

```jsx
static fetchUserId() {
  // Get the value stored in the global window variable
  const token = window['_JWT_USER_VAR']; 
  // 'eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzdWIiOiIxMjM0NTY3ODkwIiwiaWF0IjoxNTE2MjM5MDIyLCJhdXRoIjoie1widXNlclwiOntcImlkXCI6XCJ1c2VyMTIzXCJ9fSJ9.sucsd6A2vgK6sIhKPqDqHBZ4uUhr5gsI3-C1RANaiQo'
 
  // Decode the value using JWT
  const obj = RFHelpers.decodeJWT(value);
  // {sub: '1234567890', iat: 1516239022, auth: '{"user":{"id":"user123"}}'}
  
  // Get the deeply-nested value
  return RFHelpers.dig(obj, 'auth.user.id'); // 'user123'
}
```

First, the JWT token is retrieved simply from the global window variable. Then, the token is decoded using `RFHelpers.decodeJWT`. This also automatically parses the JSON string into a Javascript object. Finally, to retrieve the actual user value, we use `RFHelpers.dig` to access the deeply-nested value. This helper function works on both Arrays as well as Objects.

## Multiple Fallbacks

Of course, you can combine these to check for multiple possible values or to utilise conditionals:

```jsx
static fetchUserId() {
  if (window.location.pathname.match('/smart-console-apps/') {
    return window.localStorage.getItem('USERID');
  }

  const cookieValue = RFHelpers.getCookie('user');
  if (cookieValue) return cookieValue;
  
  const localValue = window.localStorage.getItem('auth');
  if (localValue) {
    const hash = RFHelpers.decodeJWT(localValue);  
    return RFHelpers.dig(hash, 'auth.id');
   }
}
```