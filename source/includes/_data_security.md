# Archive/Data security
## Data security Object
Name | Type | Description
--------- | ----------- | -----------
id | integer | Id of the data security
title | string | German title of the data security
titleF | string | French title of the data security
titleI | string | Italian title of the data security
titleE | string | English title of the data security

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
title * | string | German title of the data security
titleF | string | French title of the data security
titleI | string | Italian title of the data security
titleE | string | English title of the data security

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
title | string | German title of the data security
titleF | string | French title of the data security
titleI | string | Italian title of the data security
titleE | string | English title of the data security

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
