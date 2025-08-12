# Registros

{% hint style="warning" %}
Esta sección de la API aún está en desarrollo, por lo que puede sufrir cambios considerables. Esta página está en desarrollo.
{% endhint %}

## Obtener registros

<mark style="color:green;">`POST`</mark> `https://www.pepdata.com/api/get_questionnaires`

Endpoint para obtener registros de transacciones y clientes.

#### Headers

| Name                                            | Type   | Description     |
| ----------------------------------------------- | ------ | --------------- |
| Authorization<mark style="color:red;">\*</mark> | string | key \[API\_KEY] |

#### Request Body

| Name                                   | Type    | Description                                                                                                                                                                                                              |
| -------------------------------------- | ------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| id                                     | string  | Id de registro o transacción                                                                                                                                                                                             |
| id\_custom                             | string  | Id personalizable de registro o transacción                                                                                                                                                                              |
| search\_term                           | string  | Término de búsqueda: Buscar en las columnas name, vatin e id\_custom                                                                                                                                                     |
| page                                   | integer | <p>Página de registros o transacciones<br>Default: 1</p>                                                                                                                                                                 |
| type<mark style="color:red;">\*</mark> | string  | <p>Tipo de registros</p><p>Valores aceptados:</p><p><strong>customer</strong></p><p><strong>supplier</strong></p><p><strong>employee</strong></p><p><strong>transaction</strong></p><p><strong>relationship</strong></p> |
| status                                 | string  | <p>Estado de lo registro<br>Valores aceptados:<br><strong>rejected</strong><br><strong>to_decide</strong><br><strong>approved</strong><br><strong>incomplete</strong><br><strong>needs_attention</strong></p>            |

{% tabs %}
{% tab title="200: OK Registros obtenidos con éxito" %}
```
{
    "data": {
        "items": [
            {
                "id": "7dd49ce1-9385-0cd1-7835-828393771ea0",
                "name": "individual",
                "vatin": null,
                "value": "{\"entity_proof\":{\"type\":\"\",\"identification_metadata\":{\"document_number\":\"\",\"document_validity\":\"\",\"is_document_perpetual\":\"\",\"document_issuing_entity\":\"\",\"document_issuing_date\":\"\",\"document_issuing_location\":\"\"},\"documentUpload\":{\"files\":[],\"type\":null,\"source\":null,\"extraData\":null,\"is_trustworthy\":null}},\"personal_data\":{\"name\":\"individual\",\"vatin\":null,\"email\":\"\",\"birth_date\":\"\",\"nationalities\":[],\"birth_place\":\"\",\"documentUpload\":{\"files\":[]}},\"address_data\":{\"type\":null,\"country\":null,\"cep\":\"\",\"address_line_1\":\"\",\"address_line_2\":\"\",\"city\":\"\",\"district\":\"\",\"documentUpload\":{\"files\":[],\"type\":null,\"source\":null,\"extraData\":null,\"is_trustworthy\":null}},\"occupation_data\":{\"type\":null,\"profession\":\"\",\"employer\":\"\",\"eni\":{\"commercial_name\":\"\",\"is_same_address\":null,\"address\":{\"country\":null,\"cep\":\"\",\"address_line_1\":\"\",\"address_line_2\":\"\",\"city\":\"\",\"district\":\"\"},\"cae\":\"\"},\"documentUpload\":{\"files\":[],\"type\":null,\"source\":null,\"extraData\":null,\"is_trustworthy\":null}},\"data_verification\":{\"type\":null,\"client_email\":\"\",\"documentUpload\":{\"files\":[],\"type\":null,\"source\":null,\"extraData\":null,\"is_trustworthy\":null},\"invite_sent\":false},\"adverse_media_data\":{\"adverse_media\":[]},\"suspicion_data\":{\"is_suspect\":null,\"reason\":\"\"},\"questionnaire_id\":\"7dd49ce1-9385-0cd1-7835-828393771ea0\",\"name\":\"individual\"}",
                "type": "individual",
                "main_entity_subtype": "regular",
                "relations": null,
                "added_by": "cd9f4a64-ab25-4efb-bf31-323ee2280095",
                "added_at": 1693489958769,
                "submitted_at": null,
                "submitted_by": null,
                "approval_state": null,
                "approval_change_reason": null,
                "risk": 0,
                "risk_change_reason": null,
                "saved_at": 1693491414116,
                "assigned_to": null,
                "id_invited_user": null,
                "locked_by": null,
                "locked_at": null,
                "invited_submission_by": null,
                "invited_submission_at": null,
                "data_treatment_accepted_at": null,
                "needs_attention": "[{\"reason\":\"onboarding:quick_registration.needs_attention.risk_configurations_changed\",\"needs_attention_date\":\"2025-06-26\",\"old_risk_category_key\":\"medium\",\"new_risk_category_key\":\"low\"}]",
                "id_organization": "6cc1b6c1-33a9-4095-a4a4-aaca0db8d647",
                "id_custom": null,
                "invited_at": null,
                "invited_by_organization_name": null,
                "language": null,
                "organization_id_country": "PT",
                "id_iperson": "ID1",
                "type": "customer",
                "id_questionnaire_data": "4ba763f9-6675-949b-482c-35c689991d65"
                "risk_category: "low"
            }
        ],
        "page": 1,
        "max_results_per_page": 10,
        "count": 1,
        "total": 1
    },
    "version": "0.1",
    "timestamp": 1648132877766
}
```
{% endtab %}
{% endtabs %}

### Leyenda

* **id:** id de registro
* **name:** nombre del registro
* **vatin**: NIF/CIF de registro
* **value:** información de registro
* **entity\_type:** tipo de entidad (individual, colectivo o transaccion)
* **main\_entity\_subtype:** subtipo de entidad (representante, titular real, etc...)
* **relations:** relaciones asociadas al registro.
* **added\_by:** id del usuario que agregó el registro
* **added\_at:** fecha en que se agregó el registro, en milisegundos desde el 1 de enero de 1970 00:00:00 UTC
* **submitted\_at:** fecha en que se envió el registro, en milisegundos desde el 1 de enero de 1970 a las 00:00:00 UTC
* **submitted\_by:** id del usuario que envió el registro
* **approval\_state:** estado de aprobación del registro (0 - en espera de decisión, 1 - aprobado, -1 - rechazado)
* **approval\_change\_reason:** justificación para cambiar el estado de aprobación
* **risk:** valor de riesgo del registro
* **risk\_change\_reason:** justificación del cambio de categoría de riesgo
* **saved\_at:** fecha en que se guardó el registro por última vez, en milisegundos desde el 1 de enero de 1970 a las 00:00:00 UTC
* **assigned\_to:** id del responsable del registro
* **id\_invited\_user:** id del usuario invitado al completar el registro
* **locked\_by:** id del usuario que tiene el registro abierto
* **lock\_at:** fecha en que se abrió el registro por última vez, en milisegundos desde el 1 de enero de 1970 a las 00:00:00 UTC
* **invited\_submission\_by:** id del usuario invitado que aceptó la invitación a rellenar
* **invited\_submission\_at:** fecha en la que se aceptó la invitación de finalización, en forma de número de milisegundos desde el 1 de enero de 1970 00:00:00 UTC
* **data\_treatment\_accepted\_at:** fecha en la que se aceptaron las condiciones de tratamiento de datos del usuario invitado, en forma de número de milisegundos desde el 1 de enero de 1970 00:00:00 UTC
* **needs\_attention:** array de objetos con información sobre el motivo de cada una de las alertas.
* **id\_organization:** id de la organización que creó el registro
* **id\_custom:** id personalizable ingresado por el usuario
* **invited\_at:** fecha en que se envió la invitación a llenar, expresada en milisegundos desde el 1 de enero de 1970 00:00:00 UTC
* **invited\_by\_organization\_name:** nombre de la organización que envió la invitación a rellenar
* **language:** idioma en el que se envió la invitación a completar
* **organization\_id\_country:** país de la organización que creó el registro en formato ISO 3166-1 alpha-2
* **id\_iperson:** id de la persona identificable correspondiente. nulo si no hubo ninguna coincidencia.
* **type:** tipo de registro.
* **id\_questionnaire\_data:** id del registro donde se almacena la información del cuestionario.
* **risk\_category:** categoría en la que caie el valor del riesgo.

## Agregando un registro

<mark style="color:green;">`POST`</mark> `https://www.pepdata.com/api/add_questionnaire`

Endpoint para agregar un registro de clientes y transacciones.

#### Headers

| Name                                            | Type   | Description     |
| ----------------------------------------------- | ------ | --------------- |
| Authorization<mark style="color:red;">\*</mark> | string | key \[API\_KEY] |

#### Request Body

| Name                                   | Type   | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| -------------------------------------- | ------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| name<mark style="color:red;">\*</mark> | string | Nombre del registro o transacción                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| vatin                                  | string | NIF/CIF de registro                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| id\_custom                             | string | id personalizable de registro                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| type<mark style="color:red;">\*</mark> | string | <p>Tipo de registro</p><p></p><p>Valores aceptados: </p><p><strong>individual</strong> (registro de persona física)</p><p><strong>organization</strong> (registro de persona jurídica)</p><p><strong>transaction</strong> (Transacción)</p>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| questionnaire\_data                    |        | <p><strong>Dependiendo de cada tipo de registro</strong>, se necesitan diferentes objetos:</p><p></p><p><em>indivudal</em></p><p><code>{</code></p><p>   <code>"personal_data": {</code></p><p>     <code>"email": "test@test.pt",</code></p><p>     <code>"birth_date": "2010-10-10",</code></p><p>     <code>"nationalities": ["Portugal"],</code></p><p>     <code>"birth_place": "Portugal"</code>  </p><p>   <code>},</code></p><p>   <code>"entity_proof": {</code></p><p>      <code>"identification_metadata": {</code></p><p>      <code>"document_number": 123456789,</code></p><p>      <code>"is_document_perpetual": false,</code></p><p>       <code>"document_validity": "2023-05-20",</code></p><p>       <code>"document_issuing_entity": "Test",</code></p><p>       <code>"document_issuing_date": "2013-05-20",</code></p><p>       <code>"document_issuing_location": "Test"</code></p><p>     <code>},</code></p><p>   <code>},</code></p><p><code>"address_data": {</code></p><p><code>"type": "residence",</code> ** <code>"country":"Portugal",</code></p><p><code>"cep":"1234-567",</code></p><p><code>"address_line_1":"Rua X",</code></p><p><code>"address_line_2":"nº123", "city":"Lisboa",</code></p><p><code>"district":"Lisboa"</code></p><p><code>},</code></p><p>   <code>"suspicion_data": {</code></p><p>     <code>"is_suspect": false,</code></p><p>      <code>"reason": "Test"</code></p><p>   <code>},</code>  </p><p><code>}</code></p><p></p><p>**Valores aceptados:</p><p><strong>residence</strong></p><p><strong>fiscal_residence</strong></p><p><strong>headquarters</strong></p><p></p><p><em>organization</em></p><p><code>{</code></p><p>   <code>"company_data": {</code></p><p><code>"brand_name": "Brand Name",</code></p><p>     <code>"object": "test",</code></p><p>     <code>"caes": ["01111"],</code></p><p>     <code>"country": "Portugal",</code></p><p>     <code>"foundation_date": "2005-02-01",</code></p><p>     <code>"countries_operations": ["Portugal"]</code>  </p><p>   <code>},</code></p><p>   <code>"entity_proof": {</code></p><p>      <code>"national_headquarters": true</code></p><p>   <code>},</code></p><p>   <code>"beneficiary_data": {</code></p><p>      <code>"codigo_rcbe": "123456"</code></p><p>   <code>},</code></p><p><code>"address_data": {</code></p><p><code>"country":"Portugal", "cep":"1234-567", "address_line_1":"Rua X", "address_line_2":"nº 123", "city":"Lisboa", "district":"Lisboa"</code></p><p><code>},</code></p><p>   <code>"suspicion_data": {</code></p><p>     <code>"is_suspect": false,</code></p><p>      <code>"reason": "Test"</code></p><p>   <code>},</code></p><p><code>}</code></p><p></p><p><em>transaction</em></p><p><code>{</code></p><p>   <code>"buyer": {</code></p><p>     <code>"acquisition_purpose": "test purpose",</code></p><p>   <code>},</code></p><p>   <code>"basic_information": {</code></p><p>      <code>"sell_type": "good",</code></p><p>      <code>"description": "test description",</code></p><p>      <code>"observations": "test observations"</code></p><p>   <code>},</code></p><p>   <code>"suspicion_data": {</code></p><p>     <code>"is_suspect": false,</code></p><p>      <code>"reason": "Test"</code></p><p>   <code>},</code></p><p><code>}</code></p> |

{% tabs %}
{% tab title="200: OK Registro o transacción agregado con éxito" %}
```
{
    "version": 0.1,
    "timestamp": 1660060397561,
    "data": {
        "id": "aa199264-c62e-3763-e3a5-68127b070720",
        "risk": 0,
        "risk_category": "low"
    }
}
```
{% endtab %}

{% tab title="409: Conflict Ya existe un registro con el mismo nif/cif o ID personalizado." %}
```
{
    "message": {
        "version": 0.1,
        "timestamp": 1660060761083,
        "message": "Ya existe un registro con el mismo nif/cif o ID personalizado."
    }
}
```
{% endtab %}

{% tab title="409: Conflict (Transaciónes) Ya existe un registro con el mismo identificador personalizado. " %}
```
{
    "message": {
        "version": 0.1,
        "timestamp": 1660060761083,
        "message": "Ya existe un registro con el mismo identificador personalizado."
    }
}
```
{% endtab %}

{% tab title="400: Bad Request NIF/CIF inválido" %}


```json
{
    "message": {
        "version": 0.1,
        "timestamp": 1697022391324,
        "message": "NIF/CIF: El NIF/CIF no es válido. Si es internacional, introduce el código de país al principio. Ej.: FR12345678901 para un número de registro de IVA francés."
    }
}
```
{% endtab %}
{% endtabs %}

### Leyenda

* **id:** Id del registro o transacción creada.
* **risk:** valor de riesgo del registro/transación creado/a.
* **risk\_category:** categoria en la que se inserta el valor de riesgo del registro/transación creado/a.

## Edición de un registro

<mark style="color:green;">`POST`</mark> `https://www.pepdata.com/api/edit_questionnaire`

Endpoint para editar un registro de clientes y transacciones.

#### Headers

| Name                                            | Type   | Description     |
| ----------------------------------------------- | ------ | --------------- |
| Authorization<mark style="color:red;">\*</mark> | string | key \[API\_KEY] |

#### Request Body

| Name                                 | Type   | Description                                                                                                                                                                                  |
| ------------------------------------ | ------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| id<mark style="color:red;">\*</mark> | string | id del registro o transacción                                                                                                                                                                |
| questionnaire\_data                  | json   | <p>Solo puede editar el valor que necesita:</p><p>Compruebe <a href="registros.md#agregando-un-registro">add_questionnaire</a> (questionnaire_data) para ver qué propiedades se aceptan.</p> |

{% tabs %}
{% tab title="200: OK Registro de clientes o transacciones editado" %}
```
{
    "version": 0.1,
    "timestamp": 1660061942863,
    "data": {
        "risk": 0,
        "risk_category": "low"
    }
}
```
{% endtab %}

{% tab title="400: Bad Request Registro de cliente o transación no encontrado" %}


```json
{
    "message": {
        "version": 0.1,
        "timestamp": 1697023313540,
        "message": "No se ha podido encontrar el registro deseado"
    }
}
```
{% endtab %}
{% endtabs %}

### Leyenda

* **risk:** valor de riesgo del registro/transación editado/a.
* **risk\_category:** categoria en la que se inserta el valor de riesgo del registro/transación editado/a.

## Eliminación de registros

<mark style="color:green;">`POST`</mark> `https://www.pepdata.com/api/delete_questionnaire`

Endpoint para eliminar registros de clientes o transacciones.

#### Headers

| Name                                            | Type   | Description     |
| ----------------------------------------------- | ------ | --------------- |
| Authorization<mark style="color:red;">\*</mark> | string | key \[API\_KEY] |

#### Request Body

| Name                                  | Type  | Description                      |
| ------------------------------------- | ----- | -------------------------------- |
| ids<mark style="color:red;">\*</mark> | array | ids de registros o transacciónes |

{% tabs %}
{% tab title="200: OK El registro de clientes o transacciones fue eliminado con éxito" %}


```json
{
    "version": 0.1,
    "timestamp": 1695892485159,
    "data": {
        "message": "Registro(s) eliminado(s) con éxito."
    }
}
```
{% endtab %}

{% tab title="400: Bad Request Registro de cliente o transación no encontrado" %}
```
{
    "message": {
        "version": 0.1,
        "timestamp": 1697023313540,
        "message": "No se ha podido encontrar el registro deseado"
    }
}
```
{% endtab %}
{% endtabs %}

{% hint style="warning" %}
**Importante**: Puede obtener un error al eliminar un registro si tiene dependencias con otros registros.
{% endhint %}

## Anular el envío de un registro

<mark style="color:green;">`POST`</mark> `https://www.pepdata.com/api/unsubmit_questionnaire`

Endpoint para cancelar el envío de un registro de cliente o transacción.

#### Headers

| Name                                            | Type   | Description     |
| ----------------------------------------------- | ------ | --------------- |
| Authorization<mark style="color:red;">\*</mark> | string | key \[API\_KEY] |

#### Request Body

| Name | Type   | Description                   |
| ---- | ------ | ----------------------------- |
| id   | string | id del registro o transacción |

{% tabs %}
{% tab title="200: OK El registro de cliente o de transacciones se ha cancelado con éxito" %}


```json
{
    "version": 0.1,
    "timestamp": 1695893220141,
    "data": {
        "risk": 0,
        "risk_category": "low"
    }
}
```
{% endtab %}

{% tab title="400: Bad Request Registro de cliente o transación no encontrado" %}
```
{
    "message": {
        "version": 0.1,
        "timestamp": 1697023313540,
        "message": "No se ha podido encontrar el registro deseado"
    }
}
```
{% endtab %}
{% endtabs %}

{% hint style="warning" %}
Cancelar el envío recalculará el riesgo de registro. Si tiene una categoría de riesgo configurada manualmente, se perderá.
{% endhint %}

### Leyenda

* **risk:** riesgo recalculado de alta de clientes u operaciones.
* **risk\_category:** categoria en la que se inserta el valor de riesgo recalculado de alta de clientes u operaciones.

## Enviar una invitación para completar el registro

<mark style="color:green;">`POST`</mark> `https://www.pepdata.com/api/send_questionnaire_invite`

Endpoint para enviar una invitación para completar un registro de cliente o transacción.

#### Headers

| Name                                            | Type   | Description     |
| ----------------------------------------------- | ------ | --------------- |
| Authorization<mark style="color:red;">\*</mark> | string | key \[API\_KEY] |

#### Request Body

| Name                                            | Type   | Description                                                                                                                                                                                                                        |
| ----------------------------------------------- | ------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| id<mark style="color:red;">\*</mark>            | string | Id del registro o transacción                                                                                                                                                                                                      |
| client\_email<mark style="color:red;">\*</mark> | string | Correo del cliente invitado                                                                                                                                                                                                        |
| language                                        | string | <p>Idioma en el que debe enviarse la invitación<br></p><p>Predeterminado: pt-PT<br></p><p>Valores aceptados:</p><p><strong>pt-PT</strong> (portugués) </p><p><strong>en</strong> (inglés) </p><p><strong>es</strong> (español)</p> |

{% tabs %}
{% tab title="200: OK Invitación enviada con éxito" %}
```
{
    "version": 0.1,
    "timestamp": 1695997097315,
    "data": {
        "message": "Invitación enviada a {{client_email}}."
    }
}
```
{% endtab %}

{% tab title="400: Bad Request Registro de cliente o transación no encontrado" %}
```
{
    "message": {
        "version": 0.1,
        "timestamp": 1697023313540,
        "message": "No se ha podido encontrar el registro deseado"
    }
}
```
{% endtab %}
{% endtabs %}

## Cancelar una invitación para completar el registro

<mark style="color:green;">`POST`</mark> `https://www.pepdata.com/api/cancel_questionnaire_invite`

Endpoint para cancelar la invitación para completar un registro de cliente o transacción.

#### Headers

| Name                                            | Type   | Description     |
| ----------------------------------------------- | ------ | --------------- |
| Authorization<mark style="color:red;">\*</mark> | string | key \[API\_KEY] |

#### Request Body

| Name                                            | Type   | Description                   |
| ----------------------------------------------- | ------ | ----------------------------- |
| id<mark style="color:red;">\*</mark>            | string | Id del registro o transacción |
| client\_email<mark style="color:red;">\*</mark> | string | Correo del cliente invitado   |

{% tabs %}
{% tab title="200: OK Invitación cancelada con éxito" %}
```
{
    "version": 0.1,
    "timestamp": 1695997713238,
    "data": {
        "message": "La invitación de {{client_email}} fue cancelada."
    }
}
```
{% endtab %}

{% tab title="400: Bad Request Registro de cliente o transación no encontrado" %}
```
{
    "message": {
        "version": 0.1,
        "timestamp": 1697023313540,
        "message": "No se ha podido encontrar el registro deseado"
    }
}
```
{% endtab %}
{% endtabs %}

## Asignar un usuario a un registro

<mark style="color:green;">`POST`</mark> `https://www.pepdata.com/api/assign_user_to_questionnaire`

Endpoint para asignar un usuario a un registro de cliente o transacción.

#### Headers

| Name                                             | Type   | Description     |
| ------------------------------------------------ | ------ | --------------- |
| Authorization <mark style="color:red;">\*</mark> | string | key \[API\_KEY] |

#### Request Body

| Name                                       | Type   | Description                   |
| ------------------------------------------ | ------ | ----------------------------- |
| id<mark style="color:red;">\*</mark>       | string | Id del registro o transacción |
| id\_user<mark style="color:red;">\*</mark> | string | Id de usuario                 |

{% tabs %}
{% tab title="200: OK El usuario se ha asignado correctamente al registro de cliente o transacción." %}
```
{
    "version": 0.1,
    "timestamp": 1695999232282,
    "data": {
        "message": "Responsable modificado a {{user_name}}."
    }
}
```
{% endtab %}

{% tab title="400: Bad Request Registro de cliente o transación no encontrado" %}
```
{
    "message": {
        "version": 0.1,
        "timestamp": 1697023313540,
        "message": "No se ha podido encontrar el registro deseado"
    }
}
```
{% endtab %}
{% endtabs %}

## Asignar departamentos a un registro

<mark style="color:green;">`POST`</mark> `https://www.pepdata.com/api/assign_departments_to_questionnaire`

Endpoint para asignar departamentos a un cliente o registro de transacciones.

#### Headers

| Name                                            | Type   | Description     |
| ----------------------------------------------- | ------ | --------------- |
| Authorization<mark style="color:red;">\*</mark> | string | key \[API\_KEY] |

#### Request Body

| Name                                          | Type   | Description                                                            |
| --------------------------------------------- | ------ | ---------------------------------------------------------------------- |
| id                                            | string | Id del registro o transacción                                          |
| departments<mark style="color:red;">\*</mark> | json   | <p>Array de departamentos<br><br>Ejemplo:<br>["Financiero"]</p><p></p> |

{% tabs %}
{% tab title="200: OK Se han asignado departamentos al registro de clientes o transacciones con éxito." %}
```
{
    "version": 0.1,
    "timestamp": 1696001921643,
    "data": {
        "message": "Departamentos asignados con éxito."
    }
}
```
{% endtab %}

{% tab title="400: Bad Request Departamentos inválidos" %}


```json
{
    "message": {
        "version": 0.1,
        "timestamp": 1697025478223,
        "message": "Se ha producido un error al asociar los departamentos con el registro. Compruebe que los departamentos que va a asociar existen en la página \\'Configuraciones\\'."
    }
}
```
{% endtab %}
{% endtabs %}

## Editar el estado de aprobación de un registro

<mark style="color:green;">`POST`</mark> `https://www.pepdata.com/api/edit_questionnaire_approval_state`

Endpoint para editar el estado de aprobación de un cliente o registro de transacción.

#### Headers

| Name                                            | Type   | Description     |
| ----------------------------------------------- | ------ | --------------- |
| Authorization<mark style="color:red;">\*</mark> | string | key \[API\_KEY] |

#### Request Body

| Name                                                       | Type   | Description                                                                                                |
| ---------------------------------------------------------- | ------ | ---------------------------------------------------------------------------------------------------------- |
| id<mark style="color:red;">\*</mark>                       | string | id del regristro o transacción                                                                             |
| approval\_state<mark style="color:red;">\*</mark>          | string | <p>Estado de aprobación<br></p><p>Valores aceptados:<br>-1 (Rechazado)<br>0 (Indeciso)<br>1 (aprobado)</p> |
| approval\_change\_reason<mark style="color:red;">\*</mark> | string | Justificación para cambiar el estado de aprobación                                                         |

{% tabs %}
{% tab title="200: OK El estado de aprobación del registro de clientes o de la transacción se ha cambiado correctamente." %}
```
{
    "version": 0.1,
    "timestamp": 1696002523053,
    "data": {
        "message": "Estado de aprobación cambiado con éxito."
    }
}
```
{% endtab %}

{% tab title="400: Bad Request Registro de cliente o transación no encontrado" %}
```
{
    "message": {
        "version": 0.1,
        "timestamp": 1697023313540,
        "message": "No se ha podido encontrar el registro deseado"
    }
}
```
{% endtab %}
{% endtabs %}

## Revertir el riesgo de un registro

<mark style="color:green;">`POST`</mark> `https://www.pepdata.com/api/revert_questionnaire_risk`

Endpoint para revertir el riesgo actual de un cliente o registro de transacciones.

#### Headers

| Name                                            | Type   | Description     |
| ----------------------------------------------- | ------ | --------------- |
| Authorization<mark style="color:red;">\*</mark> | string | key \[API\_KEY] |

#### Request Body

| Name                                 | Type   | Description                   |
| ------------------------------------ | ------ | ----------------------------- |
| id<mark style="color:red;">\*</mark> | string | id del registro o transacción |

{% tabs %}
{% tab title="200: OK Se revirtió con éxito el riesgo del registro de clientes o transacciones" %}


```json
{
    "version": 0.1,
    "timestamp": 1696238603806,
    "data": {
        "risk": 0,
        "risk_category": "low"
    }
}
```
{% endtab %}

{% tab title="400: Bad Request Registro de cliente o transación no encontrado" %}
```
{
    "message": {
        "version": 0.1,
        "timestamp": 1697023313540,
        "message": "No se ha podido encontrar el registro deseado"
    }
}
```
{% endtab %}
{% endtabs %}

### Leyenda

* **risk:** riesgo de alta de clientes u operaciones.
* **risk\_category:** categoria en la que se inserta el valor de riesgo de alta de clientes u operaciones.

## Restablecer el estado "Necesita atención" de un registro

<mark style="color:green;">`POST`</mark> `https://www.pepdata.com/api/reset_questionnaire_needs_attention`

Endpoint para restablecer el estado "Necesita atención" de un registro de cliente o transacción.

#### Headers

| Name                                            | Type   | Description     |
| ----------------------------------------------- | ------ | --------------- |
| Authorization<mark style="color:red;">\*</mark> | string | key \[API\_KEY] |

#### Request Body

| Name | Type   | Description                   |
| ---- | ------ | ----------------------------- |
| id   | string | Id del registro o transacción |

{% tabs %}
{% tab title="200: OK El estado "Necesita atención" del registro de clientes o de transacciones se ha restablecido correctamente." %}


```json
{
    "version": 0.1,
    "timestamp": 1696239199674,
    "data": {
        "message": "El estado 'Necesita atención' se ha restablecido correctamente."
    }
}
```
{% endtab %}

{% tab title="400: Bad Request Registro de cliente o transación no encontrado" %}
```
{
    "message": {
        "version": 0.1,
        "timestamp": 1697023313540,
        "message": "No se ha podido encontrar el registro deseado"
    }
}
```
{% endtab %}
{% endtabs %}

## Entregar los registros

<mark style="color:green;">`POST`</mark> `https://www.pepdata.com/api/submit_questionnaires`

Endpoint que entrega automáticamente todos los registros no enviados.\*

**\*Esta operación está limitada a 8000 registros a la vez.**

#### Headers

| Name                                            | Type   | Description     |
| ----------------------------------------------- | ------ | --------------- |
| Authorization<mark style="color:red;">\*</mark> | string | key \[API\_KEY] |

#### Request Body

| Name                                   | Type   | Description                                                                                                                         |
| -------------------------------------- | ------ | ----------------------------------------------------------------------------------------------------------------------------------- |
| type<mark style="color:red;">\*</mark> | string | <p>Tipo de los registros a entregar</p><p>Valores aceptados: </p><p><strong>customers</strong><br><strong>transactions</strong></p> |

{% tabs %}
{% tab title="200: OK Los registros se enviaron exitosamente." %}


```json
{
    "version": 0.1,
    "timestamp": 1695983552463,
    "data": {
        "time_to_conclusion": 1
    }
}
```
{% endtab %}

{% tab title="400: Bad Request El tipo de registros no es válido." %}
```
{
    "message": {
        "version": 0.1,
        "timestamp": 1708706955487,
        "message": "El tipo no es válido."
    }
}
```
{% endtab %}
{% endtabs %}

### Leyenda

* **time\_to\_conclusion:** tiempo estimado en segundos para que se complete la operación.

## Exportar el informe de riesgos

<mark style="color:green;">`POST`</mark> `https://www.pepdata.com/api/export_risk_pdf`

Endpoint para obtener el informe de riesgos de un registro en formato pdf.

#### Headers

| Name                                            | Type   | Description     |
| ----------------------------------------------- | ------ | --------------- |
| Authorization<mark style="color:red;">\*</mark> | string | key \[API\_KEY] |

#### Request Body

| Name                                 | Type   | Description                     |
| ------------------------------------ | ------ | ------------------------------- |
| id<mark style="color:red;">\*</mark> | string | Id de lo registro o transacción |

**Response**
