# Validaciones

## Obtener validaciones

<mark style="color:green;">`POST`</mark> `https://www.pepdata.com/api/get_validations`

Endpoint para obtener validaciones.

#### Headers

| Name           | Type   | Description     |
| -------------- | ------ | --------------- |
| Authentication | string | key \[API\_KEY] |

#### Request Body

| Name       | Type   | Description                                                                                                                                                                                                                                         |
| ---------- | ------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| page       | number | <p>Página de validaciones<br>Default: 1</p>                                                                                                                                                                                                         |
| source     | string | <p>Origen de las validaciones<br>Default: all<br>Valores posibles: </p><ul><li>all</li><li>upload</li><li>manual</li></ul>                                                                                                                          |
| status     | string | <p>Estado de validación</p><p><br>Predeterminado: incomplete<br></p><p>Valores posibles: </p><ul><li>all</li><li>complete</li><li>complete_identified</li><li>complete_not_identified</li><li>complete_needs_attention</li><li>incomplete</li></ul> |
| id         | string | Id de la validación                                                                                                                                                                                                                                 |
| id\_custom | string | Id personalizable de la validación                                                                                                                                                                                                                  |
| sort\_by   | string | <p>Propiedad utilizada para la ordenación de las validaciones<br><br>Valores posibles:  </p><ul><li>added_at</li><li>determined_at</li><li>name</li></ul>                                                                                           |
| sort\_dir  | string | <p>Ordenación descendente o ascendente de las validaciones<br><br>Valores posibles: </p><ul><li>desc</li><li>asc</li></ul>                                                                                                                          |



{% tabs %}
{% tab title="200 Validaciones obtenidas con éxito." %}
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
{% endtab %}
{% endtabs %}

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

## Exportar Validaciones

<mark style="color:green;">`POST`</mark> `https://www.pepdata.com/api/export_validations`

**Headers**

| Name                                             | Type   | Description     |
| ------------------------------------------------ | ------ | --------------- |
| Authentication<mark style="color:red;">\*</mark> | string | key \[API\_KEY] |

**Body**

| Name                                    | Type   | Description                                                                                                                                                                                                                                               |
| --------------------------------------- | ------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| from<mark style="color:red;">\*</mark>  | int    | Fecha de inicio del filtro, com número de milisegundos desde el 1 de enero de 1970 00:00:00 UTC                                                                                                                                                           |
| until<mark style="color:red;">\*</mark> | int    | Fecha de finalización del filtro, com número de milisegundos desde el 1 de enero de 1970 00:00:00 UTC                                                                                                                                                     |
| status                                  | string | <p>Estado de las validaciones</p><p></p><p>Predeterminado: all</p><p></p><p>Valores posibles: </p><ul><li>all</li><li>complete</li><li>complete_identified,</li><li>complete_not_identified</li><li>complete_needs_attention</li><li>incomplete</li></ul> |
| format                                  | string | <p>Formato del archivo exportado<br><br>Predeterminado: xlsx<br><br>Valores posibles: </p><ul><li>xlsx</li><li>csv</li></ul>                                                                                                                              |
| export\_by                              | string | <p>Exportar validaciones por fecha de adición o fecha de determinación.<br><br>Predeterminado: added_at<br><br>Valores posibles:</p><ul><li>added_at</li><li>determined_at</li></ul>                                                                      |
| timezone                                | string | <p>Zona horaria de fechas utilizadas en los filtros<br><br>Predeterminado: Europe/Lisbon<br></p>                                                                                                                                                          |

**Response**

{% tabs %}
{% tab title="200: OK Archivo exportado con éxito" %}
{% file src="../.gitbook/assets/validaciones de 01-07-2024 a 29-07-2024.xlsx" %}
Ejemplo de archivo de exportación de validaciones
{% endfile %}
{% endtab %}

{% tab title="400: Bad Request Campos obligatorios vacíos" %}
```json
{
   "message": {
        "version": 0.1,
        "timestamp": 1722266342583,
        "message": "El campo 'from' no puede estar vacío."
    }
}
```
{% endtab %}

{% tab title="400: Bad Request Opciones inválidas" %}
<pre class="language-json"><code class="lang-json">{
<strong>   "message": {
</strong>        "version": 0.1,
        "timestamp": 1722266342583,
        "message": "La opción del campo 'status' no es válida."
    }
}
</code></pre>
{% endtab %}
{% endtabs %}

## Agregar validación

<mark style="color:green;">`POST`</mark> `https://www.pepdata.com/api/add_validation`

Endpoint para agregar una validación.

#### Headers

| Name           | Type   | Description     |
| -------------- | ------ | --------------- |
| Authentication | string | key \[API\_KEY] |

#### Request Body

| Name                                   | Type    | Description                                                                                                                                                                                       |
| -------------------------------------- | ------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| ignore\_duplicates                     | boolean | <p>Instrucción para omitir el control por duplicado.<br>Formato: 0/1<br>Default: 0</p>                                                                                                            |
| name<mark style="color:red;">\*</mark> | string  | Nombre de validación                                                                                                                                                                              |
| birth\_date                            | string  | <p>Fecha  de nacimiento de la validación.</p><p><strong>Parámetro solo utilizado en validaciones de personas.</strong><br>Formato: yyyy-mm-dd<br>Default: null</p>                                |
| country\_nationality                   | string  | <p>País de nacionalidad de la validación.</p><p><strong>Parámetro solo utilizado en validaciones de personas.</strong><br>Formato: Nombre del país (véase la nota más abajo)<br>Default: null</p> |
| vatin                                  | string  | <p>Nif de la validación<br>Default: null</p>                                                                                                                                                      |
| id\_custom                             | string  | <p>id personalizable de la validación<br>Default: null</p>                                                                                                                                        |
| country\_residence                     | string  | <p>País de residencia de la validación.</p><p><strong>Parámetro solo utilizado en validaciones de personas.</strong><br>Formato: Nombre del país (véase la nota más abajo)<br>Default: null</p>   |
| type                                   | string  | <p>Tipo de entidad, que puede ser: "individual" u "organization".</p><p>Default: "individual"</p>                                                                                                 |
| country                                | String  | <p>País de la validación.</p><p><strong>Parámetro solo utilizado en validaciones de organizaciones.</strong></p><p>Formato: Nombre del país (véase la nota más abajo)</p><p>Default: null</p>     |

{% tabs %}
{% tab title="200 Validación añadida con éxito." %}
```

{
    "data": {
        "id": "926b7dab-a3af-986f-2137-872adb95260f"
    },
    "version": "0.1",
    "timestamp": 1588599744111
}
```
{% endtab %}

{% tab title="409: Conflict La validación a agregar ya está en la base de datos." %}
```
{
    "message": "Esta validação parece já existir na base de dados"
    "version": 0.1,
    "timestamp": 1696943296957
}
```
{% endtab %}

{% tab title="400: Bad Request Nombre inválido" %}


```json
{
    "message": {
        "version": 0.1,
        "timestamp": 1697017001540,
        "message": "El nombre no es válido. Solo se permiten nombres:  • Solo con caracteres latinos, apóstrofes, espacios, puntos o guiones;"
    }
}
```
{% endtab %}
{% endtabs %}

### Leyenda

* **id**: id de la validación creada.



## Obtener alertas

<mark style="color:green;">`POST`</mark> `https://www.pepdata.com/api/get_alerts`

#### Headers

| Name                                             | Type   | Description     |
| ------------------------------------------------ | ------ | --------------- |
| Authentication<mark style="color:red;">\*</mark> | string | key \[API\_KEY] |

#### Request Body

| Name              | Type         | Description                                                                                                                                                                                           |
| ----------------- | ------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| id\_validation    | string       | Id de la validación                                                                                                                                                                                   |
| ids\_validations  | string array | Array de ids de validaciónes                                                                                                                                                                          |
| status            | string       | <p>Estado de alertas </p><p></p><p>Predeterminado: unresolved </p><p></p><p>Valores posibles: </p><ul><li>all</li><li>resolved</li><li>unresolved</li></ul>                                           |
| from              | int          | Fecha de inicio del filtro, com número de milisegundos desde el 1 de enero de 1970 00:00:00 UTC                                                                                                       |
| until             | int          | Fecha de finalización del filtro, com número de milisegundos desde el 1 de enero de 1970 00:00:00 UTC                                                                                                 |
| include\_comments | boolean      | <p>Parámetro para solicitar información sobre comentarios asociados a los alertas. </p><p></p><p>Predeterminado: false</p><p></p><p>Valores posibles: </p><ul><li>true</li><li>false</li></ul><p></p> |
| page              | number       | <p>Pagina de los alertas.<br>Predeterminado: 1</p>                                                                                                                                                    |

{% tabs %}
{% tab title="200: OK Alertas de validación obtenidas con éxito" %}


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
                "country_nationality": "Japan",
                "comments": [
                    {
                        "id": "ff959c5f-8dbb-130c-f904-b0b02359d113",
                        "comment": "Comentario 1"
                    },
                    {
                        "id": "2b0c4c70-6730-9056-b3c2-bb8dc21125d3",
                        "comment": "Comentario 2"
                    }
                ]
            }
        ],
        "count": 1,
        "total": 1,
        "page": 1,
        "max_results_per_page": 50
    }
}
```
{% endtab %}

{% tab title="400: Bad Request estado de alertas inválido" %}
```
{
    "message": {
        "version": 0.1,
        "timestamp": 1588599744111,
        "message": "El campo 'estado' no es válido."
    }
}
```
{% endtab %}
{% endtabs %}

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
* **comments:** comentarios asociados con la alerta.
  * **id:** id de lo comentario.
  * **comment:** comentario.

{% hint style="info" %}
**country\_nationality, country\_address e country**

Hay múltiples formas diferentes de escribir el nombre de cada país. La aplicación PEPData es capaz de identificar todas las denominaciones de los países presentes en la [Lista de Estados, territorios y monedas de la Unión Europea](https://publications.europa.eu/code/pt/pt-5000500.htm). Sin embargo, para garantizar una mayor robustez, recomendamos utilizar el formato [ISO 3166-1 alpha-2](https://en.wikipedia.org/wiki/ISO\_3166-1\_alpha-2), siempre que sea posible.
{% endhint %}

## Analizar la validación

<mark style="color:green;">`POST`</mark> `https://www.pepdata.com/api/analyze_validation`

Endpoint para consultar los resultados obtenidos del análisis de una validación.

#### Headers

| Name           | Type   | Description     |
| -------------- | ------ | --------------- |
| Authentication | string | key \[API\_KEY] |

#### Request Body

| Name | Type   | Description         |
| ---- | ------ | ------------------- |
| id   | string | Id de la validación |

{% tabs %}
{% tab title="200 Resultados del análisis de validación obtenidos con éxito." %}
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
{% endtab %}

{% tab title="400: Bad Request Validación no encontrada" %}


```json
{
    "message": {
        "version": 0.1,
        "timestamp": 1697017565826,
        "message": "No se encontró la validación"
    }
}
```
{% endtab %}
{% endtabs %}

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

## Determinación de la validación

<mark style="color:green;">`POST`</mark> `https://www.pepdata.com/api/determine_validation`

Endpoint para determinar una validación.

#### Headers

| Name           | Type   | Description     |
| -------------- | ------ | --------------- |
| Authentication | string | key \[API\_KEY] |

#### Request Body

| Name       | Type   | Description                                                     |
| ---------- | ------ | --------------------------------------------------------------- |
| id         | string | Id de validación                                                |
| id\_entity | string | Id de la persona u organización identificable correspondiente.  |

{% tabs %}
{% tab title="200  La validación ha sido determinada con éxito." %}
```
{
    "version": 0.1,
    "timestamp": 1695805850051,
    "data": {
        "message": "La validación ha sido determinada con éxito."
    }
}
```
{% endtab %}

{% tab title="400: Bad Request Validación no encontrada" %}
```
{
    "message": {
        "version": 0.1,
        "timestamp": 1697017565826,
        "message": "No se encontró la validación"
    }
}
```
{% endtab %}
{% endtabs %}

## Eliminar la validación

<mark style="color:green;">`POST`</mark> `https://www.pepdata.com/api/delete_validation`

Endpoint para eliminar una validación.

#### Headers

| Name           | Type   | Description     |
| -------------- | ------ | --------------- |
| Authentication | string | key \[API\_KEY] |

#### Request Body

| Name | Type   | Description      |
| ---- | ------ | ---------------- |
| id   | string | Id de validación |

{% tabs %}
{% tab title="200 La validación ha sido eliminada con éxito." %}
```
{
    "version": 0.1,
    "timestamp": 1695806667520,
    "data": {
        "message": "La validación ha sido eliminada con éxito."
    }
}
```
{% endtab %}

{% tab title="400: Bad Request Validación no encontrada" %}
```
{
    "message": {
        "version": 0.1,
        "timestamp": 1697017565826,
        "message": "No se encontró la validación"
    }
}
```
{% endtab %}
{% endtabs %}

## Aplicación de las reglas

<mark style="color:green;">`POST`</mark> `https://www.pepdata.com/api/apply_rules`

Endpoint para la aplicación de las reglas de validación.

#### Headers

| Name           | Type   | Description     |
| -------------- | ------ | --------------- |
| Authentication | string | key \[API\_KEY] |

{% tabs %}
{% tab title="200: OK Las reglas han empezado a aplicarse." %}
```
{
    "version": 0.1,
    "timestamp": 1695827026005,
    "data": {
        "time_to_conclusion": 1
    }
}
```
{% endtab %}

{% tab title="200: OK No hay validaciones elegibles para aplicar las reglas." %}
```
{
    "version": 0.1,
    "timestamp": 1695827026005,
    "data": {
        "message": "No hay validaciones elegibles para aplicar las reglas."
    }
}
```
{% endtab %}

{% tab title="400: Bad Request Las reglas ya se están aplicando." %}
```
{
    "message": {
        "version": 0.1,
        "timestamp": 1695984451235,
        "message": "Esta operación ya está en marcha. Por favor, espere hasta que se complete."
    }
}
```
{% endtab %}
{% endtabs %}

### Leyenda

* **time\_to\_conclusion**: tiempo estimado en segundos para que se complete la operación.

{% hint style="warning" %}
Se recomienda fuertemente leer la documentación sobre la [aplicación de    las reglas de validación](../a-aplicacao/validacoes/aplicacao-de-regras.md), ya que aplicarlas sin una comprensión adecuada puede conducir a cambios no deseados.
{% endhint %}

{% hint style="info" %}
A [aplicación de la regla](../a-aplicacao/validacoes/aplicacao-de-regras.md) puede tardar varios minutos en completarse, dependiendo del número de validaciones incompletas existentes.
{% endhint %}

## Obtener comentários

<mark style="color:green;">`POST`</mark> `https://www.pepdata.com/api/get_comments`

Endpoint para obtener comentarios.

#### Headers

| Name                                             | Type   | Description     |
| ------------------------------------------------ | ------ | --------------- |
| Authentication<mark style="color:red;">\*</mark> | string | key \[API\_KEY] |

#### Request Body

| Name           | Type   | Description                                                                                                                                             |
| -------------- | ------ | ------------------------------------------------------------------------------------------------------------------------------------------------------- |
| page           | number | <p>Pagina de los comentarios.<br>Predeterminado: 1</p>                                                                                                  |
| type           | string | <p>Tipo de comentarios. </p><p></p><p>Valores posibles:</p><ul><li>determination</li><li>alert</li><li>judicial_process</li><li>adverse_media</li></ul> |
| id\_validation | string | Id de la validación asociada a los comentarios.                                                                                                         |

{% tabs %}
{% tab title="200: OK Comentarios obtenidos con éxito." %}
```
{
    "version": 0.1,
    "timestamp": 1697728294225,
    "data": {
        "count": 2,
        "total": 2,
        "items": [
            {
                "id": "ff959c5f-8dbb-130c-f904-b0b02359d113",
                "comment": "Comentario 1",
                "added_at": 1697704218743,
                "added_by": "António Jesus",
                "id_validation": "a086cf5f-99ad-12d6-7a80-3d9a47a638d0",
                "id_iperson": null,
                "id_validation_alert": "e9b629b3-0566-c119-1de3-a86d8436205d",
                "id_validation_judicial_process": null,
                "id_validation_adverse_media": null,
                "id_added_by": "cd9f4a64-ab25-4efb-bf31-323ee2280095"
            },
            {
                "id": "12cdbdba-685d-73d5-fc35-017ecb17c166",
                "comment": "Comentario 2",
                "added_at": 1697704304926,
                "added_by": "António Jesus",
                "id_validation": "6f95d22f-9751-3d02-0784-0c6288c79c66",
                "id_iperson": "91a1d1c0-bfd0-6e4b-3574-08c40bc9e577",
                "id_validation_alert": null,
                "id_validation_judicial_process": null,
                "id_validation_adverse_media": null,
                "id_added_by": "cd9f4a64-ab25-4efb-bf31-323ee2280095"
            }
        ],
        "page": 1,
        "max_results_per_page": 50
    }
}
```
{% endtab %}

{% tab title="400: Bad Request Tipo de comentarios no válido." %}


```json
{
    "message": {
        "version": 0.1,
        "timestamp": 1697728633346,
        "message": "El tipo de comentario no es valido."
    }
}
```
{% endtab %}
{% endtabs %}

### Leyenda

* **id**: id de lo comentario.
* **comment**: comentario.
* **added\_at**: fecha en que se añadió el comentario, expressada en milisegundos desde el 1 de enero de 1970 a las 1970 00:00:00 UTC.
* **added\_by**: usuario que agregó el comentario.
* **id\_validation**: id de la validación asociado con el comentario.
* **id\_iperson**: id de la persona identificable correspondiente, si el tipo de comentario es "determination".
* **id\_validation\_alert**: id de la alerta de validación correspondiente, si el tipo de comentario es "alert".
* **id\_validation\_judicial\_process:** id del proceso judicial correspondiente, si el tipo de comentario es "judicial\_process".
* **id\_validation\_adverse\_media:** id de la noticia adversa correspondiente, si el tipo de comentario es "adverse\_media".
* **id\_added\_by:** id del usuario que agregó el comentario.

## Añadir un comentario

<mark style="color:green;">`POST`</mark> `https://www.pepdata.com/apiadd_comment`

Endpoint para anãdir un comentario.

#### Headers

| Name                                             | Type   | Description     |
| ------------------------------------------------ | ------ | --------------- |
| Authentication<mark style="color:red;">\*</mark> | string | key \[API\_KEY] |

#### Request Body

| Name                                             | Type   | Description                                                                                                                                                    |
| ------------------------------------------------ | ------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| id\_validation<mark style="color:red;">\*</mark> | string | Id de la validación                                                                                                                                            |
| id\_iperson                                      | string | Id de la persona identificable correspondiente. **Este parámetro es obligatorio si el comentario a agregar se refiere a la identificación de una validación.** |
| comment<mark style="color:red;">\*</mark>        | string | Comentario                                                                                                                                                     |
| id\_validation\_alert                            | string | Id de lo alerta de validación correspondiente. **Este parámetro es obligatorio si el comentario a agregar se refiere a una alerta de validación.**             |
| id\_validation\_judicial\_process                | string | Id de lo proceso judiciale correspondiente. **Este parámetro es obligatorio si el comentario a agregar se refiere a un proceso judicial.**                     |
| id\_validation\_adverse\_media                   | string | Id de la noticia adversa  correspondiente. **Este parámetro es obligatorio si el comentario a agregar se refiere a una noticia adversa.**                      |

{% tabs %}
{% tab title="200: OK Comentario agregado con éxito." %}
```
{
    "version": 0.1,
    "timestamp": 1697730099564,
    "data": {
        "id": "ac33a772-a869-1c36-8569-5cba9cd0542d"
    }
}
```
{% endtab %}

{% tab title="400: Bad Request Validación no encontrada." %}


```json
{
    "message": {
        "version": 0.1,
        "timestamp": 1697730211531,
        "message": "No se encontró la validación."
    }
}
```
{% endtab %}
{% endtabs %}

### Leyenda

* **id**: id de lo comentario agregado.

## Editar un comentario

<mark style="color:green;">`POST`</mark> `https://www.pepdata.com/apiedit_comment`

Endpoint para editar un comentario.

#### Headers

| Name                                             | Type   | Description     |
| ------------------------------------------------ | ------ | --------------- |
| Authentication<mark style="color:red;">\*</mark> | string | key \[API\_KEY] |

#### Request Body

| Name                                      | Type   | Description                  |
| ----------------------------------------- | ------ | ---------------------------- |
| id<mark style="color:red;">\*</mark>      | string | Id de lo comentario a editar |
| comment<mark style="color:red;">\*</mark> | string | Comentario                   |

{% tabs %}
{% tab title="200: OK Comentario editado con éxito." %}
```
{
    "version": 0.1,
    "timestamp": 1697730574961,
    "data": {
        "message": "Comentário editado correctamente."
    }
}
```
{% endtab %}

{% tab title="400: Bad Request Id de comentario no valido." %}


```json
{
    "message": {
        "version": 0.1,
        "timestamp": 1697730622187,
        "message": "No se encontró lo comentario."
    }
}
```
{% endtab %}
{% endtabs %}

## Eliminar un comentário

<mark style="color:green;">`POST`</mark> `https://www.pepdata.com/apidelete_comment`

Endpoint para eliminar un comentario.

#### Headers

| Name                                             | Type   | Description     |
| ------------------------------------------------ | ------ | --------------- |
| Authentication<mark style="color:red;">\*</mark> | string | key \[API\_KEY] |

#### Request Body

| Name                                 | Type   | Description                    |
| ------------------------------------ | ------ | ------------------------------ |
| id<mark style="color:red;">\*</mark> | string | Id de lo comentario a eliminar |

{% tabs %}
{% tab title="200: OK Comentario eliminado con éxito." %}
```
{
    "version": 0.1,
    "timestamp": 1697730574961,
    "data": {
        "message": "Comentario eliminado con éxito."
    }
}
```
{% endtab %}

{% tab title="400: Bad Request Id de comentario no valido." %}


```json
{
    "message": {
        "version": 0.1,
        "timestamp": 1697730622187,
        "message": "No se encontró lo comentario."
    }
}
```
{% endtab %}
{% endtabs %}

## Obtener relaciones de una validación

<mark style="color:green;">`POST`</mark> `https://www.pepdata.com/apiget_validation_relationships`

Endpoint para obtener relaciones de una validación.

#### Headers

| Name                                             | Type   | Description     |
| ------------------------------------------------ | ------ | --------------- |
| Authentication<mark style="color:red;">\*</mark> | string | key \[API\_KEY] |

#### Request Body

| Name                                             | Type   | Description                                              |
| ------------------------------------------------ | ------ | -------------------------------------------------------- |
| id\_validation<mark style="color:red;">\*</mark> | string | Id de la validación                                      |
| page                                             | number | <p>Pagina de las relaciones.</p><p>Predeterminado: 1</p> |

{% tabs %}
{% tab title="200: OK Relaciones obtenidas con éxito" %}
```
{
    "version": 0.1,
    "timestamp": 1697795044035,
    "data": {
        "items": [
            {
                "id": "7f0c97de-6c71-1461-4d9b-da65b4670824",
                "id_relationship": "a86a80bf-0d90-cdfe-1869-726b898cc426",
                "relationship_type": "representative",
                "relationship_to": "António João Soares",
                "id_relationship_to": "df3250ff-382f-c9aa-346e-ef76dd3d333f",
                "id_relationship_from": "6474d5fc-205a-f750-2dd6-24c5d87a5ee5",
                "added_by": "Carlos Araujo",
                "added_at": 1697795029624
            },
            {
                "id": "3b402dbb-ccef-c773-7fac-3225ce7f0e25",
                "id_relationship": "7c5d3c73-b61c-44ae-6d0a-234e1ea2145b",
                "relationship_type": "manager",
                "relationship_to": "José Manuel Silva",
                "id_relationship_to": "3b981423-e1eb-f30f-b4ff-d72b8f34c43a",
                "id_relationship_from": "6474d5fc-205a-f750-2dd6-24c5d87a5ee5",
                "added_by": "Carlos Araujo",
                "added_at": 1697795038487
            }
        ],
        "count": 2,
        "total": 2,
        "page": 1,
        "max_results_per_page": 50
    }
}
```
{% endtab %}

{% tab title="400: Bad Request Validación no encontrada." %}


```json
{
    "message": {
        "version": 0.1,
        "timestamp": 1697795069776,
        "message": "No se encontró la validación."
    }
}
```
{% endtab %}
{% endtabs %}

### Legenda

* **id**: identificador de la tabla de información de relaciones.
* **id\_relationship:** id de la relación.
* **relationship\_type:** tipo de la relación.
* **relationship\_to:** nombre de la validación para la cual se creó la relación.
* **id\_relationship\_to:** id de la validación para la cual se creó la relación.
* **id\_relationship\_from:** id de la validación a partir de la cual se creó la relación.
* **added\_by:** usuario responsable de crear la relación.
* **added\_at:** fecha en que se añadió la relación, expressada en milisegundos desde el 1 de enero de 1970 a las 1970 00:00:00 UTC.

## Agregar una relación a una validación

<mark style="color:green;">`POST`</mark> `https://www.pepdata.com/apiadd_validation_relationship`

Endpoint para agregar una relación a una validación.

#### Headers

| Name                                             | Type   | Description     |
| ------------------------------------------------ | ------ | --------------- |
| Authentication<mark style="color:red;">\*</mark> | string | key \[API\_KEY] |

#### Request Body

| Name                                                         | Type   | Description                                                                                                                                                                      |
| ------------------------------------------------------------ | ------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| organization\_vat\_number<mark style="color:red;">\*</mark>  | string | NIF de la validación a partir de la cual se creará la relación. **Es necesariamente una validación de organización.**                                                            |
| vat\_number<mark style="color:red;">\*</mark>                | string | NIF de la validación para la cual se creará la relación. **Es necesariamente una validación de persona  si el tipo de relación es representative, manager o beneficial\_owner.** |
| position\_in\_organization<mark style="color:red;">\*</mark> | string | <p>Tipo de la relación.</p><p></p><p>Valores posibles:</p><ul><li>representative</li><li>manager</li><li>owner</li><li>beneficial_owner</li></ul>                                |

{% tabs %}
{% tab title="200: OK Relación agregada con éxito." %}
```
{
    "version": 0.1,
    "timestamp": 1697798272664,
    "data": {
        "id": "8e6c7899-7c13-33d1-0538-50faf20f123e"
    }
}
```
{% endtab %}

{% tab title="400: Bad Request Tipo de relación no válido." %}
```json
{
    "message": {
        "version": 0.1,
        "timestamp": 1697798319930,
        "message": "El tipo de relación no es válido."
    }
}
```
{% endtab %}
{% endtabs %}

### Leyenda

* **id**: id de la nueva relación.

## Editar una relación de validación

<mark style="color:green;">`POST`</mark> `https://www.pepdata.com/apiedit_validation_relationship`

Endpoint para editar una relación de validación.

#### Headers

| Name                                             | Type   | Description     |
| ------------------------------------------------ | ------ | --------------- |
| Authentication<mark style="color:red;">\*</mark> | string | key \[API\_KEY] |

#### Request Body

| Name                                                         | Type   | Description                                                                                                                                       |
| ------------------------------------------------------------ | ------ | ------------------------------------------------------------------------------------------------------------------------------------------------- |
| id\_relationship\_info<mark style="color:red;">\*</mark>     | string | identificador de la tabla de información de relaciones asociado con la relación a editar.                                                         |
| position\_in\_organization<mark style="color:red;">\*</mark> | string | <p>Tipo de la relación.</p><p></p><p>Valores posibles:</p><ul><li>representative</li><li>manager</li><li>owner</li><li>beneficial_owner</li></ul> |

{% tabs %}
{% tab title="200: OK Relación editada con éxito." %}
```
{
    "version": 0.1,
    "timestamp": 1697798682365,
    "data": {
        "message": "Relación editada con éxito."
    }
}
```
{% endtab %}

{% tab title="400: Bad Request Tipo de relación no válido." %}
```json
{
    "message": {
        "version": 0.1,
        "timestamp": 1697798319930,
        "message": "El tipo de relación no es válido."
    }
}
```
{% endtab %}
{% endtabs %}

## Eliminar una relación de validación

<mark style="color:green;">`POST`</mark> `https://www.pepdata.com/apidelete_validation_relationship`

Endpoint para eliminar una relación de validación.

#### Headers

| Name                                             | Type   | Description     |
| ------------------------------------------------ | ------ | --------------- |
| Authentication<mark style="color:red;">\*</mark> | string | key \[API\_KEY] |

#### Request Body

| Name                                                     | Type   | Description                                                                                 |
| -------------------------------------------------------- | ------ | ------------------------------------------------------------------------------------------- |
| id\_relationship\_info<mark style="color:red;">\*</mark> | string | identificador de la tabla de información de relaciones asociado con la relación a eliminar. |

{% tabs %}
{% tab title="200: OK Relación eliminada con éxito." %}
```
{
    "version": 0.1,
    "timestamp": 1697798682365,
    "data": {
        "message": "Relación eliminada con éxito."
    }
}
```
{% endtab %}

{% tab title="400: Bad Request Identificador de la tabla de información de relaciones no válido." %}
```json
{
    "message": {
        "version": 0.1,
        "timestamp": 1697798319930,
        "message": "Lo identificador de la tabla de información de relaciones no es válido."
    }
}
```
{% endtab %}
{% endtabs %}
