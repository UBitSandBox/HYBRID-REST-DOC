---
title: HYBRID-REST

language_tabs: # must be one of https://git.io/vQNgJ
  - shell
  - javascript

toc_footers:
  - <a href='#'>Sign Up for a Developer Key</a>
  - <a href='https://github.com/lord/slate'>Documentation Powered by Slate</a>

includes:
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

# ACL
## Object

Name | Type | Description
--------- | ----------- | -----------
ID | string | Id of the ACL
ACLNAME | string | German name of the ACL
ACLNAME_F | string | French name of the ACL
ACLNAME_I | string | Italian name of the ACL
ACLNAME_E | string | English name of the ACL
ACLDEF | string | TODO
ACLDEF_CLOSED | string | TODO
ACL_ON_CREATION | boolean | TODO
REMOVE_ADDEDRIGHTS | boolean | TODO 


## Get All ACL
```shell
curl --request GET \
  --url http://127.0.0.1:9002/api/v1/ubit/acl \
  --header "Authorization: Bearer {ACCESS_TOKEN}" \
  --header 'cache-control: no-cache'
```

```javascript
var request = require("request");

var options = { method: 'GET',
  url: 'http://127.0.0.1:9002/api/v1/ubit/acl',
  headers: 
   { 'Authorization': 'Bearer {ACCESS_TOKEN}',
     'cache-control': 'no-cache' } };

request(options, function (error, response, body) {
  if (error) throw new Error(error);

  console.log(body);
});
```

>You must replace `{ACCESS_TOKEN}` with your personal token.

> The above command returns JSON structured like this:

```json
[
    {
        "id": 1,
        "aclName": "Offen",
        "aclNameF": "Ouvert",
        "aclNameI": null,
        "aclNameE": null,
        "aclDef": "ALL[U:MODIFY]",
        "aclDefClosed": "ALL[U:READ]",
        "aclOnCreation": true,
        "removeAdditionalRights": false
    },
    {
        "id": 2,
        "aclName": "LEITER",
        "aclNameF": "RESPONSABLE",
        "aclNameI": null,
        "aclNameE": null,
        "aclDef": "THIS[L:MODIFY]",
        "aclDefClosed": "THIS[L:READ]",
        "aclOnCreation": true,
        "removeAdditionalRights": false
    }
]
```

This endpoint retrieves all ACL.

### HTTP Request

`GET http://127.0.0.1:9002/api/v1/ubit/acl`

<aside class="success">
Remember — you must be authenticated !
</aside>

## Get ACL by its ID

```shell
curl --request GET \
  --url http://127.0.0.1:9002/api/v1/ubit/acl/1 \
  --header 'Authorization: Bearer {ACCESS_TOKEN}' \
  --header 'Connection: keep-alive' \
  --header 'Host: 127.0.0.1:9002' \
  --header 'cache-control: no-cache'
```

```javascript
var request = require("request");

var options = { method: 'GET',
  url: 'http://127.0.0.1:9002/api/v1/ubit/acl/1',
  headers: 
   { 'cache-control': 'no-cache',
     Connection: 'keep-alive',
     Host: '127.0.0.1:9002',
     Authorization: 'Bearer {ACCESS_TOKEN}' } };

request(options, function (error, response, body) {
  if (error) throw new Error(error);

  console.log(body);
});
```

>You must replace `{ACCESS_TOKEN}` with your personal token.

> The above command returns JSON structured like this:

```json
{
    "id": 1,
    "aclName": "Offen",
    "aclNameF": "Ouvert",
    "aclNameI": null,
    "aclNameE": null,
    "aclDef": "ALL[U:MODIFY]",
    "aclDefClosed": "ALL[U:READ]",
    "aclOnCreation": true,
    "removeAdditionalRights": false
}
```

This endpoint retrieves a specific ACL.

### HTTP Request

`GET http://127.0.0.1:9002/api/v1/ubit/acl/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the ACL to retrieve

<aside class="success">
Remember — you must be authenticated !
</aside>

## Create an ACL
```shell
curl --request POST \
  --url http://127.0.0.1:9002/api/v1/ubit/acl/ \
  --header 'Authorization: Bearer {ACCESS_TOKEN}' \
  --header 'Connection: keep-alive' \
  --header 'Host: 127.0.0.1:9002' \
  --header 'cache-control: no-cache'
  --data '{"aclName": "Offen","aclNameF": "Ouvert","aclNameI": "Aperto","aclNameE": "Open","aclDef": "ALL[U:MODIFY]","aclDefClosed": "ALL[U:READ]","aclOnCreation": true,"removeAdditionalRights": false}'
```

```javascript
```

>You must replace `{ACCESS_TOKEN}` with your personal token.

This endpoint create an ACL.

### HTTP Request

`POST http://127.0.0.1:9002/api/v1/ubit/acl/`

### Body Parameters

Parameter | Type | Description
--------- | ----------- | -----------
ACLNAME *  | string | The german name of the ACL (3 to 255 characters)
ACLNAME_F | string | The french name of the ACL (3 to 255 characters)
ACLNAME_I | string | The italian name of the ACL (3 to 255 characters)
ACLNAME_E | string | The english name of the ACL (3 to 255 characters)
ACLDEF  * | string | TODO
ACLDEF_CLOSED  * | string | TODO
ACL_ON_CREATION * | boolean | TODO
REMOVE_ADDEDRIGHTS * | boolean | TODO

<aside class="notice">
Parameters marked with an asterisk (*) are mandatory.
</aside>

<aside class="success">
Remember — you must be authenticated !
</aside>

## Update an ACL

## Delete an ACL
