---
title: HYBRID-REST

language_tabs: # must be one of https://git.io/vQNgJ
  - shell
  - javascript

toc_footers:
  - <a href='#'>Sign Up for a Developer Key</a>
  - <a href='https://github.com/lord/slate'>Documentation Powered by Slate</a>

includes:
  - os
  - acl
  - acp
  - ou
  - users
  - admins
  - roles
  - deadlines
  - deadline_category
  - data_security
  - dispose_type
  - public_status
  - security_class
  - errors

search: true
---

# Introduction

Welcome to the Kittn API! You can use our API to access Kittn API endpoints, which can get information on various cats, kittens, and breeds in our database.

We have language bindings in Shell, Ruby, Python, and JavaScript! You can view code examples in the dark area to the right, and you can switch the programming language of the examples with the tabs in the top right.

This example API documentation page was created with [Slate](https://github.com/lord/slate). Feel free to edit it and use it as a base for your own API's documentation.

# Authentification

> To authorize, use this code:

```shell
curl --request POST \
  --url http://127.0.0.1:9002/api/v1/ubit/auth/ \
  --header 'Authorization: Basic c3VwZXJAdXNlci5jaDp1bml0VGVzdDEyMzQ=' \
  --header 'Content-Type: application/json' \
  --header 'cache-control: no-cache' \
  --data '{\n	"access_token":"YfE9ye75tILYVOOzucvXkr2WMkNvhJai"\n}'
```

```javascript
var request = require("request");

var options = { method: 'POST',
  url: 'http://127.0.0.1:9002/api/v1/ubit/auth/',
  headers: 
   { 'cache-control': 'no-cache',
     Authorization: 'Basic c3VwZXJAdXNlci5jaDp1bml0VGVzdDEyMzQ=',
     'Content-Type': 'application/json' },
  body: { access_token: 'YfE9ye75tILYVOOzucvXkr2WMkNvhJai' },
  json: true };

request(options, function (error, response, body) {
  if (error) throw new Error(error);

  console.log(body);
});
````
> Assurez-vous de remplacer 
>
>`c3VwZXJAdXNlci5jaDp1bml0VGVzdDEyMzQ=` par votre nom d'utilisateur et mot de passe, encodé en base 64
>
> `YfE9ye75tILYVOOzucvXkr2WMkNvhJai` par votre Master Key.

Lors de toute requête auprès de l’API, vous devez inclure un Token (Bearer Token) dans l’entête. 
Ce token est généré à l’aide de la requête Auth

Kittn uses API keys to allow access to the API. You can register a new Kittn API key at our [developer portal](http://example.com/developers).

Kittn expects for the API key to be included in all API requests to the server in a header that looks like the following:

`Authorization: meowmeowmeow`

<aside class="notice">
You must replace <code>meowmeowmeow</code> with your personal API key.
</aside>
