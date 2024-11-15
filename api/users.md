# Utilizadores

<mark style="color:green;">`POST`</mark> `https://www.pepdata.com/api/get_users`

#### Headers

| Name                                            | Type   | Description     |
| ----------------------------------------------- | ------ | --------------- |
| Authorization<mark style="color:red;">\*</mark> | string | key \[API\_KEY] |

#### Request Body

| Name | Type   | Description                                     |
| ---- | ------ | ----------------------------------------------- |
| id   | string | Id do utilizador                                |
| page | number | <p>Página dos utilizadores</p><p>Default: 1</p> |

{% tabs %}
{% tab title="200: OK " %}
```javascript
{
    "data": {
        "items": [
            {
                "id": "ab152600-4cf5-6b7e-813b-3a4f8bda8f66",
                "name": "Amílcar da Silva",
                "email": "amilcar.da.silva@test.pt",
            },
            {
                "id": "f59c0220-7d33-d2a3-fc42-35030d14c794",
                "name": "Alcídio da Fonseca",
                "email": "alcidio.da.fonseca@test.pt",
            },
        ],
        "count": 2,
        "total": 2,
        "page": 1,
        "max_results_per_page": 50
    },
    "version": "0.1",
    "timestamp": 1646390980644
}
```
{% endtab %}
{% endtabs %}

### Legenda

* **id**: id do utilizador.
* **name**: nome do utilizador.
* **email**: email do utilizador.
