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

# OS
## Object
Name | Type | Description
--------- | ----------- | -----------

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


## Get all ACL
```shell
curl --request GET \
  --url http://127.0.0.1:9002/api/v1/ubit/acl \
  --header "Authorization: Bearer {ACCESS_TOKEN}"
```

```javascript
var request = require("request");

var options = { method: 'GET',
  url: 'http://127.0.0.1:9002/api/v1/ubit/acl',
  headers: { 'Authorization': 'Bearer {ACCESS_TOKEN}'} 
};

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
  --header 'Authorization: Bearer {ACCESS_TOKEN}'
```

```javascript
var request = require("request");

var options = { method: 'GET',
  url: 'http://127.0.0.1:9002/api/v1/ubit/acl/1',
  headers: { Authorization: 'Bearer {ACCESS_TOKEN}' } 
};

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
  --data '{"aclName": "Offen","aclDef": "ALL[U:MODIFY]","aclDefClosed": "ALL[U:READ]","aclOnCreation": true,"removeAdditionalRights": false}'
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
```shell
curl --request PUT \
  --url http://127.0.0.1:9002/api/v1/ubit/acl/1 \
  --header 'Authorization: Bearer {ACCESS_TOKEN}' \
  --data '{"aclNameF": "Ouvert","aclNameI": "Aperto","aclNameE": "Open"}'
```

```javascript
```

>You must replace `{ACCESS_TOKEN}` with your personal token.

This endpoint update an ACL.

### HTTP Request
`PUT http://127.0.0.1:9002/api/v1/ubit/acl/<ID>`

### URL Parameters
Parameter | Description
--------- | -----------
ID | The ID of the ACL to update

### Body Parameters
Parameter | Type | Description
--------- | ----------- | -----------
ACLNAME  | string | The german name of the ACL (3 to 255 characters)
ACLNAME_F | string | The french name of the ACL (3 to 255 characters)
ACLNAME_I | string | The italian name of the ACL (3 to 255 characters)
ACLNAME_E | string | The english name of the ACL (3 to 255 characters)
ACLDEF | string | TODO
ACLDEF_CLOSED | string | TODO
ACL_ON_CREATION | boolean | TODO
REMOVE_ADDEDRIGHTS | boolean | TODO

<aside class="success">
Remember — you must be authenticated !
</aside>

## Delete an ACL
```shell
curl --request DELETE \
  --url http://127.0.0.1:9002/api/v1/ubit/acl/1 \
  --header 'Authorization: Bearer {ACCESS_TOKEN}'
```

```javascript
```
>You must replace `{ACCESS_TOKEN}` with your personal token.

This endpoint delete an ACL.

### HTTP Request
`DELETE http://127.0.0.1:9002/api/v1/ubit/acl/<ID>`

### URL Parameters
Parameter | Description
--------- | -----------
ID | The ID of the ACL to delete

<aside class="success">
Remember — you must be authenticated !
</aside>

# ACP
## Object
Name | Type | Description
--------- | ----------- | -----------

# OU
## Object
Name | Type | Description
--------- | ----------- | -----------

# Users
## Object
Name | Type | Description
--------- | ----------- | -----------

# Admins
## Object
Name | Type | Description
--------- | ----------- | -----------

# Roles
## Object
Name | Type | Description
--------- | ----------- | -----------

# Archive/Deadlines
## Object
Name | Type | Description
--------- | ----------- | -----------
ID | integer | Id of the deadlines
TITLE | string | German title of the deadlines
TITLE_F | string | French title of the deadlines
TITLE_I | string | Italian title of the deadlines
TITLE_E | string | English title of the deadlines

## Get all deadlines

```shell
curl --request GET \
  --url http://127.0.0.1:9002/api/v1/ubit/archive/deadlines \
  --header 'Authorization: Bearer {ACCESS_TOKEN}'
```

```javascript
```

>You must replace `{ACCESS_TOKEN}` with your personal token.

>The above command returns JSON structured like this:

```json
[
    {
        "id": 1,
        "title": "1 Jahr",
        "titleF": "1 An",
        "titleI": "1 Anno",
        "titleE": "1 Year"
    },
    {
        "id": 3,
        "title": "3 Jahre",
        "titleF": "3 Ans",
        "titleI": "3 Anni",
        "titleE": "3 Years"
    }
]
```

This endpoint retrieves all deadlines.

### HTTP Request

`GET http://127.0.0.1:9002/api/v1/ubit/archive/deadlines`

<aside class="success">
Remember — you must be authenticated !
</aside>

## Get deadline by its ID

```shell
curl --request GET \
  --url http://127.0.0.1:9002/api/v1/ubit/archive/deadlines/1 \
  --header 'Authorization: Bearer {ACCESS_TOKEN}'
```

```javascript
```

>You must replace `{ACCESS_TOKEN}` with your personal token.

> The above command returns JSON structured like this:

```json
{
    "id": 1,
    "title": "1 Jahr",
    "titleF": "1 An",
    "titleI": "1 Anno",
    "titleE": "1 Year"
}
```

This endpoint retrieves a specific deadline.

### HTTP Request
`GET http://127.0.0.1:9002/api/v1/ubit/archive/deadlines/<ID>`

### URL Parameters
Parameter | Description
--------- | -----------
ID | The ID of the deadline to retrieve

<aside class="success">
Remember — you must be authenticated !
</aside>

## Create a deadline
```shell
curl --request POST \
  --url http://127.0.0.1:9002/api/v1/ubit/archive/deadlines/ \
  --header 'Authorization: Bearer {ACCESS_TOKEN}' \
  --data '{"id": 5,"title": "5 Jahre"}'
```

```javascript
```

>You must replace `{ACCESS_TOKEN}` with your personal token.

This endpoint create a deadline.

### HTTP Request
`POST http://127.0.0.1:9002/api/v1/ubit/archive/deadlines/`

### Body Parameters
Parameter | Type | Description
--------- | ----------- | -----------
ID * | integer | Id of the deadlines
TITLE * | string | German title of the deadlines
TITLE_F | string | French title of the deadlines
TITLE_I | string | Italian title of the deadlines
TITLE_E | string | English title of the deadlines

<aside class="notice">
Parameters marked with an asterisk (*) are mandatory.
</aside>

<aside class="success">
Remember — you must be authenticated !
</aside>

## Update a deadline
```shell
curl --request PUT \
  --url http://127.0.0.1:9002/api/v1/ubit/archive/deadlines/1 \
  --header 'Authorization: Bearer {ACCESS_TOKEN}' \
  --data '{"titleF": "5 Ans","titleI": "5 Anni","titleE": "5 Years"}'
```

```javascript
```

>You must replace `{ACCESS_TOKEN}` with your personal token.

This endpoint update a deadline.

### HTTP Request
`PUT http://127.0.0.1:9002/api/v1/ubit/archive/deadlines/<ID>`

### URL Parameters
Parameter | Description
--------- | -----------
ID | The ID of the deadline to update

### Body Parameters
Parameter | Type | Description
--------- | ----------- | -----------
ID | integer | Id of the deadlines
TITLE | string | German title of the deadlines
TITLE_F | string | French title of the deadlines
TITLE_I | string | Italian title of the deadlines
TITLE_E | string | English title of the deadlines

<aside class="success">
Remember — you must be authenticated !
</aside>

## Delete a deadline
```shell
curl --request DELETE \
  --url http://127.0.0.1:9002/api/v1/ubit/archive/deadlines/1 \
  --header 'Authorization: Bearer {ACCESS_TOKEN}'
```

```javascript
```
>You must replace `{ACCESS_TOKEN}` with your personal token.

This endpoint delete a deadline.

### HTTP Request
`DELETE http://127.0.0.1:9002/api/v1/ubit/archive/deadlines/<ID>`

### URL Parameters
Parameter | Description
--------- | -----------
ID | The ID of the deadline to delete

<aside class="success">
Remember — you must be authenticated !
</aside>


# Archive/Deadline category
## Object
Name | Type | Description
--------- | ----------- | -----------
ID | integer | Id of the deadline category
TITLE | string | German title of the deadline category
TITLE_F | string | French title of the deadline category
TITLE_I | string | Italian title of the deadline category
TITLE_E | string | English title of the deadline category
DESC | string | German description of the deadline category
DESC_F | string | French description of the deadline category
DESC_I | string | Italian description of the deadline category
DESC_E | string | English description of the deadline category

## Get all deadline category

```shell
curl --request GET \
  --url http://127.0.0.1:9002/api/v1/ubit/archive/deadline_categories \
  --header 'Authorization: Bearer {ACCESS_TOKEN}'
```

```javascript
```

>You must replace `{ACCESS_TOKEN}` with your personal token.

>The above command returns JSON structured like this:

```json
[
    {
        "id": 1,
        "title": "Art. 9. Abs. 1 [BGA]",
        "titleF": "Art. 9, al. 1 [LAr]",
        "titleI": "Art. 9. cpv. 1 [LAr]",
        "titleE": "Art. 9. Abs. 1 [BGA]",
        "desc": "Das Archivgut des Bundes...",
        "descF": "Les archives de la Confédération...",
        "descI": "Gli archivi della Confederazione...",
        "descE": "The archive records of the Confederation..."
    },
    {
        "id":2,
        "title":"Art. 9. Abs. 2 [BGA]",
        "titleF":"Art. 9, al. 2 [LAr]",
        "titleI":"Art. 9. cpv. 2 [LAr]",
        "titleE":"Art. 9. Abs. 2 [BGA]",
        "desc":"Unterlagen, welche bereits vor ihrer Ablieferung an das Bundesarchiv öffentlich zugänglich waren, bleiben auch weiterhin öffentlich zugänglich.",
        "descF":"Les documents consultables par le public avant d'être versés aux Archives fédérales le restent par la suite.",
        "descI":"I documenti che erano accessibili al pubblico già prima del loro versamento all'Archivio federale lo restano anche in seguito.",
        "descE":"Documents that were accessible to the public before their delivery to the Federal Archives remain accessible to the public."
    }
]
```

This endpoint retrieves all deadline category.

### HTTP Request

`GET http://127.0.0.1:9002/api/v1/ubit/archive/deadline_categories`

<aside class="success">
Remember — you must be authenticated !
</aside>

## Get deadline category by its ID

```shell
curl --request GET \
  --url http://127.0.0.1:9002/api/v1/ubit/archive/deadline_categories/1 \
  --header 'Authorization: Bearer {ACCESS_TOKEN}'
```

```javascript
```

>You must replace `{ACCESS_TOKEN}` with your personal token.

> The above command returns JSON structured like this:

```json
{
    "id": 1,
    "title": "Art. 9. Abs. 1 [BGA]",
    "titleF": "Art. 9, al. 1 [LAr]",
    "titleI": "Art. 9. cpv. 1 [LAr]",
    "titleE": "Art. 9. Abs. 1 [BGA]",
    "desc": "Das Archivgut des Bundes...",
    "descF": "Les archives de la Confédération...",
    "descI": "Gli archivi della Confederazione...",
    "descE": "The archive records of the Confederation..."
}
```

This endpoint retrieves a specific deadline category.

### HTTP Request
`GET http://127.0.0.1:9002/api/v1/ubit/archive/deadline_categories/<ID>`

### URL Parameters
Parameter | Description
--------- | -----------
ID | The ID of the deadline category to retrieve

<aside class="success">
Remember — you must be authenticated !
</aside>

## Create a deadline category
```shell
curl --request POST \
  --url http://127.0.0.1:9002/api/v1/ubit/archive/deadline_categories/ \
  --header 'Authorization: Bearer {ACCESS_TOKEN}' \
  --data '{"title": "Art. 11. Abs. 1 [BGA]", "desc": "Archivgut, das nach Personennamen erschlossen ist und besonders schützenswerte Personendaten oder Persönlichkeitsprofile enthält, unterliegt einer Schutzfrist von 50 Jahren, es sei denn, die betroffene Person habe einer Einsichtnahme zugestimmt"}'
```

```javascript
```

>You must replace `{ACCESS_TOKEN}` with your personal token.

This endpoint create a deadline category.

### HTTP Request
`POST http://127.0.0.1:9002/api/v1/ubit/archive/deadline_categories/`

### Body Parameters
Parameter | Type | Description
--------- | ----------- | -----------
TITLE * | string | German title of the deadline category
TITLE_F | string | French title of the deadline category
TITLE_I | string | Italian title of the deadline category
TITLE_E | string | English title of the deadline category
DESC * | string | German description of the deadline category
DESC_F | string | French description of the deadline category
DESC_I | string | Italian description of the deadline category
DESC_E | string | English description of the deadline category

<aside class="notice">
Parameters marked with an asterisk (*) are mandatory.
</aside>

<aside class="success">
Remember — you must be authenticated !
</aside>

## Update a deadline category
```shell
curl --request PUT \
  --url http://127.0.0.1:9002/api/v1/ubit/archive/deadline_categories/1 \
  --header 'Authorization: Bearer {ACCESS_TOKEN}' \
  --data '{"titleF": "Art. 11, al. 1 [LAr]","descF": "Les archives classées selon des noms de personnes et contenant des données personnelles sensibles ou des profils de la personnalité sont soumises à un délai de protection de 50 ans à moins que la personne concernée n'en ait autorisé la consultation."}'
```

```javascript
```

>You must replace `{ACCESS_TOKEN}` with your personal token.

This endpoint update a deadline category.

### HTTP Request
`PUT http://127.0.0.1:9002/api/v1/ubit/archive/deadline_categories/<ID>`

### URL Parameters
Parameter | Description
--------- | -----------
ID | The ID of the deadline category to update

### Body Parameters
Parameter | Type | Description
--------- | ----------- | -----------
TITLE | string | German title of the deadline category
TITLE_F | string | French title of the deadline category
TITLE_I | string | Italian title of the deadline category
TITLE_E | string | English title of the deadline category
DESC | string | German description of the deadline category
DESC_F | string | French description of the deadline category
DESC_I | string | Italian description of the deadline category
DESC_E | string | English description of the deadline category

<aside class="success">
Remember — you must be authenticated !
</aside>

## Delete a deadline category
```shell
curl --request DELETE \
  --url http://127.0.0.1:9002/api/v1/ubit/archive/deadline_categories/1 \
  --header 'Authorization: Bearer {ACCESS_TOKEN}'
```

```javascript
```
>You must replace `{ACCESS_TOKEN}` with your personal token.

This endpoint delete a deadline category.

### HTTP Request
`DELETE http://127.0.0.1:9002/api/v1/ubit/archive/deadline_categories/<ID>`

### URL Parameters
Parameter | Description
--------- | -----------
ID | The ID of the deadline category to delete

<aside class="success">
Remember — you must be authenticated !
</aside>

# Archive/Data security
## Object
Name | Type | Description
--------- | ----------- | -----------
ID | integer | Id of the data security
TITLE | string | German title of the data security
TITLE_F | string | French title of the data security
TITLE_I | string | Italian title of the data security
TITLE_E | string | English title of the data security

## Get all data security
```shell
curl --request GET \
  --url http://127.0.0.1:9002/api/v1/ubit/archive/data_securities \
  --header 'Authorization: Bearer {ACCESS_TOKEN}'
```

```javascript
```

>You must replace `{ACCESS_TOKEN}` with your personal token.

>The above command returns JSON structured like this:

```json
[
    {
        "id": 1,
        "title": "Keine Personendaten",
        "titleF": "Pas de données personnelles",
        "titleI": "Senza dati personali",
        "titleE": "No personal data"
    },
    {
        "id": 2,
        "title": "Personendaten",
        "titleF": "Données personnelles",
        "titleI": "Dati personali",
        "titleE": "Personal data"
    }
]
```

This endpoint retrieves all data security

### HTTP Request

`GET http://127.0.0.1:9002/api/v1/ubit/archive/data_securities`

<aside class="success">
Remember — you must be authenticated !
</aside>

## Get data security by its ID

```shell
curl --request GET \
  --url http://127.0.0.1:9002/api/v1/ubit/archive/data_securities/1 \
  --header 'Authorization: Bearer {ACCESS_TOKEN}'
```

```javascript
```

>You must replace `{ACCESS_TOKEN}` with your personal token.

> The above command returns JSON structured like this:

```json
{
    "id": 1,
    "title": "Keine Personendaten",
    "titleF": "Pas de données personnelles",
    "titleI": "Senza dati personali",
    "titleE": "No personal data"
}
```

This endpoint retrieves a specific data security.

### HTTP Request
`GET http://127.0.0.1:9002/api/v1/ubit/archive/data_securities/<ID>`

### URL Parameters
Parameter | Description
--------- | -----------
ID | The ID of the data security to retrieve

<aside class="success">
Remember — you must be authenticated !
</aside>

## Create a data security
```shell
curl --request POST \
  --url http://127.0.0.1:9002/api/v1/ubit/archive/data_securities/ \
  --header 'Authorization: Bearer {ACCESS_TOKEN}' \
  --data '{"title": "Personendaten, deren Missbrauch für den Betroffenen Gefahren für Leib und Leben bedeuten"}'
```

```javascript
```

>You must replace `{ACCESS_TOKEN}` with your personal token.

This endpoint create a data security.

### HTTP Request
`POST http://127.0.0.1:9002/api/v1/ubit/archive/data_securities/`

### Body Parameters
Parameter | Type | Description
--------- | ----------- | -----------
TITLE * | string | German title of the data security
TITLE_F | string | French title of the data security
TITLE_I | string | Italian title of the data security
TITLE_E | string | English title of the data security

<aside class="notice">
Parameters marked with an asterisk (*) are mandatory.
</aside>

<aside class="success">
Remember — you must be authenticated !
</aside>

## Update a data security
```shell
curl --request PUT \
  --url http://127.0.0.1:9002/api/v1/ubit/archive/data_securities/3 \
  --header 'Authorization: Bearer {ACCESS_TOKEN}' \
  --data '{"titleF": "Données personnelles dont l\'utilisation frauduleuse entraîne un danger pour la personne concernée"}'
```

```javascript
```

>You must replace `{ACCESS_TOKEN}` with your personal token.

This endpoint update a data security.

### HTTP Request
`PUT http://127.0.0.1:9002/api/v1/ubit/archive/data_securities/<ID>`

### URL Parameters
Parameter | Description
--------- | -----------
ID | The ID of the data security to update

### Body Parameters
Parameter | Type | Description
--------- | ----------- | -----------
TITLE | string | German title of the data security
TITLE_F | string | French title of the data security
TITLE_I | string | Italian title of the data security
TITLE_E | string | English title of the data security

<aside class="success">
Remember — you must be authenticated !
</aside>

## Delete a data security
```shell
curl --request DELETE \
  --url http://127.0.0.1:9002/api/v1/ubit/archive/data_securities/1 \
  --header 'Authorization: Bearer {ACCESS_TOKEN}'
```

```javascript
```
>You must replace `{ACCESS_TOKEN}` with your personal token.

This endpoint delete a data security.

### HTTP Request
`DELETE http://127.0.0.1:9002/api/v1/ubit/archive/data_securities/<ID>`

### URL Parameters
Parameter | Description
--------- | -----------
ID | The ID of the data security to delete

<aside class="success">
Remember — you must be authenticated !
</aside>

# Archive/Dispose type
## Object
Name | Type | Description
--------- | ----------- | -----------

# Archive/Public status
## Object
Name | Type | Description
--------- | ----------- | -----------

# Archive/Security class
## Object
Name | Type | Description
--------- | ----------- | -----------
