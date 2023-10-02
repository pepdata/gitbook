# Búsqueda

{% swagger baseUrl="https://www.pepdata.com/api" path="/search_iperson" method="post" summary="Búsqueda de Persona Identificable" %}
{% swagger-description %}
Endpoint para buscar una persona identificable.
{% endswagger-description %}

{% swagger-parameter in="header" name="Authentication" type="string" %}
key \[API\_KEY]
{% endswagger-parameter %}

{% swagger-parameter in="body" name="name" type="string" %}
Nombre de la persona que se busca
{% endswagger-parameter %}

{% swagger-parameter in="body" name="birth_date" type="string" %}
Fecha de nacimiento de la validación. \
Formato: yyyy-mm-dd\
Default: null
{% endswagger-parameter %}

{% swagger-response status="200" description="Búsqueda completada con éxito." %}
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

### Leyenda

* **id**: id de la persona identificable.
* **name**: nombre de la persona identificable.
* **birth\_date**: fecha de nacimiento de la persona identificable.
* **death\_date**: fecha de la muerte de la persona identificable.
* **id\_country**: país principal de la persona identificable, en formato [ISO 3166-1 alpha-2](https://en.wikipedia.org/wiki/ISO\_3166-1\_alpha-2).
* **score**: [grado de similitud](../glossario/glossario-aplicacao.md#grau-de-semelhanca).
* **country:** país principal de la persona identificable.

{% hint style="info" %}
Para obtener los mejores resultados, se recomienda leer la documentación relativa a su área de [búsqueda](../a-aplicacao/pesquisa.md).
{% endhint %}

{% swagger baseUrl="https://www.pepdata.com/api" path="/search_organization" method="post" summary="Búsqueda de organizaciones sancionadas" %}
{% swagger-description %}
Endpoint para buscar una organización sancionada.
{% endswagger-description %}

{% swagger-parameter in="header" name="Authentication" type="string" %}
key \[API\_KEY]
{% endswagger-parameter %}

{% swagger-parameter in="body" name="name" type="string" %}
Nombre de la organización a buscar
{% endswagger-parameter %}

{% swagger-response status="200" description="Búsqueda completada con éxito." %}
```
{
    "data": {
        "items": [
            {
                "id": "894e61ca-0264-0ed2-542c-d5aa53ef407c",
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

### Leyenda

* **id**: id de la organización sancionada.
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
