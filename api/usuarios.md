# Usuarios

{% swagger method="post" path="" baseUrl="https://www.pepdata.com/api/get_users" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="Authentication" type="string" required="true" %}
key \[API\_KEY]
{% endswagger-parameter %}

{% swagger-parameter in="body" name="id" type="string" %}
Id de usario
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
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
        ]
    },
    "version": "0.1",
    "timestamp": 1646390980644
}
```
{% endswagger-response %}
{% endswagger %}

### Leyenda

* **id:** identificación del usuario
* **name:** nombre de usuario
* **email:** correo del usuario

