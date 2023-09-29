# Registros

{% hint style="warning" %}
Esta sección de la API aún está en desarrollo, por lo que puede sufrir cambios considerables. Esta página está en desarrollo.
{% endhint %}

{% swagger method="post" path="" baseUrl="https://www.pepdata.com/api/get_questionnaires" summary="Obtener registros" %}
{% swagger-description %}
Endpoint para obtener registros de transacciones y clientes.
{% endswagger-description %}

{% swagger-parameter in="header" name="Authorization" type="string" required="true" %}
key \[API\_KEY]
{% endswagger-parameter %}

{% swagger-parameter in="body" name="id" type="string" %}
Id de registro o transacción
{% endswagger-parameter %}

{% swagger-parameter in="body" name="id_custom" type="string" %}
Id personalizable de registro o transacción
{% endswagger-parameter %}

{% swagger-parameter in="body" name="search_term" type="string" %}
Término de búsqueda: Buscar en las columnas name, vatin e id\_custom
{% endswagger-parameter %}

{% swagger-parameter in="body" name="page" type="integer" %}
Página de registros o transacciones\
Default: 1
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Registros obtenidos con éxito" %}
```
{
    "data": {
        "items": [
            {
                "id": "7dd49ce1-9385-0cd1-7835-828393771ea0",
                "name": "individual",
                "vatin": null,
                "value": "{\"entity_proof\":{\"type\":\"\",\"identification_metadata\":{\"document_number\":\"\",\"document_validity\":\"\",\"is_document_perpetual\":\"\",\"document_issuing_entity\":\"\",\"document_issuing_date\":\"\",\"document_issuing_location\":\"\"},\"documentUpload\":{\"files\":[],\"type\":null,\"source\":null,\"extraData\":null,\"is_trustworthy\":null}},\"personal_data\":{\"name\":\"individual\",\"vatin\":null,\"email\":\"\",\"birth_date\":\"\",\"nationalities\":[],\"birth_place\":\"\",\"documentUpload\":{\"files\":[]}},\"address_data\":{\"type\":null,\"country\":null,\"cep\":\"\",\"address_line_1\":\"\",\"address_line_2\":\"\",\"city\":\"\",\"district\":\"\",\"documentUpload\":{\"files\":[],\"type\":null,\"source\":null,\"extraData\":null,\"is_trustworthy\":null}},\"occupation_data\":{\"type\":null,\"profession\":\"\",\"employer\":\"\",\"eni\":{\"commercial_name\":\"\",\"is_same_address\":null,\"address\":{\"country\":null,\"cep\":\"\",\"address_line_1\":\"\",\"address_line_2\":\"\",\"city\":\"\",\"district\":\"\"},\"cae\":\"\"},\"documentUpload\":{\"files\":[],\"type\":null,\"source\":null,\"extraData\":null,\"is_trustworthy\":null}},\"data_verification\":{\"type\":null,\"client_email\":\"\",\"documentUpload\":{\"files\":[],\"type\":null,\"source\":null,\"extraData\":null,\"is_trustworthy\":null},\"invite_sent\":false},\"adverse_media_data\":{\"adverse_media\":[]},\"suspicion_data\":{\"is_suspect\":null,\"reason\":\"\"},\"questionnaire_id\":\"7dd49ce1-9385-0cd1-7835-828393771ea0\",\"name\":\"individual\"}",
                "version": "1",
                "type": "individual",
                "subtype": "regular",
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
                "accepted_by": null,
                "accepted_at": null,
                "data_treatment_accepted_at": null,
                "needs_attention": null,
                "id_organization": "6cc1b6c1-33a9-4095-a4a4-aaca0db8d647",
                "id_custom": null,
                "invited_at": null,
                "invited_by_organization_name": null,
                "language": null,
                "id_country": "PT",
                "id_iperson": "ID1",
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
{% endswagger-response %}
{% endswagger %}

### Leyenda

* **id:** id de registro
* **name:** nombre del registro
* **vatin**: NIF/CIF de registro
* **value:** información de registro
* **version:** versión del cuestionario
* **type:** tipo de registro (individual, colectivo o transaccion)
* **subtype:** subtipo de registro (representante, titular real, etc...)
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
* **accepted\_by:** id del usuario invitado que aceptó la invitación a rellenar
* **accepted\_at:** fecha en la que se aceptó la invitación de finalización, en forma de número de milisegundos desde el 1 de enero de 1970 00:00:00 UTC
* **data\_treatment\_accepted\_at:** fecha en la que se aceptaron las condiciones de tratamiento de datos del usuario invitado, en forma de número de milisegundos desde el 1 de enero de 1970 00:00:00 UTC
* **needs\_attention:** booleano que describe si el registro necesita atención
* **id\_organization:** id de la organización que creó el registro
* **id\_custom:** id personalizable ingresado por el usuario
* **invited\_at:** fecha en que se envió la invitación a llenar, expresada en milisegundos desde el 1 de enero de 1970 00:00:00 UTC
* **invited\_by\_organization\_name:** nombre de la organización que envió la invitación a rellenar
* **language:** idioma en el que se envió la invitación a completar
* **id\_country:** país de la organización que creó el registro en formato ISO 3166-1 alpha-2
* **id\_iperson:** id de la persona identificable correspondiente. nulo si no hubo ninguna coincidencia.
* **risk\_category:** categoría en la que caie el valor del riesgo.

{% swagger method="post" path="" baseUrl="https://www.pepdata.com/api/add_questionnaire" summary="Agregando un registro" %}
{% swagger-description %}
Endpoint para agregar un registro de clientes y transacciones.
{% endswagger-description %}

{% swagger-parameter in="header" name="Authorization" type="string" required="true" %}
key \[API\_KEY]
{% endswagger-parameter %}

{% swagger-parameter in="body" name="name" type="string" required="true" %}
Nombre del registro o transacción
{% endswagger-parameter %}

{% swagger-parameter in="body" name="vatin" type="string" %}
NIF/CIF de registro
{% endswagger-parameter %}

{% swagger-parameter in="body" name="id_custom" type="string" %}
id personalizable de registro
{% endswagger-parameter %}

{% swagger-parameter in="body" name="type" type="string" required="true" %}
Tipo de registro



Valores aceptados:&#x20;

**individual** (registro de persona física)

**organization** (registro de persona jurídica)

**transaction** (Transacción)
{% endswagger-parameter %}

{% swagger-parameter in="body" name="questionnaire_data" type="" %}
**Dependiendo de cada tipo de registro**, se necesitan diferentes objetos:



_indivudal_

`{`

&#x20;  `"personal_data": {`

&#x20;    `"email": "test@test.pt",`

&#x20;    `"birth_date": "2010-10-10",`

&#x20;    `"nationalities": ["Portugal"],`

&#x20;    `"birth_place": "Portugal"` &#x20;

&#x20;  `},`

&#x20;  `"entity_proof": {`

&#x20;     `"identification_metadata": {`

&#x20;     `"document_number": 123456789,`

&#x20;     `"is_document_perpetual": false,`

&#x20;      `"document_validity": "2023-05-20",`

&#x20;      `"document_issuing_entity": "Test",`

&#x20;      `"document_issuing_date": "2013-05-20",`

&#x20;      `"document_issuing_location": "Test"`

&#x20;    `},`

&#x20;  `},`

&#x20;  `"suspicion_data": {`

&#x20;    `"is_suspect": false,`

&#x20;     `"reason": "Test"`

&#x20;  `},` &#x20;

`}`



_organization_

`{`

&#x20;  `"company_data": {`

&#x20;    `"object": "test",`

&#x20;    `"caes": ["01111"],`

&#x20;    `"country": "Portugal",`

&#x20;    `"foundation_date": "2005-02-01",`

&#x20;    `"countries_operations": ["Portugal"]` &#x20;

&#x20;  `},`

&#x20;  `"entity_proof": {`

&#x20;     `"national_headquarters": true`

&#x20;  `},`

&#x20;  `"beneficiary_data": {`

&#x20;     `"codigo_rcbe": "123456"`

&#x20;  `},`

&#x20;  `"suspicion_data": {`

&#x20;    `"is_suspect": false,`

&#x20;     `"reason": "Test"`

&#x20;  `},`

`}`



_transaction_

`{`

&#x20;  `"buyer": {`

&#x20;    `"acquisition_purpose": "test purpose",`

&#x20;  `},`

&#x20;  `"basic_information": {`

&#x20;     `"sell_type": "good",`

&#x20;     `"description": "test description",`

&#x20;     `"observations": "test observations"`

&#x20;  `},`

&#x20;  `"suspicion_data": {`

&#x20;    `"is_suspect": false,`

&#x20;     `"reason": "Test"`

&#x20;  `},`

`}`


{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Registro o transacción agregado con éxito" %}
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
{% endswagger-response %}

{% swagger-response status="400: Bad Request" description="El registro no fue creado, ya existe en la lista" %}
```
{
    "message": {
        "version": 0.1,
        "timestamp": 1660060761083,
        "message": "El registro no se ha creado, ya existe en la lista."
    }
}
```
{% endswagger-response %}
{% endswagger %}

### Leyenda

* **id:** Id del registro o transacción creada.
* **risk:** valor de riesgo del registro/transación creado/a.
* **risk\_category:** categoria en la que se inserta el valor de riesgo del registro/transación creado/a.

{% swagger method="post" path="" baseUrl="https://www.pepdata.com/api/edit_questionnaire" summary="Edición de un registro" %}
{% swagger-description %}
Endpoint para editar un registro de clientes y transacciones.
{% endswagger-description %}

{% swagger-parameter in="header" name="Authorization" type="string" required="true" %}
key \[API\_KEY]
{% endswagger-parameter %}

{% swagger-parameter in="body" name="id" type="string" required="true" %}
id del registro o transacción
{% endswagger-parameter %}

{% swagger-parameter in="body" name="questionnaire_data" type="json" %}
Solo puede editar el valor que necesita:

Compruebe [add\_questionnaire](registros.md#agregando-un-registro) (questionnaire\_data) para ver qué propiedades se aceptan.
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Registro de clientes o transacciones editado" %}
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
{% endswagger-response %}
{% endswagger %}

### Leyenda

* **risk:** valor de riesgo del registro/transación editado/a.
* **risk\_category:** categoria en la que se inserta el valor de riesgo del registro/transación editado/a.

{% swagger method="post" path="" baseUrl="https://www.pepdata.com/api/delete_questionnaire" summary="Eliminación de un registro" %}
{% swagger-description %}
Endpoint para eliminar un registro de clientes o transacciones.
{% endswagger-description %}

{% swagger-parameter in="header" name="Authorization" type="string" required="true" %}
key \[API\_KEY]
{% endswagger-parameter %}

{% swagger-parameter in="body" name="id" required="true" type="string" %}
id del registro o transacción
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="El registro de clientes o transacciones fue eliminado con éxito" %}


```json
{
    "version": 0.1,
    "timestamp": 1695892485159,
    "data": {
        "message": "El registro fue eliminado con éxito."
    }
}
```
{% endswagger-response %}
{% endswagger %}

{% hint style="warning" %}
**Importante**: Puede obtener un error al eliminar un registro si tiene dependencias con otros registros.
{% endhint %}

{% swagger method="post" path="" baseUrl="https://www.pepdata.com/api/unsubmit_questionnaire" summary="Anular el envío de un registro" %}
{% swagger-description %}
Endpoint para cancelar el envío de un registro de cliente o transacción.
{% endswagger-description %}

{% swagger-parameter in="header" name="Authorization" type="string" required="true" %}
key \[API\_KEY]
{% endswagger-parameter %}

{% swagger-parameter in="body" name="id" type="string" %}
id del registro o transacción
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="El registro de cliente o de transacciones se ha cancelado con éxito" %}


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
{% endswagger-response %}
{% endswagger %}

{% hint style="warning" %}
Cancelar el envío recalculará el riesgo de registro. Si tiene una categoría de riesgo configurada manualmente, se perderá.
{% endhint %}

### Leyenda

* **risk:** riesgo recalculado de alta de clientes u operaciones.
* **risk\_category:** categoria en la que se inserta el valor de riesgo recalculado de alta de clientes u operaciones.

{% swagger method="post" path="" baseUrl="https://www.pepdata.com/api/send_questionnaire_invite" summary="Enviar una invitación para completar el registro" %}
{% swagger-description %}
Endpoint para enviar una invitación para completar un registro de cliente o transacción.
{% endswagger-description %}

{% swagger-parameter in="header" name="Authorization" type="string" required="true" %}
key \[API\_KEY]
{% endswagger-parameter %}

{% swagger-parameter in="body" required="true" name="id" type="string" %}
Id del registro o transacción
{% endswagger-parameter %}

{% swagger-parameter in="body" name="client_email" required="true" type="string" %}
Correo del cliente invitado
{% endswagger-parameter %}

{% swagger-parameter in="body" name="language" type="string" required="false" %}
Idioma en el que debe enviarse la invitación\


Predeterminado: pt-PT\


Valores aceptados:

**pt-PT** (portugués)&#x20;

**en** (inglés)&#x20;

**es** (español)
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Invitación enviada con éxito" %}
```
{
    "version": 0.1,
    "timestamp": 1695997097315,
    "data": {
        "message": "Invitación enviada a {{client_email}}."
    }
}
```
{% endswagger-response %}
{% endswagger %}

{% swagger method="post" path="" baseUrl="https://www.pepdata.com/api/cancel_questionnaire_invite" summary="Cancelar una invitación para completar el registro" %}
{% swagger-description %}
Endpoint para cancelar la invitación para completar un registro de cliente o transacción.
{% endswagger-description %}

{% swagger-parameter in="header" name="Authorization" type="string" required="true" %}
key \[API\_KEY]
{% endswagger-parameter %}

{% swagger-parameter in="body" name="id" type="string" required="true" %}
Id del registro o transacción
{% endswagger-parameter %}

{% swagger-parameter in="body" name="client_email" required="true" type="string" %}
Correo del cliente invitado
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Invitación cancelada con éxito" %}
```
{
    "version": 0.1,
    "timestamp": 1695997713238,
    "data": {
        "message": "La invitación de {{client_email}} fue cancelada."
    }
}
```
{% endswagger-response %}
{% endswagger %}

{% swagger method="post" path="" baseUrl="https://www.pepdata.com/api/assign_user_to_questionnaire" summary="Asignar un usuario a un registro" %}
{% swagger-description %}
Endpoint para asignar un usuario a un registro de cliente o transacción.
{% endswagger-description %}

{% swagger-parameter in="header" name="Authorization " type="string" required="true" %}
key \[API\_KEY]
{% endswagger-parameter %}

{% swagger-parameter in="body" name="id" type="string" required="true" %}
Id del registro o transacción
{% endswagger-parameter %}

{% swagger-parameter in="body" name="id_user" type="string" required="true" %}
Id de usuario
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="El usuario se ha asignado correctamente al registro de cliente o transacción." %}

{% endswagger-response %}
{% endswagger %}

{% swagger method="post" path="" baseUrl="https://www.pepdata.com/api/assign_departments_to_questionnaire" summary="Asignar departamentos a un registro" %}
{% swagger-description %}
Endpoint para asignar departamentos a un cliente o registro de transacciones.
{% endswagger-description %}

{% swagger-parameter in="header" name="Authorization" type="string" required="true" %}
key \[API\_KEY]
{% endswagger-parameter %}

{% swagger-parameter in="body" name="id" type="string" %}
Id del registro o transacción
{% endswagger-parameter %}

{% swagger-parameter in="body" name="departments" type="json" required="true" %}
Array de departamentos\
\
Ejemplo:\
\["Financiero"]


{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Se han asignado departamentos al registro de clientes o transacciones con éxito." %}

{% endswagger-response %}
{% endswagger %}

{% swagger method="post" path="" baseUrl="https://www.pepdata.com/api/edit_questionnaire_approval_state" summary="Editar el estado de aprobación de un registro" %}
{% swagger-description %}
Endpoint para editar el estado de aprobación de un cliente o registro de transacción.
{% endswagger-description %}

{% swagger-parameter in="header" name="Authorization" type="string" required="true" %}
key \[API\_KEY]
{% endswagger-parameter %}

{% swagger-parameter in="body" name="id" type="string" required="true" %}
id del regristro o transacción
{% endswagger-parameter %}

{% swagger-parameter in="body" name="approval_state" type="string" required="true" %}
Estado de aprobación\


Valores aceptados:\
\-1 (Rechazado)\
0 (Indeciso)\
1 (aprobado)
{% endswagger-parameter %}

{% swagger-parameter in="body" name="approval_change_reason" type="string" required="true" %}
Justificación para cambiar el estado de aprobación
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="El estado de aprobación del registro de clientes o de la transacción se ha cambiado correctamente." %}

{% endswagger-response %}
{% endswagger %}

{% swagger method="post" path="" baseUrl="https://www.pepdata.com/api/revert_questionnaire_risk" summary="Revertir el riesgo de un registro" %}
{% swagger-description %}
Endpoint para revertir el riesgo actual de un cliente o registro de transacciones.
{% endswagger-description %}

{% swagger-parameter in="header" name="Authorization" type="string" required="true" %}
key \[API\_KEY]
{% endswagger-parameter %}

{% swagger-parameter in="body" name="id" type="string" required="true" %}
id del registro o transacción
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Se revirtió con éxito el riesgo del registro de clientes o transacciones" %}

{% endswagger-response %}
{% endswagger %}

{% swagger method="post" path="" baseUrl="https://www.pepdata.com/api/reset_questionnaire_needs_attention" summary="Restablecer el estado "Necesita atención" de un registro" %}
{% swagger-description %}
Endpoint para restablecer el estado "Necesita atención" de un registro de cliente o transacción.
{% endswagger-description %}

{% swagger-parameter in="header" name="Authorization" type="string" required="true" %}
key \[API\_KEY]
{% endswagger-parameter %}

{% swagger-parameter in="body" name="id" type="string" %}
Id del registro o transacción
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="El estado "Necesita atención" del registro de clientes o de transacciones se ha restablecido correctamente." %}

{% endswagger-response %}
{% endswagger %}
