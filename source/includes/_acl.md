# ACL
## ACL Object
Name | Type | Description
--------- | ----------- | -----------
id | integer | Id of the ACL
aclName | string | German name of the ACL
aclNameF | string | French name of the ACL
aclNameI | string | Italian name of the ACL
aclNameE | string | English name of the ACL
aclDef | string | TODO
aclDefClosed | string | TODO
aclOnCreation | boolean | TODO
removeAdditionalRights | boolean | TODO 

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
aclName * | string | German name of the ACL
aclNameF | string | French name of the ACL
aclNameI | string | Italian name of the ACL
aclNameE | string | English name of the ACL
aclDef * | string | TODO
aclDefClosed * | string | TODO
aclOnCreation * | boolean | TODO
removeAdditionalRights * | boolean | TODO 

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
aclName | string | German name of the ACL
aclNameF | string | French name of the ACL
aclNameI | string | Italian name of the ACL
aclNameE | string | English name of the ACL
aclDef | string | TODO
aclDefClosed | string | TODO
aclOnCreation | boolean | TODO
removeAdditionalRights | boolean | TODO 

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
