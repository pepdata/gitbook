# Búsqueda

{% api-method method="post" host="https://www.pepdata.com/api" path="/search\_iperson" %}
{% api-method-summary %}
Búsqueda de Persona Identificable
{% endapi-method-summary %}

{% api-method-description %}
Endpoint para buscar una persona identificable.
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
Nombre de la persona que se busca
{% endapi-method-parameter %}

{% api-method-parameter name="birth\_date" type="string" required=false %}
Fecha de nacimiento de la validación.   
Formato: yyyy-mm-dd  
Default: null
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Búsqueda completada con éxito.
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

### Leyenda

* **id**: id de la persona identificable.
* **name**: nombre de la persona identificable.
* **birth\_date**: fecha de nacimiento de la persona identificable.
* **death\_date**: fecha de la muerte de la persona identificable.
* **id\_country**: país principal de la persona identificable, en formato [ISO 3166-1 alpha-2](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2).
* **score**: [grado de similitud](../glossario/glossario-aplicacao.md#grau-de-semelhanca).

{% hint style="info" %}
Para obtener los mejores resultados, se recomienda leer la documentación relativa a su área de [búsqueda](../a-aplicacao/pesquisa.md).
{% endhint %}

{% api-method method="post" host="https://www.pepdata.com/api" path="/search\_organizations" %}
{% api-method-summary %}
Búsqueda de organizaciones sancionadas
{% endapi-method-summary %}

{% api-method-description %}
Endpoint para buscar una organización sancionada.
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
Nombre de la organización a buscar
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Búsqueda completada con éxito.
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

### Leyenda

* **name**: nombre de la organización sancionada.
* **score**: [grado de similitud](../glossario/glossario-aplicacao.md#grau-de-semelhanca).

{% hint style="info" %}
Este endpoint realiza una búsqueda en organizaciones presentes en las siguientes listas de sanciones internacionales:

* United Nations Security Council Consolidated List
* EU Financial Sanctions Database
* OFAC Specially Designated Nationals and Blocked Persons List
* HM Treasury Financial Sanctions Targets

**Importante:** por el momento, el nombre de la organización debe coincidir con el de la lista de sanciones para que se devuelven resultados.
{% endhint %}

