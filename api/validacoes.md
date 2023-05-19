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

{% swagger-response status="200" description="Validações obtidas com sucesso." %}
```
{
    "data": {
        "items": [
            {
                "id": "2a206d4a-0a5d-4a04-9a0c-cadae6e2cffa", 
                "name": "Lisa Fidalgo Corte-Real",
                "birth_date": "01-08-1986",
                "id_country": "PT",
                "source": "Manual",
                "added_at": 1588003603593,
                "added_by": "839a5871-fa0e-470a-af42-9110f8ef5b27",
                "decision": null,
                "id_iperson": null,
                "determined_at": null,
                "determined_by": null,
                "needs_attention": 0
            },
            {
                "id": "01a0ae72-bff9-47df-a7ec-843a7524d67e", 
                "name": "Baltasar Lousada Vieira",
                "birth_date": null,
                "id_country": null,
                "source": "Automatic",
                "added_at": 1588008603595,
                "added_by": "839a5871-fa0e-470a-af42-9110f8ef5b27",,
                "decision": 1,
                "id_iperson": "d37903e9-589b-4db8-a9e0-efd69d89bf6b",
                "determined_at": 1588009503831,
                "determined_by": "0d874a7f-a94b-4b0c-ba48-47a278f12065",
                "needs_attention": 0
            }
        ],
        "page": 1,
        "max_results_per_page": 50
        "total": 2
    },
    "version": "0.1",
    "timestamp": 1588599744111
}
```
{% endswagger-response %}
{% endswagger %}

### Leyenda

* **id**: id de validación.
* **vatin:** nif de la validación.
* **name**: nombre de validación.
* **birth\_date**: fecha de nacimiento de la validación.
* **id\_country\_nationality**: país de nacionalidad de la validación, en el formato [ISO 3166-1 alpha-2](https://en.wikipedia.org/wiki/ISO\_3166-1\_alpha-2).
* **id\_country\_address**: país de residencia de la validación, en el formato [ISO 3166-1 alpha-2](https://en.wikipedia.org/wiki/ISO\_3166-1\_alpha-2).
* **country\_sanctioned**: booleano que describe si el país de validación está sancionado (1) o no (0).
* **source**: origen de la validación.
* **added\_at**: la fecha a la que se agregó la validación, como el número de milisegundos desde el 1 de enero de 1970 00:00:00 UTC.
* **added\_by**: id del usuario que ha [agregado ](../a-aplicacao/validacoes/#adicao-determinacao-e-estados-de-validacoes)la validación.
* **decision**: booleano que describe si ha habido una coincidencia con una persona identificable (1) o no (0).
* **id\_iperson**: id de la persona identificable correspondiente. null si no se ha encontrado ninguna coincidencia.
* **determined\_at**: la fecha en la que se determinó la validación, como el número de milisegundos desde el 1 de enero de 1970 00:00:00 UTC.
* **determined\_by**: id del usuario que ha [determinado ](../a-aplicacao/validacoes/#adicao-determinacao-e-estados-de-validacoes)la validación.
* **needs\_attention**: booleano que describe si la validación necesita atención (1) o no (0).

{% swagger baseUrl="https://www.pepdata.com/api" path="/add_validation" method="post" summary="Agregar validación" %}
{% swagger-description %}
Endpoint para agregar una validación.
{% endswagger-description %}

{% swagger-parameter in="header" name="Authentication" type="string" %}
key [API_KEY]
{% endswagger-parameter %}

{% swagger-parameter in="body" name="ignore_duplicates" type="boolean" %}
Instrucción para omitir el control por duplicado.

\


Formato: 0/1

\


Default: 0
{% endswagger-parameter %}

{% swagger-parameter in="body" name="vatin" type="string" %}
Nif de la validación

\


Default: null
{% endswagger-parameter %}

{% swagger-parameter in="body" name="name" type="string" %}
Nombre de validación
{% endswagger-parameter %}

{% swagger-parameter in="body" name="birth_date" type="string" %}
Fecha  de nacimiento de la validación.

\


Formato: yyyy-mm-dd

\


Default: null
{% endswagger-parameter %}

{% swagger-parameter in="body" name="country_nationality" type="string" %}
País de nacionalidad de la validación. 

\


Formato: Nombre del país (véase la nota más abajo)

\


Default: null
{% endswagger-parameter %}

{% swagger-parameter in="body" name="country_address" type="string" %}
País de residencia de la validación. 

\


Formato: Nombre del país (véase la nota más abajo)

\


Default: null
{% endswagger-parameter %}

{% swagger-parameter in="body" name="id_custom" type="string" %}
id personalizable de la validación

\


Default: null
{% endswagger-parameter %}

{% swagger-response status="200" description="Validação adicionada com sucesso." %}
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

{% swagger-response status="400" description="A validação a adicionar já se encontra na base de dados." %}
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
**id\_country\_nationality y id\_country\_address**&#x20;

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

{% swagger-parameter in="body" name="id_iperson" type="string" %}
Id de la persona identificable correspondiente. 
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
