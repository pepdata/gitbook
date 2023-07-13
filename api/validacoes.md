# Validaciones

{% swagger baseUrl="https://www.pepdata.com/api" path="/get_validations" method="post" summary="Obtener validaciones" %}
{% swagger-description %}
Endpoint para obtener validaciones.
{% endswagger-description %}

{% swagger-parameter in="header" name="Authentication" type="string" %}
key [API_KEY]
{% endswagger-parameter %}

{% swagger-parameter in="body" name="page" type="number" %}
Página de validaciones

\


Default: 1
{% endswagger-parameter %}

{% swagger-parameter in="body" name="source" type="string" %}
Origen de las validaciones

\


Default: all

\


Valores posibles: all, upload, manual
{% endswagger-parameter %}

{% swagger-parameter in="body" name="status" type="string" %}
Estado de validación

\


Default: incomplete

\


Valores posibles: all, complete, complete_identified, complete_not_identified, complete_needs_attention, incomplete
{% endswagger-parameter %}

{% swagger-response status="200" description="Validaciones obtenidas con éxito." %}
```
{
    "version": 0.1,
    "timestamp": 1688640113263,
    "data": {
        "page": 1,
        "max_results_per_page": 50,
        "items": [
            {
                "id": "0984f9f1-1895-dc5b-6530-9075825225aa",
                "vatin": "628579388",
                "source": "Automatic",
                "name": "António Jorge Melo Lourenço Neco Rodrigues Fernandes",
                "birth_date": "1931-07-19",
                "id_country_nationality": "PT",
                "id_country_address": null,
                "decision": null,
                "id_iperson": null,
                "iperson_classifications": [
                    "PRP",
                    "Familiar",
                    "Asociado
                ],
                "iperson_classifications": null,
                "added_by": "cd9f4a64-ab25-4efb-bf31-323ee2280095",
                "added_at": 1688639245750,
                "determined_at": null,
                "determined_by": null,
                "identifiable_country": null,
                "id_organization": "6cc1b6c1-33a9-4095-a4a4-aaca0db8d647",
                "id_custom": null,
                "entity_type": "individual",
                "id_iorganization": null,
                "adverse_media_searched_at": null,
                "alerts": [],
                "country_nationality": "Portugal"
            },
            {
                "id": "a58dd84e-7e89-9904-5acf-2b1fbfcc8a31",
                "vatin": "595596160",
                "source": "Automatic",
                "name": "Maria Edite Nieto",
                "birth_date": null,
                "id_country_nationality": "PT",
                "id_country_address": null,
                "decision": null,
                "id_iperson": null,
                "iperson_classifications": null,
                "added_by": "cd9f4a64-ab25-4efb-bf31-323ee2280095",
                "added_at": 1688639245750,
                "determined_at": null,
                "determined_by": null,
                "identifiable_country": null,
                "id_organization": "6cc1b6c1-33a9-4095-a4a4-aaca0db8d647",
                "id_custom": null,
                "entity_type": "individual",
                "id_iorganization": null,
                "adverse_media_searched_at": null,
                "alerts": [
                    {
                        "id": "1d71c856-8dde-4815-9dce-1683e176a6f1",
                        "added_at": 1689244974065,
                        "resolved_by": null,
                        "resolved_at": null,
                        "reasons": [
                            "Hay un nuevo resultado que podría coincidir con esta validación: María García"
                        ]
                    }
                ],
                "country_nationality": "Portugal"
            },
        ]
    }
}
```
{% endswagger-response %}
{% endswagger %}

### Leyenda

* **id**: id de validación.
* **vatin:** nif de la validación.
* **source**: origen de la validación.
* **name**: nombre de validación.
* **birth\_date**: fecha de nacimiento de la validación.
* **id\_country\_nationality**: país de nacionalidad de la validación, en el formato [ISO 3166-1 alpha-2](https://en.wikipedia.org/wiki/ISO\_3166-1\_alpha-2).
* **id\_country\_address**: país de residencia de la validación, en el formato [ISO 3166-1 alpha-2](https://en.wikipedia.org/wiki/ISO\_3166-1\_alpha-2).
* **decision**: booleano que describe si ha habido una coincidencia con una persona identificable.
* **id\_iperson**: id de la persona identificable correspondiente. null si no se ha encontrado ninguna coincidencia.
* **iperson\_classifications:** lista de classificações da pessoa identificável, possíveis valores:
  * Asociado
  * Familiar
  * Titular de Otros Cargos
  * PRP
  * Sancionado (EU)
  * Sancionado (HM Treasury)
  * Sancionado (OFAC)
  * Sancionado (UN)
* **iperson\_classifications:** lista de clasificaciones de personas identificables.
* **added\_by**: id del usuario que ha [agregado ](../a-aplicacao/validacoes/#adicao-determinacao-e-estados-de-validacoes)la validación, como el número de milisegundos desde el 1 de enero de 1970 00:00:00 UTC.
* **added\_at**: la fecha a la que se agregó la validación, como el número de milisegundos desde el 1 de enero de 1970 00:00:00 UTC.
* **determined\_at**: la fecha en la que se determinó la validación, como el número de milisegundos desde el 1 de enero de 1970 00:00:00 UTC.
* **determined\_by**: id del usuario que ha [determinado ](../a-aplicacao/validacoes/#adicao-determinacao-e-estados-de-validacoes)la validación.
* **identifiable\_country:** booleano que describe si el país de validación está sancionado.
* **id\_organization:** id de la organización que creó la validación.
* **id\_custom:** identificación personalizable ingresada por el usuario.
* **entity\_type:** tipo de validación, que puede ser: "individual" u "organization".
* **id\_iorganization**: identificación de la organización identificable correspondiente. null si no hubo ninguna coincidencia.
* **adverse\_media\_searched\_at:** fecha de la última búsqueda de noticias adversas asociadas al nombre de la validación.
* **alerts:** alertas relacionadas con la validación y que aún están sin resolver.
* **country\_nationality:** país de nacionalidad.

{% swagger baseUrl="https://www.pepdata.com/api" path="/add_validation" method="post" summary="Agregar validación" %}
{% swagger-description %}
Endpoint para agregar una validación.
{% endswagger-description %}

{% swagger-parameter in="body" name="name" type="string" required="true" %}
Nombre de validación
{% endswagger-parameter %}

{% swagger-parameter in="header" name="Authentication" type="string" %}
key [API_KEY]
{% endswagger-parameter %}

{% swagger-parameter in="body" name="birth_date" type="string" %}
Fecha  de nacimiento de la validación.

**Parámetro solo utilizado en validaciones de personas.**\
Formato: yyyy-mm-dd\
Default: null
{% endswagger-parameter %}

{% swagger-parameter in="body" name="ignore_duplicates" type="boolean" %}
Instrucción para omitir el control por duplicado.

\


Formato: 0/1

\


Default: 0
{% endswagger-parameter %}

{% swagger-parameter in="body" name="country_nationality" type="string" %}
País de nacionalidad de la validación.

**Parámetro solo utilizado en validaciones de personas.**\
Formato: Nombre del país (véase la nota más abajo)\
Default: null
{% endswagger-parameter %}

{% swagger-parameter in="body" name="country_address" type="string" %}
País de residencia de la validación.

**Parámetro solo utilizado en validaciones de personas.**\
Formato: Nombre del país (véase la nota más abajo)\
Default: null
{% endswagger-parameter %}

{% swagger-parameter in="body" name="country" %}
País de la validación.

**Parámetro solo utilizado en validaciones de organizaciones.**

Formato: Nombre del país (véase la nota más abajo)

Default: null
{% endswagger-parameter %}

{% swagger-parameter in="body" name="vatin" type="string" %}
Nif de la validación

\


Default: null
{% endswagger-parameter %}

{% swagger-parameter in="body" name="id_custom" type="string" %}
id personalizable de la validación

\


Default: null
{% endswagger-parameter %}

{% swagger-parameter in="body" name="type" type="string" %}
Tipo de entidad, que puede ser: "individual" u "organization".

Default: "individual"
{% endswagger-parameter %}

{% swagger-response status="200" description="Validación añadida con éxito." %}
```

{
    "data": {
        "id": "926b7dab-a3af-986f-2137-872adb95260f"
    },
    "version": "0.1",
    "timestamp": 1588599744111
}
```
{% endswagger-response %}

{% swagger-response status="400" description="La validación a agregar ya está en la base de datos." %}
```
{
    "message": "Esta validação parece já existir na base de dados"
    "version": "versão da API",
    "timestamp": X 
}
```
{% endswagger-response %}
{% endswagger %}

### Leyenda

* **id**: id de la validación creada.

{% hint style="info" %}
**country\_nationality, country\_address y country**&#x20;

* Hay muchas formas diferentes de escribir el nombre de cada país. La aplicación PEPData puede identificar todos los nombres de países presentes en la [Lista de los Estados, territórios y monedas de la Unión Europea](https://publications.europa.eu/code/pt/pt-5000500.htm).Sin embargo, para garantizar una mayor solidez, recomendamos el uso del formato [ISO 3166-1 alpha-2](https://en.wikipedia.org/wiki/ISO\_3166-1\_alpha-2), siempre que sea posible.
{% endhint %}



{% swagger baseUrl="https://www.pepdata.com/api" path="/analyze_validation" method="post" summary="Analizar la validación" %}
{% swagger-description %}
Endpoint para consultar los resultados obtenidos del análisis de una validación.
{% endswagger-description %}

{% swagger-parameter in="header" name="Authentication" type="string" %}
key [API_KEY]
{% endswagger-parameter %}

{% swagger-parameter in="body" name="id" type="string" %}
Id de la validación
{% endswagger-parameter %}

{% swagger-response status="200" description="Resultados del análisis de validación obtenidos con éxito." %}
```
{
    "data": {
        "items": [
            {
              "id": "0bdeb685-8d0b-41ec-a3ff-996188fe2b22",
              "name": "João Pedro Silva",
              "birth_date": null,
              "score": 95
            },
            {
              "id": "BFFD688C-4618-048D-9C14-8887B1BDA173",
              "name": "João Pedro Pereira",
              "birth_date": "1933-05-25",
              "score": 76
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

* **id**: identificación de la persona identificable.
* **name**: nombre de la persona identificable.
* **birth\_date**: fecha de nacimiento de la persona identificable.
* **score**: [grado de similitud](../glossario/glossario-aplicacao.md#grau-de-semelhanca).

{% swagger baseUrl="https://www.pepdata.com/api" path="/determine_validation" method="post" summary="Determinación de la validación" %}
{% swagger-description %}
Endpoint para enviar una validación.
{% endswagger-description %}

{% swagger-parameter in="header" name="Authentication" type="string" %}
key [API_KEY]
{% endswagger-parameter %}

{% swagger-parameter in="body" name="id" type="string" %}
Id de validación
{% endswagger-parameter %}

{% swagger-parameter in="body" name="id_entity" type="string" %}
Id de la persona u organización identificable correspondiente. 
{% endswagger-parameter %}

{% swagger-response status="200" description=" La validación ha sido enviada con éxito." %}
```
{
    "data": {},
    "version": "0.1",
    "timestamp": 1588599744111
}
```
{% endswagger-response %}
{% endswagger %}

{% swagger baseUrl="https://www.pepdata.com/api" path="/delete_validation" method="post" summary="Eliminar la validación" %}
{% swagger-description %}
Endpoint para eliminar una validación.
{% endswagger-description %}

{% swagger-parameter in="header" name="Authentication" type="string" %}
key [API_KEY]
{% endswagger-parameter %}

{% swagger-parameter in="body" name="id" type="string" %}
Id de validación
{% endswagger-parameter %}

{% swagger-response status="200" description="La validación ha sido eliminada con éxito" %}
```
{
    "data": {},
    "version": "0.1",
    "timestamp": 1588599744111
}
```
{% endswagger-response %}
{% endswagger %}

{% swagger baseUrl="https://www.pepdata.com/api" path="/apply_rules" method="post" summary="Aplicación de las reglas" %}
{% swagger-description %}
Endpoint para la aplicación de las reglas de validación.
{% endswagger-description %}

{% swagger-parameter in="header" name="Authentication" type="string" %}
key [API_KEY]
{% endswagger-parameter %}

{% swagger-response status="200" description="Las reglas han empezado a aplicarse." %}
```
{
    "data": {
        "time_to_conclusion": X
    },
    "version": "0.1",
    "timestamp": 1588599744111
}
```
{% endswagger-response %}
{% endswagger %}

### Leyenda

* **time\_to\_conclusion**: tiempo **estimado** para completar la aplicación de las reglas, en segundos.

{% hint style="warning" %}
Se recomienda fuertemente leer la documentación sobre la [aplicación de    las reglas de validación](../a-aplicacao/validacoes/aplicacao-de-regras.md), ya que aplicarlas sin una comprensión adecuada puede conducir a cambios no deseados.
{% endhint %}

{% hint style="info" %}
A [aplicación de la regla](../a-aplicacao/validacoes/aplicacao-de-regras.md) puede tardar varios minutos en completarse, dependiendo del número de validaciones incompletas existentes. El tiempo estimado de finalización se devuelve en la respuesta.
{% endhint %}
