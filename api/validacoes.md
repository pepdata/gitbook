# Validaciones

{% swagger baseUrl="https://www.pepdata.com/api" path="/get_validations" method="post" summary="Obtener validaciones" %}
{% swagger-description %}
Endpoint para obtener validaciones.
{% endswagger-description %}

{% swagger-parameter in="header" name="Authentication" type="string" %}
key \[API\_KEY]
{% endswagger-parameter %}

{% swagger-parameter in="body" name="page" type="number" %}
Página de validaciones\
Default: 1
{% endswagger-parameter %}

{% swagger-parameter in="body" name="source" type="string" %}
Origen de las validaciones\
Default: all\
Valores posibles: all, upload, manual
{% endswagger-parameter %}

{% swagger-parameter in="body" name="status" type="string" %}
Estado de validación\
Default: incomplete\
Valores posibles: all, complete, complete\_identified, complete\_not\_identified, complete\_needs\_attention, incomplete
{% endswagger-parameter %}

{% swagger-response status="200" description="Validaciones obtenidas con éxito." %}
```
{
    "version": 0.1,
    "timestamp": 1688640113263,
    "data": {
        "count": 2,
        "total": 2,
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
                "relations": [
                    {
                        "name": "António Silva",
                        "vatin": null,
                        "id_iperson": "5e809bc7-927e-3dc3-0ff8-ab9022843a5a",
                        "id_iorganization": null,
                        "relationship_type": "representative",
                        "id_relationship_info": "d0a4effc-576e-a4a2-f32e-9e594d7144ba"
                    }
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
                "judicial_processes_searched_at": null,
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
                "relations": null,
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
                "judicial_processes_searched_at": null,
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
* **iperson\_classifications:** lista de clasificaciones de la persona identificable, posibles valores:
  * Asociado
  * Familiar
  * Titular de Otros Cargos
  * PRP
  * Sancionado (EU)
  * Sancionado (HM Treasury)
  * Sancionado (OFAC)
  * Sancionado (UN)
* **relations:** lista de relaciones asociadas con la validación. Contiene las siguientes propriedades:
  * **name:** nombre de la relación.
  * **vatin:** nif de la relación.
  * **id\_iperson:** id de la persona identificable asociada con la relación.
  * **id\_iorganization:** id de la organización identificable asociada con la relación.
  * **relationship\_type:** tipo de relación. Valores posibles:
    * representative
    * manager
    * beneficary
    * beneficial\_owner
  * **id\_relationship\_info:** id de la relación.
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
* **judicial\_processes\_searched\_at:** fecha de la última búsqueda de procesos judiciales asociados al nombre de la validación.
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
key \[API\_KEY]
{% endswagger-parameter %}

{% swagger-parameter in="body" name="birth_date" type="string" %}
Fecha  de nacimiento de la validación.

**Parámetro solo utilizado en validaciones de personas.**\
Formato: yyyy-mm-dd\
Default: null
{% endswagger-parameter %}

{% swagger-parameter in="body" name="ignore_duplicates" type="boolean" %}
Instrucción para omitir el control por duplicado.\
Formato: 0/1\
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
Nif de la validación\
Default: null
{% endswagger-parameter %}

{% swagger-parameter in="body" name="id_custom" type="string" %}
id personalizable de la validación\
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

{% swagger-response status="409: Conflict" description="La validación a agregar ya está en la base de datos." %}
```
{
    "message": "Esta validação parece já existir na base de dados"
    "version": 0.1,
    "timestamp": 1696943296957
}
```
{% endswagger-response %}

{% swagger-response status="400: Bad Request" description="Nombre inválido" %}


```json
{
    "message": {
        "version": 0.1,
        "timestamp": 1697017001540,
        "message": "El nombre no es válido. Solo se permiten nombres:  • Solo con caracteres latinos, apóstrofes, espacios, puntos o guiones;"
    }
}
```
{% endswagger-response %}
{% endswagger %}

### Leyenda

* **id**: id de la validación creada.



{% swagger method="post" path="" baseUrl="https://www.pepdata.com/api/get_alerts" summary="Obtener validaciones" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="Authentication" required="true" type="string" %}
key \[API\_KEY]
{% endswagger-parameter %}

{% swagger-parameter in="body" name="id_validation" type="string" %}
Id de la validación
{% endswagger-parameter %}

{% swagger-parameter in="body" name="ids_validations" type="string array" %}
Array de ids de validaciónes
{% endswagger-parameter %}

{% swagger-parameter in="body" name="status" type="string" %}
Estado de alertas Predeterminado: sin resolver Valores posibles: todos, resueltos, no resueltos
{% endswagger-parameter %}

{% swagger-parameter in="body" name="from" type="int" %}
Fecha de inicio del filtro, com número de milisegundos desde el 1 de enero de 1970 00:00:00 UTC
{% endswagger-parameter %}

{% swagger-parameter in="body" name="until" type="int" %}
Fecha de finalización del filtro, com número de milisegundos desde el 1 de enero de 1970 00:00:00 UTC
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Alertas de validación obtenidas con éxito" %}


```json
{
    "version": 0.1,
    "timestamp": 1693318084192,
    "data": {
        "items": [
            {
                "id": "53fef9d4-e3d4-ed03-5e79-38ba066050f7",
                "id_validation": "3462600c-8b9a-6384-c321-4587104ce0f1",
                "name": "José Codinha Manso",
                "birth_date": null,
                "id_country_nationality": "JP",
                "added_at": 1687873995707,
                "resolved_at": null,
                "resolved_by": null,
                "status": "unresolved",
                "reason": "Podem ter sido encontradas novas adverse media relativas a esta pessoa.",
                "country_nationality": "Japan"
            }
        ],
        "count": 1,
        "total": 1,
        "page": 1,
        "max_results_per_page": 50
    }
}
```
{% endswagger-response %}

{% swagger-response status="400: Bad Request" description="estado de alertas inválido" %}
```
{
    "message": {
        "version": 0.1,
        "timestamp": 1588599744111,
        "message": "El campo 'estado' no es válido."
    }
}
```
{% endswagger-response %}
{% endswagger %}

### Leyenda

* **id**: id de la alerta.
* **id\_validation:**  id de validación.
* **name**: nombre de la persona idenficiable.
* **birth\_date**: fecah de nacimiento de la persona identificable.
* **id\_country\_nationality**: código del país de la nacionalidad, en formato [ISO 3166-1 alpha-2](https://en.wikipedia.org/wiki/ISO\_3166-1\_alpha-2).
* **added\_at**: fecha en que se creó la alerta, expressada en milisegundos desde el 1 de enero de 1970 a las 1970 00:00:00 UTC.
* **resolved\_at:** fecha en que se resolvió la alerta, expressada en milisegundos desde el 1 de enero de 1970 a las 1970 00:00:00 UTC.
* **resolved\_by:** usuario que resolvió la alerta.
* **status:** estado de la alerta.
* **reason**: motivo para crear la alerta.
* **country\_nationality:** país de nacionalidad.

{% hint style="info" %}
**country\_nationality, country\_address e country**

Hay múltiples formas diferentes de escribir el nombre de cada país. La aplicación PEPData es capaz de identificar todas las denominaciones de los países presentes en la [Lista de Estados, territorios y monedas de la Unión Europea](https://publications.europa.eu/code/pt/pt-5000500.htm). Sin embargo, para garantizar una mayor robustez, recomendamos utilizar el formato [ISO 3166-1 alpha-2](https://en.wikipedia.org/wiki/ISO\_3166-1\_alpha-2), siempre que sea posible.
{% endhint %}

{% swagger baseUrl="https://www.pepdata.com/api" path="/analyze_validation" method="post" summary="Analizar la validación" %}
{% swagger-description %}
Endpoint para consultar los resultados obtenidos del análisis de una validación.
{% endswagger-description %}

{% swagger-parameter in="header" name="Authentication" type="string" %}
key \[API\_KEY]
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
              "classifications": [
                    "PEP"
                ],
                "occupations": [
                    {
                        "organization": "Governo da República Portuguesa",
                        "organ": "Ministério dos Negócios Estrangeiros",
                        "position": "Ministro",
                        "source": "https://test-link.com",
                        "start_date": null,
                        "end_date": null,
                        "comments": null
                    }
                ],
                "relationships": []
            },
            {
              "id": "BFFD688C-4618-048D-9C14-8887B1BDA173",
              "name": "João Pedro Pereira",
              "birth_date": "1933-05-25",
              "score": 76,
              "classifications": [
                    "PEP",
                    "Familiar"
                ],
                "occupations": [
                    {
                        "organization": "Governo da República Portuguesa",
                        "organ": "Ministério dos Negócios Estrangeiros",
                        "position": "Ministro",
                        "source": "https://test-link.com",
                        "start_date": "2005-01-01",
                        "end_date": "2030-01-01",
                        "comments": null
                    }
                ],
                "relationships": [
                    {
                        "relationship_type": "son",
                        "relationship_to": "Flávio Alberto Roldão",
                        "source": "https://test-link.com",
                        "end_date": null,
                        "comments": null
                    },
                    {
                        "relationship_type": "spouse",
                        "relationship_to": "Albertina Hermínia da Corte",
                        "source": "https://test-link.com",
                        "end_date": null,
                        "comments": null
                    }
                ]
            }
        ],
        "count": 2
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
* **classifications**: clasificaciones de la persona identificable.
* **occupations**: lista de ocupaciones de la persona identificable:
  * **organization**: organización de la ocupación.
  * **organ**: organismo de la ocupación.
  * **position**: posición de la ocupación.
  * **source**: link de la fuente que relaciona a la persona identificable con lá ocupación.
  * **start\_date:** fecha de inicio de la ocupación.
  * **end\_date:** fecha de finalización de la ocupación.
  * **comments:** notas relevantes sobre la ocupación.
* **relationships**: lista de relaciones de la persona identificable:
  * **relationship\_type**: tipo de relación.
  * **relationship\_to:** nombre del familiar de la person identificable.
  * **source:** link de la fuente con información sobre la relación.
  * **end\_date:** fecha de finalización de la relación.
  * **comments:** notas relevantes sobre la relación.

{% swagger baseUrl="https://www.pepdata.com/api" path="/determine_validation" method="post" summary="Determinación de la validación" %}
{% swagger-description %}
Endpoint para determinar una validación.
{% endswagger-description %}

{% swagger-parameter in="header" name="Authentication" type="string" %}
key \[API\_KEY]
{% endswagger-parameter %}

{% swagger-parameter in="body" name="id" type="string" %}
Id de validación
{% endswagger-parameter %}

{% swagger-parameter in="body" name="id_entity" type="string" %}
Id de la persona u organización identificable correspondiente.&#x20;
{% endswagger-parameter %}

{% swagger-response status="200" description=" La validación ha sido determinada con éxito." %}
```
{
    "version": 0.1,
    "timestamp": 1695805850051,
    "data": {
        "message": "La validación ha sido determinada con éxito."
    }
}
```
{% endswagger-response %}
{% endswagger %}

{% swagger baseUrl="https://www.pepdata.com/api" path="/delete_validation" method="post" summary="Eliminar la validación" %}
{% swagger-description %}
Endpoint para eliminar una validación.
{% endswagger-description %}

{% swagger-parameter in="header" name="Authentication" type="string" %}
key \[API\_KEY]
{% endswagger-parameter %}

{% swagger-parameter in="body" name="id" type="string" %}
Id de validación
{% endswagger-parameter %}

{% swagger-response status="200" description="La validación ha sido eliminada con éxito." %}
```
{
    "version": 0.1,
    "timestamp": 1695806667520,
    "data": {
        "message": "La validación ha sido eliminada con éxito."
    }
}
```
{% endswagger-response %}
{% endswagger %}

{% swagger baseUrl="https://www.pepdata.com/api" path="/apply_rules" method="post" summary="Aplicación de las reglas" %}
{% swagger-description %}
Endpoint para la aplicación de las reglas de validación.
{% endswagger-description %}

{% swagger-parameter in="header" name="Authentication" type="string" %}
key \[API\_KEY]
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Las reglas han empezado a aplicarse." %}
```
{
    "version": 0.1,
    "timestamp": 1695827026005,
    "data": {
        "time_to_conclusion": 1
    }
}
```
{% endswagger-response %}

{% swagger-response status="200: OK" description="No hay validaciones elegibles para aplicar las reglas." %}
```
{
    "version": 0.1,
    "timestamp": 1695827026005,
    "data": {
        "message": "No hay validaciones elegibles para aplicar las reglas."
    }
}
```
{% endswagger-response %}

{% swagger-response status="400: Bad Request" description="Las reglas ya se están aplicando." %}
```
{
    "message": {
        "version": 0.1,
        "timestamp": 1695984451235,
        "message": "Esta operación ya está en marcha. Por favor, espere hasta que se complete."
    }
}
```
{% endswagger-response %}
{% endswagger %}

### Leyenda

* **time\_to\_conclusion**: tiempo estimado en segundos para que se complete la operación.

{% hint style="warning" %}
Se recomienda fuertemente leer la documentación sobre la [aplicación de    las reglas de validación](../a-aplicacao/validacoes/aplicacao-de-regras.md), ya que aplicarlas sin una comprensión adecuada puede conducir a cambios no deseados.
{% endhint %}

{% hint style="info" %}
A [aplicación de la regla](../a-aplicacao/validacoes/aplicacao-de-regras.md) puede tardar varios minutos en completarse, dependiendo del número de validaciones incompletas existentes.
{% endhint %}
