# Registros

{% hint style="warning" %}
Esta sección de la API aún está en desarrollo, por lo que puede sufrir cambios considerables. Esta página está en desarrollo.
{% endhint %}

{% swagger method="post" path="" baseUrl="https://www.pepdata.com/api/get_questionnaires" summary="Obtener registros" %}
{% swagger-description %}
Endpoint para obtener registros de transacciones y clientes.
{% endswagger-description %}

{% swagger-parameter in="header" name="Authorization" type="string" required="true" %}
key [API_KEY]
{% endswagger-parameter %}

{% swagger-parameter in="body" name="id" type="string" %}
Id de registro o transacción
{% endswagger-parameter %}

{% swagger-parameter in="body" name="id_custom" type="string" %}
Id personalizable de registro o transacción
{% endswagger-parameter %}

{% swagger-parameter in="body" name="search_term" type="string" %}
Término de búsqueda: Buscar en las columnas name, vatin e id_custom
{% endswagger-parameter %}

{% swagger-parameter in="body" name="page" type="integer" %}
Página de registros o transacciones

\


Default: 1
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Registros obtenidos con éxito" %}

{% endswagger-response %}
{% endswagger %}

### Leyenda

* **id:** id de registro
* **name:** nombre del registro
* **vatin**: NIF/CIF de registro
* **value:** información de registro
* **source\_name:** nombre del registro donde se originó este cliente
* **source\_type:** tipo de registro donde se originó este cliente
* **source\_subtype:** subtipo del registro donde se originó este cliente
* **version:** versión del cuestionario
* **type:** tipo de registro (individual, colectivo o transaccion)
* **subtype:** subtipo de registro (representante, titular real, etc...)
* **added\_by:** id del usuario que agregó el registro
* **added\_at:** fecha en que se agregó el registro, en milisegundos desde el 1 de enero de 1970 00:00:00 UTC
* **submit\_at:** fecha en que se envió el registro, en milisegundos desde el 1 de enero de 1970 a las 00:00:00 UTC
* **submitted\_by:** id del usuario que envió el registro
* **delete\_at:** fecha en que se eliminó el registro, en milisegundos desde el 1 de enero de 1970 a las 00:00:00 UTC
* **delete\_by:** id del usuario que eliminó el registro
* **approval\_state:** estado de aprobación del registro (0 - en espera de decisión, 1 - aprobado, -1 - rechazado)
* **approval\_change\_reason:** justificación para cambiar el estado de aprobación
* **riesgo:** valor de riesgo del registro
* **risk\_change\_reason:** justificación del cambio de categoría de riesgo
* **saved\_at:** fecha en que se guardó el registro por última vez, en milisegundos desde el 1 de enero de 1970 a las 00:00:00 UTC
* **assigned\_to:** id del responsable del registro
* **id\_invited\_user:** id del usuario invitado al completar el registro
* **locked\_by:** id del usuario que tiene el registro abierto
* **lock\_at:** fecha en que se abrió el registro por última vez, en milisegundos desde el 1 de enero de 1970 a las 00:00:00 UTC
* **accept\_by:** id del usuario invitado que aceptó la invitación a rellenar
* **accept\_at:** fecha en la que se aceptó la invitación de finalización, en forma de número de milisegundos desde el 1 de enero de 1970 00:00:00 UTC
* **data\_treatment\_accepted\_at:** fecha en la que se aceptaron las condiciones de tratamiento de datos del usuario invitado, en forma de número de milisegundos desde el 1 de enero de 1970 00:00:00 UTC
* **needs\_attention:** booleano que describe si el registro necesita atención
* **id\_organization:** id de la organización que creó el registro
* **id\_custom:** id personalizable ingresado por el usuario
* **invite\_at:** fecha en que se envió la invitación a llenar, expresada en milisegundos desde el 1 de enero de 1970 00:00:00 UTC
* **invite\_by\_organization\_name:** nombre de la organización que envió la invitación a rellenar
* **language:** idioma en el que se envió la invitación a completar
* **id\_country:** país de la organización que creó el registro en formato ISO 3166-1 alpha-2
* **id\_iperson:** id de la persona identificable correspondiente. nulo si no hubo ninguna coincidencia

{% swagger method="post" path="" baseUrl="https://www.pepdata.com/api/add_questionnaire" summary="Agregando un registro" %}
{% swagger-description %}
Endpoint para agregar un registro de clientes y transacciones.
{% endswagger-description %}

{% swagger-parameter in="header" name="Authorization" type="string" required="true" %}
key [API_KEY]
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

{% endswagger-response %}

{% swagger-response status="400: Bad Request" description="El registro no fue creado, ya existe en la lista" %}

{% endswagger-response %}
{% endswagger %}
