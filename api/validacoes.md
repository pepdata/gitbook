# Validaciones

{% api-method method="post" host="https://www.pepdata.com/api" path="/get\_validations" %}
{% api-method-summary %}
Obtener validaciones
{% endapi-method-summary %}

{% api-method-description %}
Endpoint para obtener validaciones.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authentication" type="string" required=true %}
key \[API\_KEY\]
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="page" type="number" required=false %}
Página de validaciones  
Default: 1
{% endapi-method-parameter %}

{% api-method-parameter name="source" type="string" required=false %}
Origen de las validaciones  
Default: all  
Valores posibles: all, upload, manual
{% endapi-method-parameter %}

{% api-method-parameter name="status" type="string" required=false %}
Estado de validación  
Default: incomplete  
Valores posibles: all, complete, complete\_identified, complete\_not\_identified, complete\_needs\_attention, incomplete
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Validações obtidas com sucesso.
{% endapi-method-response-example-description %}

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
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

### Leyenda

* **id**: id de validación.
* **name**: nombre de validación.
* **birth\_date**: fecha de nacimiento de la validación.
* **id\_country**: país de validación, en el formato [ISO 3166-1 alpha-2](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2).
* **country\_sanctioned**: booleano que describe si el país de validación está sancionado \(1\) o no \(0\).
* **source**: origen de la validación.
* **added\_at**: la fecha a la que se agregó la validación, como el número de milisegundos desde el 1 de enero de 1970 00:00:00 UTC.
* **added\_by**: id del usuario que ha [agregado ](../a-aplicacao/validacoes/#adicao-determinacao-e-estados-de-validacoes)la validación.
* **decision**: booleano que describe si ha habido una coincidencia con una persona identificable \(1\) o no \(0\).
* **id\_iperson**: id de la persona identificable correspondiente. null si no se ha encontrado ninguna coincidencia.
* **determined\_at**: la fecha en la que se determinó la validación, como el número de milisegundos desde el 1 de enero de 1970 00:00:00 UTC.
* **determined\_by**: id del usuario que ha [determinado ](../a-aplicacao/validacoes/#adicao-determinacao-e-estados-de-validacoes)la validación.
* **needs\_attention**: booleano que describe si la validación necesita atención \(1\) o no \(0\).

{% api-method method="post" host="https://www.pepdata.com/api" path="/add\_validation" %}
{% api-method-summary %}
Agregar validación
{% endapi-method-summary %}

{% api-method-description %}
Endpoint para agregar una validación.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authentication" type="string" required=true %}
key \[API\_KEY\]
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="ignore\_duplicates" type="boolean" required=false %}
Instrucción para omitir el control por duplicado.  
Formato: 0/1  
Default: 0
{% endapi-method-parameter %}

{% api-method-parameter name="name" type="string" required=true %}
Nombre de validación
{% endapi-method-parameter %}

{% api-method-parameter name="birth\_date" type="string" required=false %}
Fecha  de nacimiento de la validación.  
Formato: yyyy-mm-dd  
Default: null
{% endapi-method-parameter %}

{% api-method-parameter name="country" type="string" required=false %}
País de la validación.   
Formato: Nombre del país \(véase la nota más abajo\)  
Default: null
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Validação adicionada com sucesso.
{% endapi-method-response-example-description %}

```

{
    "data": {
        "id": "926b7dab-a3af-986f-2137-872adb95260f"
    },
    "version": "0.1",
    "timestamp": 1588599744111
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}
A validação a adicionar já se encontra na base de dados.
{% endapi-method-response-example-description %}

```
{
    "message": "Esta validação parece já existir na base de dados"
    "version": "versão da API",
    "timestamp": X 
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

### Leyenda

* **id**: id de la validación creada.

{% hint style="info" %}
#### Country

* Hay muchas formas diferentes de escribir el nombre de cada país. La aplicación PEPData puede identificar todos los nombres de países presentes en la [Lista dos Estados, territórios y monedas de la Unión Europea](https://publications.europa.eu/code/pt/pt-5000500.htm).Sin embargo, para garantizar una mayor solidez, recomendamos el uso del formato [ISO 3166-1 alpha-2](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2), siempre que sea posible.
{% endhint %}



{% api-method method="post" host="https://www.pepdata.com/api" path="/analyze\_validation" %}
{% api-method-summary %}
Analizar la validación
{% endapi-method-summary %}

{% api-method-description %}
Endpoint para consultar los resultados obtenidos del análisis de una validación.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authentication" type="string" required=true %}
key \[API\_KEY\]
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="id" type="string" required=true %}
Id de la validación
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Resultados del análisis de validación obtenidos con éxito.
{% endapi-method-response-example-description %}

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
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

### Leyenda

* **id**: identificación de la persona identificable.
* **name**: nombre de la persona identificable.
* **birth\_date**: fecha de nacimiento de la persona identificable.
* **score**: [grado de similitud](../glossario/glossario-aplicacao.md#grau-de-semelhanca).

{% api-method method="post" host="https://www.pepdata.com/api" path="/determine\_validation" %}
{% api-method-summary %}
Determinación de la validación
{% endapi-method-summary %}

{% api-method-description %}
Endpoint para enviar una validación.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authentication" type="string" required=true %}
key \[API\_KEY\]
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="id" type="string" required=true %}
Id de validación
{% endapi-method-parameter %}

{% api-method-parameter name="id\_iperson" type="string" required=false %}
Id de la persona identificable correspondiente. 
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
 La validación ha sido enviada con éxito.
{% endapi-method-response-example-description %}

```
{
    "data": {},
    "version": "0.1",
    "timestamp": 1588599744111
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="post" host="https://www.pepdata.com/api" path="/cancel\_validation" %}
{% api-method-summary %}
Cancelación de la determinación de la validación
{% endapi-method-summary %}

{% api-method-description %}
Endpoint para cancelar la determinación de una validación.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authentication" type="string" required=true %}
key \[API\_KEY\]
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="id" type="string" required=true %}
Id de validación
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
La determinación de la validación se ha anulado con éxito.
{% endapi-method-response-example-description %}

```
    "data": {},
    "version": "0.1",
    "timestamp": 1588599744111
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="post" host="https://www.pepdata.com/api" path="/delete\_validation" %}
{% api-method-summary %}
Eliminar la validación
{% endapi-method-summary %}

{% api-method-description %}
Endpoint para eliminar una validación.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authentication" type="string" required=true %}
key \[API\_KEY\]
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="id" type="string" required=true %}
Id de validación
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
La validación ha sido eliminada con éxito
{% endapi-method-response-example-description %}

```
{
    "data": {},
    "version": "0.1",
    "timestamp": 1588599744111
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% hint style="info" %}
Sólo se pueden eliminar las validaciones [incompletas](../a-aplicacao/validacoes/#adicao-determinacao-e-estados-de-validacoes). Si desea eliminar una validación completa, primero debe cancelar su [determinación](../a-aplicacao/validacoes/#adicao-determinacao-e-estados-de-validacoes).
{% endhint %}

{% api-method method="post" host="https://www.pepdata.com/api" path="/apply\_rules" %}
{% api-method-summary %}
Aplicación de las reglas
{% endapi-method-summary %}

{% api-method-description %}
Endpoint para la aplicación de las reglas de validación.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authentication" type="string" required=true %}
key \[API\_KEY\]
{% endapi-method-parameter %}
{% endapi-method-headers %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Las reglas han empezado a aplicarse.
{% endapi-method-response-example-description %}

```
{
    "data": {
        "time_to_conclusion": X
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

* **time\_to\_conclusion**: tiempo **estimado** para completar la aplicación de las reglas, en segundos.

{% hint style="warning" %}
Se recomienda fuertemente leer la documentación sobre la [aplicación de    las reglas de validación](../a-aplicacao/validacoes/aplicacao-de-regras.md), ya que aplicarlas sin una comprensión adecuada puede conducir a cambios no deseados.
{% endhint %}

{% hint style="info" %}
A [aplicación de la regla](../a-aplicacao/validacoes/aplicacao-de-regras.md) puede tardar varios minutos en completarse, dependiendo del número de validaciones incompletas existentes. El tiempo estimado de finalización se devuelve en la respuesta.
{% endhint %}

