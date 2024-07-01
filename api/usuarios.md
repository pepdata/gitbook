# Usuarios

<mark style="color:green;">`POST`</mark> `https://www.pepdata.com/api/get_users`

#### Headers

| Name                                             | Type   | Description     |
| ------------------------------------------------ | ------ | --------------- |
| Authentication<mark style="color:red;">\*</mark> | string | key \[API\_KEY] |

#### Request Body

| Name | Type   | Description                                |
| ---- | ------ | ------------------------------------------ |
| id   | string | Id de usario                               |
| page | number | <p>Página de usuarios</p><p>Default: 1</p> |

{% tabs %}
{% tab title="200: OK " %}
```
{
    "data": {
        "items": [
            {
                "id": "ab152600-4cf5-6b7e-813b-3a4f8bda8f66",
                "name": "Carlos García",
                "email": "carlos.garcia@test.pt",
            },
            {
                "id": "f59c0220-7d33-d2a3-fc42-35030d14c794",
                "name": "Daniela Lopez",
                "email": "daniela.lopez@test.pt",
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

### Leyenda

* **id:** identificación del usuario
* **name:** nombre de usuario
* **email:** correo del usuario

