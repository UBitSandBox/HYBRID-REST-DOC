# Archive/Security class
## Security class Object
Name | Type | Description
--------- | ----------- | -----------
ID | integer | Id of the security class
TITLE | string | German title of the security class
TITLE_F | string | French title of the security class
TITLE_I | string | Italian title of the security class
TITLE_E | string | English title of the security class

## Get all security class
```shell
curl --request GET \
  --url http://127.0.0.1:9002/api/v1/ubit/archive/security_classes \
  --header 'Authorization: Bearer {ACCESS_TOKEN}'
```

```javascript
```

>You must replace `{ACCESS_TOKEN}` with your personal token.

>The above command returns JSON structured like this:

```json
[
  {
    "id":1,
    "title":"Nicht Klassifiziert",
    "titleF":"Non classifié",
    "titleI":"Non classificato",
    "titleE":"Not Categorized"
  },
  {
    "id":2,
    "title":"Vertraulich",
    "titleF":"Confidentiel",
    "titleI":"Confidenziale",
    "titleE":"Confidential"
  }
]
```

This endpoint retrieves all security class

### HTTP Request

`GET http://127.0.0.1:9002/api/v1/ubit/archive/security_classes`

<aside class="success">
Remember — you must be authenticated !
</aside>

## Get security class by its ID

```shell
curl --request GET \
  --url http://127.0.0.1:9002/api/v1/ubit/archive/security_classes/1 \
  --header 'Authorization: Bearer {ACCESS_TOKEN}'
```

```javascript
```

>You must replace `{ACCESS_TOKEN}` with your personal token.

> The above command returns JSON structured like this:

```json
{
    "id":1,
    "title":"Nicht Klassifiziert",
    "titleF":"Non classifié",
    "titleI":"Non classificato",
    "titleE":"Not Categorized"
}
```

This endpoint retrieves a specific security class.

### HTTP Request
`GET http://127.0.0.1:9002/api/v1/ubit/archive/security_classes/<ID>`

### URL Parameters
Parameter | Description
--------- | -----------
ID | The ID of the security class to retrieve

<aside class="success">
Remember — you must be authenticated !
</aside>

## Create a security class
```shell
curl --request POST \
  --url http://127.0.0.1:9002/api/v1/ubit/archive/security_classes/ \
  --header 'Authorization: Bearer {ACCESS_TOKEN}' \
  --data '{"title": "Intern"}'
```

```javascript
```

>You must replace `{ACCESS_TOKEN}` with your personal token.

This endpoint create a security class.

### HTTP Request
`POST http://127.0.0.1:9002/api/v1/ubit/archive/security_classes/`

### Body Parameters
Parameter | Type | Description
--------- | ----------- | -----------
TITLE * | string | German title of the security class
TITLE_F | string | French title of the security class
TITLE_I | string | Italian title of the security class
TITLE_E | string | English title of the security class

<aside class="notice">
Parameters marked with an asterisk (*) are mandatory.
</aside>

<aside class="success">
Remember — you must be authenticated !
</aside>

## Update a security class
```shell
curl --request PUT \
  --url http://127.0.0.1:9002/api/v1/ubit/archive/security_classes/3 \
  --header 'Authorization: Bearer {ACCESS_TOKEN}' \
  --data '{"titleF": "Interne"}'
```

```javascript
```

>You must replace `{ACCESS_TOKEN}` with your personal token.

This endpoint update a security class.

### HTTP Request
`PUT http://127.0.0.1:9002/api/v1/ubit/archive/security_classes/<ID>`

### URL Parameters
Parameter | Description
--------- | -----------
ID | The ID of the security class to update

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

## Delete a security class
```shell
curl --request DELETE \
  --url http://127.0.0.1:9002/api/v1/ubit/archive/security_classes/1 \
  --header 'Authorization: Bearer {ACCESS_TOKEN}'
```

```javascript
```
>You must replace `{ACCESS_TOKEN}` with your personal token.

This endpoint delete a security class.

### HTTP Request
`DELETE http://127.0.0.1:9002/api/v1/ubit/archive/security_classes/<ID>`

### URL Parameters
Parameter | Description
--------- | -----------
ID | The ID of the security class to delete

<aside class="success">
Remember — you must be authenticated !
</aside>
