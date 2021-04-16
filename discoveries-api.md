# API docs

Make sure to read the developer terms of service, you'll also need to have followed the steps to create an application at dev.liamassistant.com

# API endpoint

https://devapi.liamassistant.com

# Authenticating with the API

You'll need to add your clientid and secret in your JSON body in every request. As shown here:

```
fetch('https://devapi.liamassistant.com/[the-directory-you-want-to-send-a-request-too]', {
      method: 'POST',
      headers: {
        'Content-Type':'application/json',
        'Content-Length': `2`,
        'Host':'192.168.2.229',
      },
      body: `{"clientid":"supercoolclientid", "secret"wowsupercoolsecret"}`
    })
    .then(response => response.json())
    .then(async response => {
      // super cool response goes here;.
    });
```

**if you're keys are invalid. The API will return ```{"error":"true", "code":"invalid_keys"}```**

# Programically setting an endpoint

Requests to your API will to your specified endpoint. You can set it by sending a request like this:

``` 
Endpoint: devapi.liamassistant.com/endpoint/edit
body: {"clientid":"", "secret":"", "endpoint":"https://example.com"}
```

# Sending notifications to a user

``` 
Endpoint: devapi.liamassistant.com/notifications/send
body: {"clientid":"", "secret":"", "title":"", "message":"", "image":""}
```

# Adding item to a users feed

you can use:

```
Title: To set the title of the feed object.
message: If you would like the feed to be a simple message, use this, otherwise, you can use the ``itemData`` option as described below.
Color: You can leave this as a single hex if you want, otherwise, you can have multiple hexs in an array for a linear gradient.
Image: This will be shown at the edge of the item.
background-image: You can set a background image for the item.
size: Set the type of size you would like your item to be, the types are ``Small, kinda-medium, medium, kinda-large, large``.
React-native or React parameters!! If you want, you can get React-Native or React render code, it has to be with what is specific under #Render-Code in the documentation, however this is a very cool feature, obviously, you can't run JS or Typescript code for security reasons, but this render is very powerful (Your render code will need to be approved).
itemData: Let's take a weather feed item for example, you might want to show something like this (shown below). This can be down via the itemData option, it's mostly the same paramaters.
```
```
Today's weather

Monday: sunny
Tuesday: sunny
Wednesday: sunny
```

Below is a full request with all the options.
```
Endpoint: devapi.liamassistant.com/feed/add
body: {"clientid":"", "secret":"", "title":"Very important notification", "message":"wowwwww", color:["#000000", "#FFFFFF"], "image":"", "background-image":"", "size":"kinda-medium", "itemData":[{"title":"Monday", "subtext":"Sunny"}]}
```

# Programically update your discoveries details.

``Type``: can be set as ``name, bio, image, banner, commands (commands must be in a JSON-ARRAY)``

```
Endpoint: devapi.liamassistant.com/details/edit
body: {"clientid":"", "secret":"", "type":"bio", "content":"wow cool discovery!"}
```

## Recieve Liam queries

This request will be sent to your endpoint, from there, you'll need to send a response that we can display to the user (more on that later). You can get our-clientid and our-secret from your developer portal to validate our requests!

 ```
 Type: POST
 Body: {"our-clientid":"". "our-secret":"", "message":""}
 ```
 
 ## Respond to Liam queries
 
 ``This is pending....``
 
 
