# Archive/Public status
## Public status Object
Name | Type | Description
--------- | ----------- | -----------
ID | integer | Id of the public status
TITLE | string | German title of the public status
TITLE_F | string | French title of the public status
TITLE_I | string | Italian title of the public status
TITLE_E | string | English title of the public status

## Get all public status
```shell
curl --request GET \
  --url http://127.0.0.1:9002/api/v1/ubit/archive/public_statuses \
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
    "title": "Kein BGÖ",
    "titleF": "Pas de Ltrans",
    "titleI": "No Ltras",
    "titleE": "No BGOE"
  },
  {
    "id": 2,
    "title": "Zugänglich",
    "titleF": "Visible",
    "titleI": "Visibile",
    "titleE": "Visible"
  }
]
```

This endpoint retrieves all public status

### HTTP Request

`GET http://127.0.0.1:9002/api/v1/ubit/archive/public_statuses`

<aside class="success">
Remember — you must be authenticated !
</aside>

## Get public status by its ID

```shell
curl --request GET \
  --url http://127.0.0.1:9002/api/v1/ubit/archive/public_statuses/1 \
  --header 'Authorization: Bearer {ACCESS_TOKEN}'
```

```javascript
```

>You must replace `{ACCESS_TOKEN}` with your personal token.

> The above command returns JSON structured like this:

```json
{
    "id": 1,
    "title": "Kein BGÖ",
    "titleF": "Pas de Ltrans",
    "titleI": "No Ltras",
    "titleE": "No BGOE"
}
```

This endpoint retrieves a specific public status.

### HTTP Request
`GET http://127.0.0.1:9002/api/v1/ubit/archive/public_statuses/<ID>`

### URL Parameters
Parameter | Description
--------- | -----------
ID | The ID of the public status to retrieve

<aside class="success">
Remember — you must be authenticated !
</aside>

## Create a public status
```shell
curl --request POST \
  --url http://127.0.0.1:9002/api/v1/ubit/archive/public_statuses/ \
  --header 'Authorization: Bearer {ACCESS_TOKEN}' \
  --data '{"title": "Nicht zugänglich"}'
```

```javascript
```

>You must replace `{ACCESS_TOKEN}` with your personal token.

This endpoint create a public status.

### HTTP Request
`POST http://127.0.0.1:9002/api/v1/ubit/archive/public_statuses/`

### Body Parameters
Parameter | Type | Description
--------- | ----------- | -----------
TITLE * | string | German title of the public status
TITLE_F | string | French title of the public status
TITLE_I | string | Italian title of the public status
TITLE_E | string | English title of the public status

<aside class="notice">
Parameters marked with an asterisk (*) are mandatory.
</aside>

<aside class="success">
Remember — you must be authenticated !
</aside>

## Update a public status
```shell
curl --request PUT \
  --url http://127.0.0.1:9002/api/v1/ubit/archive/public_statuses/3 \
  --header 'Authorization: Bearer {ACCESS_TOKEN}' \
  --data '{"titleF": "Non visible"}'
```

```javascript
```

>You must replace `{ACCESS_TOKEN}` with your personal token.

This endpoint update a public status.

### HTTP Request
`PUT http://127.0.0.1:9002/api/v1/ubit/archive/public_statuses/<ID>`

### URL Parameters
Parameter | Description
--------- | -----------
ID | The ID of the public status to update

### Body Parameters
Parameter | Type | Description
--------- | ----------- | -----------
TITLE | string | German title of the public status
TITLE_F | string | French title of the public status
TITLE_I | string | Italian title of the public status
TITLE_E | string | English title of the public status

<aside class="success">
Remember — you must be authenticated !
</aside>

## Delete a public status
```shell
curl --request DELETE \
  --url http://127.0.0.1:9002/api/v1/ubit/archive/public_statuses/1 \
  --header 'Authorization: Bearer {ACCESS_TOKEN}'
```

```javascript
```
>You must replace `{ACCESS_TOKEN}` with your personal token.

This endpoint delete a public status.

### HTTP Request
`DELETE http://127.0.0.1:9002/api/v1/ubit/archive/public_statuses/<ID>`

### URL Parameters
Parameter | Description
--------- | -----------
ID | The ID of the public status to delete

<aside class="success">
Remember — you must be authenticated !
</aside>
