# Registos

{% hint style="warning" %}
Esta secção da API ainda está em desenvolvimento, pelo que poderá sofrer alterações consideráveis. Esta página encontra-se em desenvolvimento.
{% endhint %}

{% swagger method="post" path="/get_questionnaires" baseUrl="https://www.pepdata.com/api" summary="Obter registos" %}
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

### Legenda

* **id**: id do registo.

{% swagger method="post" path="/add_questionnaire" baseUrl="https://www.pepdata.com/api" summary="Adição de um registo" %}
{% swagger-description %}
Endpoint para adicionar um registo de clientes e transações.
{% endswagger-description %}
{% endswagger %}

### Legenda

* **id**: id do registo.

{% swagger method="post" path="/edit_questionnaire" baseUrl="https://www.pepdata.com/api" summary="Edição de um registo" %}
{% swagger-description %}

{% endswagger-description %}
{% endswagger %}

### Legenda

* **id**: id do registo.

{% swagger method="post" path="/delete_questionnaire" baseUrl="https://www.pepdata.com/api" summary="Eliminação um registo" %}
{% swagger-description %}

{% endswagger-description %}
{% endswagger %}

### Legenda <a href="#legenda-2" id="legenda-2"></a>

* **id**: id do registo.

{% swagger method="post" path="/unsubmit_questionnaire" baseUrl="https://www.pepdata.com/api" summary="Cancelar a submissão de um registo" %}
{% swagger-description %}

{% endswagger-description %}
{% endswagger %}

### Legenda <a href="#legenda-2" id="legenda-2"></a>

* **id**: id do registo.

{% swagger method="post" path="/send_questionnaire_invite" baseUrl="https://www.pepdata.com/api" summary="Enviar um convite de preenchimento do registo" %}
{% swagger-description %}

{% endswagger-description %}
{% endswagger %}

### Legenda <a href="#legenda-2" id="legenda-2"></a>

* **id**: id do registo.

{% swagger method="post" path="/cancel_questionnaire_invite" baseUrl="https://www.pepdata.com/api" summary="Cancelar um convite de preenchimento do registo" %}
{% swagger-description %}

{% endswagger-description %}
{% endswagger %}

### Legenda <a href="#legenda-2" id="legenda-2"></a>

* **id**: id do registo.

{% swagger method="post" path="/assign_user_to_questionnaire" baseUrl="https://www.pepdata.com/api" summary="Atribuir um utilizador a um registo" %}
{% swagger-description %}

{% endswagger-description %}
{% endswagger %}

### Legenda <a href="#legenda-2" id="legenda-2"></a>

* **id**: id do registo.

{% swagger method="post" path="/edit_questionnaire_approval_state" baseUrl="https://www.pepdata.com/api" summary="Editar o estado de aprovação de um registo" %}
{% swagger-description %}

{% endswagger-description %}
{% endswagger %}

### Legenda <a href="#legenda-2" id="legenda-2"></a>

* **id**: id do registo.

{% swagger method="post" path="/revert_questionnaire_risk" baseUrl="https://www.pepdata.com/api" summary="Reverter o risco de um registo" %}
{% swagger-description %}

{% endswagger-description %}
{% endswagger %}

### Legenda <a href="#legenda-2" id="legenda-2"></a>

* **id**: id do registo.

{% swagger method="post" path="/reset_questionnaire_needs_attention" baseUrl="https://www.pepdata.com/api" summary="Redefinir o estado "Precisam de atenção" de um registo" %}
{% swagger-description %}

{% endswagger-description %}
{% endswagger %}

### Legenda <a href="#legenda-2" id="legenda-2"></a>

* **id**: id do registo.
