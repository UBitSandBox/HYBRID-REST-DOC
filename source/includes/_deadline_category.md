# Archive/Deadline category
## Deadline category Object
Name | Type | Description
--------- | ----------- | -----------
id | integer | Id of the deadline category
title | string | German title of the deadline category
titleF | string | French title of the deadline category
titleI | string | Italian title of the deadline category
titleE | string | English title of the deadline category
desc | string | German description of the deadline category
descF | string | French description of the deadline category
descI | string | Italian description of the deadline category
descE | string | English description of the deadline category

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
title * | string | German title of the deadline category
titleF | string | French title of the deadline category
titleI | string | Italian title of the deadline category
titleE | string | English title of the deadline category
desc * | string | German description of the deadline category
descF | string | French description of the deadline category
descI | string | Italian description of the deadline category
descE | string | English description of the deadline category

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
title | string | German title of the deadline category
titleF | string | French title of the deadline category
titleI | string | Italian title of the deadline category
titleE | string | English title of the deadline category
desc | string | German description of the deadline category
descF | string | French description of the deadline category
descI | string | Italian description of the deadline category
descE | string | English description of the deadline category

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
