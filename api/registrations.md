# Registos

{% hint style="warning" %}
Esta secção da API ainda está em desenvolvimento, pelo que poderá sofrer alterações consideráveis.
{% endhint %}

{% swagger method="post" path="get_questionnaires" baseUrl="https://www.pepdata.com/api" summary="Obter registos" %}
{% swagger-description %}
Endpoint para obter os registos de clientes e transações.
{% endswagger-description %}

{% swagger-parameter in="header" name="Authentication" type="string" required="true" %}
key [API_KEY]
{% endswagger-parameter %}

{% swagger-parameter in="body" name="id" type="string" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="search_term" type="string" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="page" type="integer" %}

{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Registos obtidos com sucesso." %}
```javascript
{
    "data": {
        "items": [
            {
                "id": "2a206d4a-0a5d-4a04-9a0c-cadae6e2cffa", 
                "name": "Lisa Fidalgo Corte-Real",
                "vatin": "255627777",
                "type": "individual",
                "added_at": 1588003603593,
                "added_by": "839a5871-fa0e-470a-af42-9110f8ef5b27",
                "submitted_at": null,
                "submitted_by": null,
                "accepted_at": null,
                "accepted_by": null,
                "data_treatment_accepted_at": null,
                "saved_at": 1648132877766,
                "assigned_to": null,
                "approval_state": null,
                "approval_change_reason": null,
                "risk": null,
                "risk_change_reason": null,
                "needs_attention": 0,
                "id_custom": "ID1"
            }
        ],
        "page": 1,
        "max_results_per_page": 50,
        "total": 1
    },
    "version": "0.1",
    "timestamp": 1648132877766
}
```
{% endswagger-response %}
{% endswagger %}

