# Archive/Dispose type
## Dispose type Object
Name | Type | Description
--------- | ----------- | -----------
ID | integer | Id of the dispose type
TITLE | string | German title of the dispose type
TITLE_F | string | French title of the dispose type
TITLE_I | string | Italian title of the dispose type
TITLE_E | string | English title of the dispose type

## Get all dispose type
```shell
curl --request GET \
  --url http://127.0.0.1:9002/api/v1/ubit/archive/dispose_types \
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
    "title": "Noch nicht bewertet",
    "titleF": "Pas encore évalué",
    "titleI": "Non ancora valutato",
    "titleE": "Not evaluated"
  },
  {
    "id": 2,
    "title": "Bundesarchiv",
    "titleF": "Archives fédérales",
    "titleI": "Archivio federale",
    "titleE": "Transfer"
  }
]
```

This endpoint retrieves all dispose type

### HTTP Request

`GET http://127.0.0.1:9002/api/v1/ubit/archive/dispose_types`

<aside class="success">
Remember — you must be authenticated !
</aside>

## Get dispose type by its ID

```shell
curl --request GET \
  --url http://127.0.0.1:9002/api/v1/ubit/archive/dispose_types/1 \
  --header 'Authorization: Bearer {ACCESS_TOKEN}'
```

```javascript
```

>You must replace `{ACCESS_TOKEN}` with your personal token.

> The above command returns JSON structured like this:

```json
{
    "id": 1,
    "title": "Noch nicht bewertet",
    "titleF": "Pas encore évalué",
    "titleI": "Non ancora valutato",
    "titleE": "Not evaluated"
}
```

This endpoint retrieves a specific dispose type.

### HTTP Request
`GET http://127.0.0.1:9002/api/v1/ubit/archive/dispose_types/<ID>`

### URL Parameters
Parameter | Description
--------- | -----------
ID | The ID of the dispose type to retrieve

<aside class="success">
Remember — you must be authenticated !
</aside>

## Create a dispose type
```shell
curl --request POST \
  --url http://127.0.0.1:9002/api/v1/ubit/archive/dispose_types/ \
  --header 'Authorization: Bearer {ACCESS_TOKEN}' \
  --data '{"title": "Nicht archivwürdig"}'
```

```javascript
```

>You must replace `{ACCESS_TOKEN}` with your personal token.

This endpoint create a dispose type

### HTTP Request
`POST http://127.0.0.1:9002/api/v1/ubit/archive/dispose_types/`

### Body Parameters
Parameter | Type | Description
--------- | ----------- | -----------
TITLE * | string | German title of the dispose type
TITLE_F | string | French title of the dispose type
TITLE_I | string | Italian title of the dispose type
TITLE_E | string | English title of the dispose type

<aside class="notice">
Parameters marked with an asterisk (*) are mandatory.
</aside>

<aside class="success">
Remember — you must be authenticated !
</aside>

## Update a dispose type
```shell
curl --request PUT \
  --url http://127.0.0.1:9002/api/v1/ubit/archive/dispose_types/3 \
  --header 'Authorization: Bearer {ACCESS_TOKEN}' \
  --data '{"titleF": "Sans valeur archivistique"}'
```

```javascript
```

>You must replace `{ACCESS_TOKEN}` with your personal token.

This endpoint update a dispose type.

### HTTP Request
`PUT http://127.0.0.1:9002/api/v1/ubit/archive/dispose_types/<ID>`

### URL Parameters
Parameter | Description
--------- | -----------
ID | The ID of the dispose type to update

### Body Parameters
Parameter | Type | Description
--------- | ----------- | -----------
TITLE | string | German title of the dispose type
TITLE_F | string | French title of the dispose type
TITLE_I | string | Italian title of the dispose type
TITLE_E | string | English title of the dispose type

<aside class="success">
Remember — you must be authenticated !
</aside>

## Delete a dispose type
```shell
curl --request DELETE \
  --url http://127.0.0.1:9002/api/v1/ubit/archive/dispose_types/1 \
  --header 'Authorization: Bearer {ACCESS_TOKEN}'
```

```javascript
```
>You must replace `{ACCESS_TOKEN}` with your personal token.

This endpoint delete a dispose type.

### HTTP Request
`DELETE http://127.0.0.1:9002/api/v1/ubit/archive/dispose_types/<ID>`

### URL Parameters
Parameter | Description
--------- | -----------
ID | The ID of the dispose type to delete

<aside class="success">
Remember — you must be authenticated !
</aside>