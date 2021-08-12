# Pesquisa

{% api-method method="post" host="https://www.pepdata.com/api" path="/search\_iperson" %}
{% api-method-summary %}
Pesquisa de pessoa identificável
{% endapi-method-summary %}

{% api-method-description %}
Endpoint para pesquisar uma pessoa identificável.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authentication" type="string" required=true %}
key \[API\_KEY\]
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="name" type="string" required=true %}
Nome da pessoa a pesquisar
{% endapi-method-parameter %}

{% api-method-parameter name="birth\_date" type="string" required=false %}
Data de nascimento da validação.   
Formato: yyyy-mm-dd  
Default: null
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Pesquisa realizada com sucesso.
{% endapi-method-response-example-description %}

```
{
    "data": {
        "items": [
            {
              "id": "0bdeb685-8d0b-41ec-a3ff-996188fe2b22",
              "name": "João Pedro Silva",
              "birth_date": null,
              "death_date": null,
              "id_country": "PT",
              "score": 95
            },
            {
              "id": "d7c48e2d-8699-4064-b94c-d6e2106fdf85",
              "name": "João Pedro Pereira",
              "birth_date": "1933-05-25",
              "death_date": null,
              "id_country": "PT",
              "score": 76
            }
        ]
    },
    "version": "0.1",
    "timestamp": 1588599744111
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

### Legenda

* **id**: id da pessoa identificável.
* **name**: nome da pessoa identificável.
* **birth\_date**: data de nascimento da pessoa identificável.
* **death\_date**: data de morte da pessoa identificável.
* **id\_country**: país primário da pessoa identificável, no formato [ISO 3166-1 alpha-2](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2).
* **score**: [grau de semelhança](../glossario/glossario-aplicacao.md#grau-de-semelhanca).

{% hint style="info" %}
De forma a obter melhores resultados, recomenda-se que leia a documentação referente à área de [pesquisa](../a-aplicacao/pesquisa.md).
{% endhint %}

{% api-method method="post" host="https://www.pepdata.com/api" path="/search\_organizations" %}
{% api-method-summary %}
Pesquisa de organizações sancionadas
{% endapi-method-summary %}

{% api-method-description %}
Endpoint para pesquisar uma organização sancionada.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authentication" type="string" required=true %}
key \[API\_KEY\]
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="name" type="string" required=true %}
Nome da organização a pesquisar
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Pesquisa realizada com sucesso.
{% endapi-method-response-example-description %}

```
{
    "data": {
        "items": [
            {
                "name": "Fekete Szeptember",
                "score": 100
            }
        ]
    },
    "version": "0.1",
    "timestamp": 1588599744111
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

### Legenda

* **name**: nome da organização sancionada.
* **score**: [grau de semelhança](../glossario/glossario-aplicacao.md#grau-de-semelhanca).

{% hint style="info" %}
Este endpoint executa uma pesquisa nas organizações presentes nas seguintes listas de sanções internacionais:

* United Nations Security Council Consolidated List
* EU Financial Sanctions Database
* OFAC Specially Designated Nationals and Blocked Persons List
* HM Treasury Financial Sanctions Targets

**Importante:** de momento, o nome da organização deverá coincidir com o nome presente na lista de sanções para que sejam devolvidos resultados.
{% endhint %}

