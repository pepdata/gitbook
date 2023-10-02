# Pesquisa

{% swagger baseUrl="https://www.pepdata.com/api" path="/search_iperson" method="post" summary="Pesquisa de pessoa identificável" %}
{% swagger-description %}
Endpoint para pesquisar uma pessoa identificável.
{% endswagger-description %}

{% swagger-parameter in="header" name="Authentication" type="string" required="true" %}
key \[API\_KEY]
{% endswagger-parameter %}

{% swagger-parameter in="body" name="name" type="string" required="true" %}
Nome da pessoa a pesquisar
{% endswagger-parameter %}

{% swagger-parameter in="body" name="birth_date" type="string" required="false" %}
Data de nascimento da validação.

\\

Formato: yyyy-mm-dd

\\

Default: null
{% endswagger-parameter %}

{% swagger-response status="200" description="Pesquisa realizada com sucesso." %}
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
              "score": 95,
              "country": "Portugal"
            },
            {
              "id": "d7c48e2d-8699-4064-b94c-d6e2106fdf85",
              "name": "João Pedro Pereira",
              "birth_date": "1933-05-25",
              "death_date": null,
              "id_country": "PT",
              "score": 76,
              "country": "Portugal"
            }
        ]
    },
    "version": "0.1",
    "timestamp": 1588599744111
}
```
{% endswagger-response %}
{% endswagger %}

### Legenda

* **id**: id da pessoa identificável.
* **name**: nome da pessoa identificável.
* **birth\_date**: data de nascimento da pessoa identificável.
* **death\_date**: data de morte da pessoa identificável.
* **id\_country**: país primário da pessoa identificável, no formato [ISO 3166-1 alpha-2](https://en.wikipedia.org/wiki/ISO\_3166-1\_alpha-2).
* **source**: fonte da lista de sanções, caso exista: EU, OFAC, HMTreasury ou UN.
* **score**: [grau de semelhança](../glossario/glossario-aplicacao.md#grau-de-semelhanca).
* **country:** país primário da pessoa identificável.

{% hint style="info" %}
De forma a obter melhores resultados, recomenda-se que leia a documentação referente à área de [pesquisa](../a-aplicacao/pesquisa/).
{% endhint %}

{% swagger baseUrl="https://www.pepdata.com/api" path="/search_organization" method="post" summary="Pesquisa de organizações sancionadas" %}
{% swagger-description %}
Endpoint para pesquisar uma organização sancionada.
{% endswagger-description %}

{% swagger-parameter in="header" name="Authentication" type="string" required="true" %}
key \[API\_KEY]
{% endswagger-parameter %}

{% swagger-parameter in="body" name="name" type="string" required="true" %}
Nome da organização a pesquisar
{% endswagger-parameter %}

{% swagger-response status="200" description="Pesquisa realizada com sucesso." %}
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
{% endswagger-response %}
{% endswagger %}

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
