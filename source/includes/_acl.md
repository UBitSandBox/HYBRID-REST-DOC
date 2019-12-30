# ACL
## ACL Object
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
