# Registos

{% hint style="warning" %}
Esta secção da API ainda está em desenvolvimento, pelo que poderá sofrer alterações consideráveis. Esta página encontra-se em desenvolvimento.
{% endhint %}

{% swagger method="post" path="/get_questionnaires" baseUrl="https://www.pepdata.com/api" summary="Obter registos" %}
{% swagger-description %}
Endpoint para obter os registos de clientes e transações.
{% endswagger-description %}

{% swagger-parameter in="header" name="Authorization" type="string" required="true" %}
key \[API\_KEY]
{% endswagger-parameter %}

{% swagger-parameter in="body" name="id" type="string" required="false" %}
Id do registo ou transação
{% endswagger-parameter %}

{% swagger-parameter in="body" name="id_custom" type="string" required="false" %}
Id personalizável do registo ou transação
{% endswagger-parameter %}

{% swagger-parameter in="body" name="search_term" type="string" required="false" %}
Termo de pesquisa:

Pesquisa sobre as colunas name, vatin e id\_custom
{% endswagger-parameter %}

{% swagger-parameter in="body" name="page" type="integer" required="false" %}
Página dos registos ou transações

\\

Default: 1
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Registos obtidos com sucesso." %}
```javascript
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
                "risk_category": "low"
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

### Legenda

* **id**: id do registo.
* **name:** nome do registo.
* **vatin:** NIF/NIPC do registo.
* **value:** informação do registo.
* **version:** versão do questionário.
* **type:** tipo de registo (individual, coletiva ou transação).
* **subtype:** subtipo do registo (representante, beneficiário, etc..).
* **relations**: relações associadas ao registo.
* **added\_by:** id do utilizador que adicionou o registo.
* **added\_at:** data a que o registo foi adicionado, sob a forma de número de milissegundos desde 1 de Janeiro de 1970 00:00:00 UTC.
* **submitted\_at:** data a que o registo foi submetido, sob a forma de número de milissegundos desde 1 de Janeiro de 1970 00:00:00 UTC.
* **submitted\_by:** id do utilizador que submeteu o registo.
* **approval\_state:** estado de aprovação do registo (_**0 -**_ aguarda decisão, _**1 -**_ aprovado, _**-1**_ - rejeitado).
* **approval\_change\_reason:** justificação para alteração do estado de aprovação.
* **risk:** valor do risco do registo.
* **risk\_change\_reason:** justificação para alteração de categoria de risco.
* **saved\_at:** data a que o registo foi gravado pela última vez, sob a forma de número de milissegundos desde 1 de Janeiro de 1970 00:00:00 UTC.
* **assigned\_to:** id do responsável do registo.
* **id\_invited\_user:** id do utilizador convidado ao preenchimento do registo.
* **locked\_by:** id do utilizador que tem o registo aberto.
* **locked\_at:** data a que o registo foi aberto pela última vez, sob a forma de número de milissegundos desde 1 de Janeiro de 1970 00:00:00 UTC.
* **accepted\_by:** id do utilizador convidado que aceitou o convite ao preenchimento.
* **accepted\_at:** data a que o convite ao preenchimento foi aceite, sob a forma de número de milissegundos desde 1 de Janeiro de 1970 00:00:00 UTC.
* **data\_treatment\_accepted\_at:** data a que o foram aceites as codições de tratamento dos dados do utilizador convidado, sob a forma de número de milissegundos desde 1 de Janeiro de 1970 00:00:00 UTC.
* **needs\_attention:** booleano que descreve se o registo precisa de atenção.
* **id\_organization:** id da organização que criou o registo.
* **id\_custom:** id personalizável inserido pelo utilizador.
* **invited\_at:** data a que o convite ao preenchimento foi enviado, sob a forma de número de milissegundos desde 1 de Janeiro de 1970 00:00:00 UTC.
* **invited\_by\_organization\_name:** nome da organização que enviou o convite ao preenchimento.
* **language:** língua em que foi enviado o convite ao preenchimento.
* **id\_country:** país da organização que criou o registo em formato [ISO 3166-1 alpha-2](https://en.wikipedia.org/wiki/ISO\_3166-1\_alpha-2).
* **id\_iperson:** id da pessoa identificável correspondente. null caso não tenha existido correspondência.
* **risk\_category:** categoria em que se insere o valor do risco.

{% swagger method="post" path="/add_questionnaire" baseUrl="https://www.pepdata.com/api" summary="Adição de um registo" %}
{% swagger-description %}
Endpoint para adicionar um registo de clientes e transações.
{% endswagger-description %}

{% swagger-parameter in="header" name="Authorization" type="string" required="true" %}
key \[API\_KEY]
{% endswagger-parameter %}

{% swagger-parameter in="body" name="name" type="string" required="true" %}
Nome do registo ou transação
{% endswagger-parameter %}

{% swagger-parameter in="body" name="vatin" type="string" required="false" %}
NIF/NIPC do registo
{% endswagger-parameter %}

{% swagger-parameter in="body" name="id_custom" type="string" required="false" %}
Id personalizável do registo
{% endswagger-parameter %}

{% swagger-parameter in="body" name="type" type="string" required="true" %}
Tipo do registo

Valores aceites:

**individual** (Registo de pessoa individual)

**organization** ( Registo de pessoa coletiva)

**transaction** (Transação)
{% endswagger-parameter %}

{% swagger-parameter in="body" name="questionnaire_data" type="json" required="false" %}
**Consoante cada tipo de registo**, são necessários objetos diferentes:

_individual_

`{`

`"personal_data": {`

`"email": "test@test.pt",`

`"birth_date": "2010-10-10",`

`"nationalities": ["Portugal"],`

`"birth_place": "Portugal"`

`},`

`"entity_proof": {`

`"identification_metadata": {`

`"document_number": 123456789,`

`"is_document_perpetual": false,`

`"document_validity": "2023-05-20",`

`"document_issuing_entity": "Test",`

`"document_issuing_date": "2013-05-20",`

`"document_issuing_location": "Test"`

`},`

`},`

`"suspicion_data": {`

`"is_suspect": false,`

`"reason": "Test"`

`},`

`}`

_organization_

`{`

`"company_data": {`

`"object": "test",`

`"caes": ["01111"],`

`"country": "Portugal",`

`"foundation_date": "2005-02-01",`

`"countries_operations": ["Portugal"]`

`},`

`"entity_proof": {`

`"national_headquarters": true`

`},`

`"beneficiary_data": {`

`"codigo_rcbe": "123456"`

`},`

`"suspicion_data": {`

`"is_suspect": false,`

`"reason": "Test"`

`},`

`}`

_transaction_

`{`

`"buyer": {`

`"acquisition_purpose": "test purpose",`

`},`

`"basic_information": {`

`"sell_type": "good",`

`"description": "test description",`

`"observations": "test observations"`

`},`

`"suspicion_data": {`

`"is_suspect": false,`

`"reason": "Test"`

`},`

`}`
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Registo ou transação criado/a." %}
```javascript
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

{% swagger-response status="409: Conflict" description="O registo não foi criado, já existe na lista." %}
```javascript
{
    "message": {
        "version": 0.1,
        "timestamp": 1660060761083,
        "message": "O registo não foi criado, já existe na lista."
    }
}
```
{% endswagger-response %}

{% swagger-response status="400: Bad Request" description="NIF/NIPC inválido" %}


```json
{
    "message": {
        "version": 0.1,
        "timestamp": 1697022273147,
        "message": "NIF/NIPC: O NIF/NIPC é inválido. Caso seja internacional, coloque o código do país no início. Ex.: FR12345678901 para um NIF francês."
    }
}
```
{% endswagger-response %}
{% endswagger %}

### Legenda

* **id:** Id do registo ou transação criado/a.
* **risk:** valor do risco do registo/transação criado/a.
* **risk\_category:** categoria em que se insere o valor do risco do registo/transação criado/a.

{% swagger method="post" path="/edit_questionnaire" baseUrl="https://www.pepdata.com/api" summary="Edição de um registo" %}
{% swagger-description %}
Endpoint para editar um registo de clientes e transações.
{% endswagger-description %}

{% swagger-parameter in="body" type="string" required="true" name="id" %}
Id do registo ou transação
{% endswagger-parameter %}

{% swagger-parameter in="body" name="questionnaire_data" type="json" required="false" %}
Poderá só editar o valor que necessita:

Verifique [add\_questionnaire](registrations.md#adicao-de-um-registo) (`questionnaire_data`) para saber quais as propriedades que são aceites.
{% endswagger-parameter %}

{% swagger-parameter in="header" name="Authorization" type="string" required="true" %}
key \[API\_KEY]
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Registo de clientes ou transações editado/a." %}
```javascript
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

{% swagger-response status="400: Bad Request" description="Registo de cliente ou transação não encontrado" %}


```json
{
    "message": {
        "version": 0.1,
        "timestamp": 1697023212378,
        "message": "O registo pretendido não foi encontrado."
    }
}
```
{% endswagger-response %}
{% endswagger %}

### Legenda

* **risk:** valor do risco do registo/transação editado/a.
* **risk\_category:** categoria em que se insere o valor do risco do registo/transação editado/a.

{% swagger method="post" path="/delete_questionnaire" baseUrl="https://www.pepdata.com/api" summary="Eliminação um registo" %}
{% swagger-description %}
Endpoint para apagar um registo de clientes ou transações.
{% endswagger-description %}

{% swagger-parameter in="header" name="Authorization" type="string" required="true" %}
key \[API\_KEY]
{% endswagger-parameter %}

{% swagger-parameter in="body" type="string" required="true" name="id" %}
Id do registo ou transação
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="O registo de clientes ou transações foi apagado com sucesso." %}
```javascript
{
    "version": 0.1,
    "timestamp": 1695892485159,
    "data": {
        "message": "O registo foi eliminado com sucesso."
    }
}
```
{% endswagger-response %}

{% swagger-response status="400: Bad Request" description="Registo de cliente ou transação não encontrado. " %}
```
{
    "message": {
        "version": 0.1,
        "timestamp": 1697023212378,
        "message": "O registo pretendido não foi encontrado."
    }
}
```
{% endswagger-response %}
{% endswagger %}

{% hint style="warning" %}
**Importante:** Poderá obter um erro ao eliminar um registo caso este tenha dependências com outros registos.
{% endhint %}

{% swagger method="post" path="/unsubmit_questionnaire" baseUrl="https://www.pepdata.com/api" summary="Cancelar a submissão de um registo" %}
{% swagger-description %}
Endpoint para cancelar a submissão de um registo de clientes ou transações.
{% endswagger-description %}

{% swagger-parameter in="header" name="Authorization" type="string" required="true" %}
key \[API\_KEY]
{% endswagger-parameter %}

{% swagger-parameter in="body" name="id" type="string" required="true" %}
Id do registo ou transação
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Submissão do registo de clientes ou transações cancelada foi cancelada com sucesso." %}
```javascript
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

{% swagger-response status="400: Bad Request" description="Registo de cliente ou transação não encontrado. " %}
```
{
    "message": {
        "version": 0.1,
        "timestamp": 1697023212378,
        "message": "O registo pretendido não foi encontrado."
    }
}
```
{% endswagger-response %}
{% endswagger %}

{% hint style="warning" %}
Cancelar a submissão irá recalcular o risco do registo. Se tiver uma categoria de risco configurada manualmente, a mesma será perdida.
{% endhint %}

### Legenda

* **risk:** valor do risco do registo de clientes/transações.
* **risk\_category:** categoria em que se insere o valor do risco do registo de clientes/transações.

{% swagger method="post" path="/send_questionnaire_invite" baseUrl="https://www.pepdata.com/api" summary="Enviar um convite de preenchimento do registo" %}
{% swagger-description %}
Endpoint para enviar convite de preenchimento de um registo de clientes ou transações.
{% endswagger-description %}

{% swagger-parameter in="header" name="Authorization" type="string" required="true" %}
key \[API\_KEY]
{% endswagger-parameter %}

{% swagger-parameter in="body" name="id" type="string" required="true" %}
Id do registo ou transação
{% endswagger-parameter %}

{% swagger-parameter in="body" name="client_email" type="string" required="true" %}
E-mail do cliente convidado
{% endswagger-parameter %}

{% swagger-parameter in="body" name="language" type="string" required="false" %}
Língua em que deve ser enviado o convite

Default: pt-PT

Valores aceites:

**pt-PT** (Português)

**en** (Inglês)

**es** (Espanhol)
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Convite enviado com sucesso." %}
```javascript
{
    "version": 0.1,
    "timestamp": 1695997097315,
    "data": {
        "message": "Convite enviado para {{client_email}}."
    }
}
```
{% endswagger-response %}
{% endswagger %}

{% swagger method="post" path="/cancel_questionnaire_invite" baseUrl="https://www.pepdata.com/api" summary="Cancelar um convite de preenchimento do registo" %}
{% swagger-description %}
Endpoint para cancelar o convite de preenchimento de um registo de clientes ou transações.
{% endswagger-description %}

{% swagger-parameter in="header" name="Authorization" type="string" required="true" %}
key \[API\_KEY]
{% endswagger-parameter %}

{% swagger-parameter in="body" name="id" type="string" required="true" %}
Id do registo ou transação
{% endswagger-parameter %}

{% swagger-parameter in="body" name="client_email" type="string" required="true" %}
E-mail do cliente convidado
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Convite cancelado com sucesso." %}
```javascript
{
    "version": 0.1,
    "timestamp": 1695997713238,
    "data": {
        "message": "Convite de {{client_email}} foi cancelado."
    }
}
```
{% endswagger-response %}
{% endswagger %}

{% swagger method="post" path="/assign_user_to_questionnaire" baseUrl="https://www.pepdata.com/api" summary="Atribuir um utilizador a um registo" %}
{% swagger-description %}
Endpoint para atribuir um utilizador a um registo de clientes ou transações.
{% endswagger-description %}

{% swagger-parameter in="header" name="Authorization" type="string" required="true" %}
key \[API\_KEY]
{% endswagger-parameter %}

{% swagger-parameter in="body" name="id" type="string" required="true" %}
Id do registo ou transação
{% endswagger-parameter %}

{% swagger-parameter in="body" name="id_user" type="string" required="true" %}
Id do utilizador
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="O utilizador foi atribuído ao registo de clientes ou transações com sucesso." %}
```javascript
{
    "version": 0.1,
    "timestamp": 1695999232282,
    "data": {
        "message": "Responsável modificado para {{user_name}}."
    }
}
```
{% endswagger-response %}
{% endswagger %}

{% swagger method="post" path="/assign_departments_to_questionnaire" baseUrl="https://www.pepdata.com/api" summary="Atribuir departamentos a um registo" %}
{% swagger-description %}
Endpoint para atribuir departamentos a um registo de clientes ou transações.
{% endswagger-description %}

{% swagger-parameter in="header" name="Authorization" type="string" required="true" %}
key \[API\_KEY]
{% endswagger-parameter %}

{% swagger-parameter in="body" name="id" type="string" required="true" %}
Id do registo ou transação
{% endswagger-parameter %}

{% swagger-parameter in="body" name="departments" type="json" required="true" %}
Array de departamentos

Exemplo:

\["Financeiro"]
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Os departamentos foram atribuídos ao registo de clientes ou transações com sucesso." %}
```javascript
{
    "version": 0.1,
    "timestamp": 1696001921643,
    "data": {
        "message": "Departamentos atribuídos com sucesso."
    }
}
```
{% endswagger-response %}
{% endswagger %}

{% swagger method="post" path="/edit_questionnaire_approval_state" baseUrl="https://www.pepdata.com/api" summary="Editar o estado de aprovação de um registo" %}
{% swagger-description %}
Endpoint para editar o estado de aprovação de um registo de clientes ou transações.
{% endswagger-description %}

{% swagger-parameter in="header" name="Authorization" type="string" required="true" %}
key \[API\_KEY]
{% endswagger-parameter %}

{% swagger-parameter in="body" name="id" type="string" required="true" %}
Id do registo ou transação
{% endswagger-parameter %}

{% swagger-parameter in="body" name="approval_state" type="string" required="true" %}
Estado de aprovação

Valores aceites:

**-1** (Rejeitado)

**0** (Por decidir)

**1** (Aprovado)
{% endswagger-parameter %}

{% swagger-parameter in="body" name="approval_change_reason" type="string" required="true" %}
Justificação para alteração do estado de aprovação
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Estado de aprovação do registo de clientes ou transações foi alterado com sucesso." %}
```javascript
{
    "version": 0.1,
    "timestamp": 1696002523053,
    "data": {
        "message": "Estado de aprovação editado com sucesso."
    }
}
```
{% endswagger-response %}
{% endswagger %}

{% swagger method="post" path="/revert_questionnaire_risk" baseUrl="https://www.pepdata.com/api" summary="Reverter o risco de um registo" %}
{% swagger-description %}
Endpoint para reverter o risco atual de um registo de clientes ou transações.
{% endswagger-description %}

{% swagger-parameter in="header" name="Authorization" type="string" required="true" %}
key \[API\_KEY]
{% endswagger-parameter %}

{% swagger-parameter in="body" type="string" required="true" name="id" %}
Id do registo ou transação
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="O risco do registo de clientes ou transações foi revertido com sucesso." %}
```javascript
{
    "version": 0.1,
    "timestamp": 1696238603806,
    "data": {
        "risk": 0,
        "risk_category": "low"
    }
}
```
{% endswagger-response %}
{% endswagger %}

### Legenda <a href="#legenda-2" id="legenda-2"></a>

* **risk:** risco calculado do registo de clientes ou transações.
* **risk\_category:** categoria em que se insere o valor do risco do registo de clientes/transações.

{% swagger method="post" path="/reset_questionnaire_needs_attention" baseUrl="https://www.pepdata.com/api" summary="Redefinir o estado " %}
{% swagger-description %}
Endpoint para redefinir o estado "Precisam de atenção" de um registo de clientes ou transações.
{% endswagger-description %}

{% swagger-parameter in="header" name="Authorization" type="string" required="true" %}
key \[API\_KEY]
{% endswagger-parameter %}

{% swagger-parameter in="body" name="id" type="string" required="true" %}
Id do registo ou transação
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Estado " %}
```javascript
{
    "version": 0.1,
    "timestamp": 1696239199674,
    "data": {
        "message": "Estado 'Needs attention' redefinido com sucesso."
    }
}
```
{% endswagger-response %}
{% endswagger %}
