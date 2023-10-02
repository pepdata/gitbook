# Utilizadores

{% swagger method="post" path="/get_users" baseUrl="https://www.pepdata.com/api" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="Authentication" type="string" required="true" %}
key \[API\_KEY]
{% endswagger-parameter %}

{% swagger-parameter in="body" name="id" type="string" required="false" %}
Id do utilizador
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
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
        ]
    },
    "version": "0.1",
    "timestamp": 1646390980644
}
```
{% endswagger-response %}
{% endswagger %}

### Legenda

* **id**: id do utilizador.
* **name**: nome do utilizador.
* **email**: email do utilizador.
