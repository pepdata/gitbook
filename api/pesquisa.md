# Búsqueda

## Búsqueda de Persona Identificable

<mark style="color:green;">`POST`</mark> `https://www.pepdata.com/api/search_iperson`

Endpoint para buscar una persona identificable.

#### Headers

| Name                                            | Type   | Description     |
| ----------------------------------------------- | ------ | --------------- |
| Authorization<mark style="color:red;">\*</mark> | string | key \[API\_KEY] |

#### Request Body

| Name        | Type   | Description                                                                           |
| ----------- | ------ | ------------------------------------------------------------------------------------- |
| name        | string | Nombre de la persona que se busca                                                     |
| birth\_date | string | <p>Fecha de nacimiento de la validación. <br>Formato: yyyy-mm-dd<br>Default: null</p> |

{% tabs %}
{% tab title="200: OK Búsqueda completada con éxito." %}
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
{% endtab %}

{% tab title="400: Bad Request Nombre inválido" %}


```json
{
    "message": {
        "version": 0.1,
        "timestamp": 1697029998050,
        "message": "El nombre no es válido. Solo se permiten nombres:  • Solo con caracteres latinos, apóstrofes, espacios, puntos o guiones;"
    }
}
```
{% endtab %}
{% endtabs %}

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

## Búsqueda de organizaciones sancionadas

<mark style="color:green;">`POST`</mark> `https://www.pepdata.com/api/search_organization`

Endpoint para buscar una organización sancionada.

#### Headers

| Name                                            | Type   | Description     |
| ----------------------------------------------- | ------ | --------------- |
| Authorization<mark style="color:red;">\*</mark> | string | key \[API\_KEY] |

#### Request Body

| Name | Type   | Description                        |
| ---- | ------ | ---------------------------------- |
| name | string | Nombre de la organización a buscar |

{% tabs %}
{% tab title="200: OK Búsqueda completada con éxito." %}
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
{% endtab %}

{% tab title="400: Bad Request Nombre no ingresado." %}


```json
{
    "message": {
        "version": 0.1,
        "timestamp": 1697030416698,
        "message": "Por favor, introduzca el nombre a buscar."
    }
}
```
{% endtab %}
{% endtabs %}

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

## Obtener informe de búsqueda de entidades

<mark style="color:green;">`POST`</mark> `https://www.pepdata.com/api/get_entities_search_report`

**Headers**

| Name                                            | Type   | Description     |
| ----------------------------------------------- | ------ | --------------- |
| Authorization<mark style="color:red;">\*</mark> | string | key \[API\_KEY] |

**Request Body**

| Name   | Type   | Description                   |
| ------ | ------ | ----------------------------- |
| name\* | string | Nombre de la entidad a buscar |

**Response**

{% tabs %}
{% tab title="200: OK Informe generado con éxito" %}
{% file src="../.gitbook/assets/PEPData - Informe de Búsqueda de Entidades - António Silva.pdf" %}
Ejemplo de informe de búsqueda de entidades
{% endfile %}


{% endtab %}

{% tab title="400: Bad Request Nombre no ingresado" %}
```
{
    "message": {
        "version": 0.1,
        "timestamp": 1697030777756,
        "message": "Por favor, introduzca un nombre."
    }
}
```
{% endtab %}
{% endtabs %}
