# Archive/Deadlines
## Deadlines Object
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
