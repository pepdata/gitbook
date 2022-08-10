# Registos

{% hint style="warning" %}
Esta secção da API ainda está em desenvolvimento, pelo que poderá sofrer alterações consideráveis. Esta página encontra-se em desenvolvimento.
{% endhint %}

{% swagger method="post" path="/get_questionnaires" baseUrl="https://www.pepdata.com/api" summary="Obter registos" %}
{% swagger-description %}
Endpoint para obter os registos de clientes e transações.
{% endswagger-description %}

{% swagger-parameter in="header" name="Authorization" type="string" required="true" %}
key [API_KEY]
{% endswagger-parameter %}

{% swagger-parameter in="body" name="id" type="string" %}
Id do registo ou transação
{% endswagger-parameter %}

{% swagger-parameter in="body" name="id_custom" type="string" %}
Id personalizável do registo ou transação
{% endswagger-parameter %}

{% swagger-parameter in="body" name="search_term" type="string" %}
Termo de pesquisa:

Pesquisa sobre as colunas name, vatin e id\_custom
{% endswagger-parameter %}

{% swagger-parameter in="body" name="page" type="integer" %}
Página dos registos ou transações

\


Default: 1
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Registos obtidos com sucesso." %}
```javascript
{
    "data": {
        "items": [
            {
                "id": "2a206d4a-0a5d-4a04-9a0c-cadae6e2cffa", 
                "name": "Lisa Fidalgo Corte-Real",
                "vatin": "255627777",
                "type": "individual",
                "added_at": 1588003603593,
                "added_by": "839a5871-fa0e-470a-af42-9110f8ef5b27",
                "submitted_at": null,
                "submitted_by": null,
                "accepted_at": null,
                "accepted_by": null,
                "data_treatment_accepted_at": null,
                "saved_at": 1648132877766,
                "assigned_to": null,
                "approval_state": null,
                "approval_change_reason": null,
                "risk": null,
                "risk_change_reason": null,
                "needs_attention": 0,
                "id_custom": "ID1"
            }
        ],
        "page": 1,
        "max_results_per_page": 50,
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
* **source\_name:** nome do registo onde teve origem este cliente.
* **source\_type:** tipo do registo onde teve origem este cliente.
* **source\_subtype:** subtipo do registo onde teve origem este cliente.
* **version:** versão do questionário.
* **type:** tipo de registo (individual, coletiva ou transação).
* **subtype:** subtipo do registo (representante, beneficiário, etc..).
* **added\_by:** id do utilizador que adicionou o registo.
* **added\_at:** data a que o registo foi adicionado, sob a forma de número de milissegundos desde 1 de Janeiro de 1970 00:00:00 UTC.
* **submitted\_at:** data a que o registo foi submetido, sob a forma de número de milissegundos desde 1 de Janeiro de 1970 00:00:00 UTC.
* **submitted\_by:** id do utilizador que submeteu o registo.
* **deleted\_at:** data a que o registo foi apagado, sob a forma de número de milissegundos desde 1 de Janeiro de 1970 00:00:00 UTC.
* **deleted\_by:** id do utilizador que apagou o registo.
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

{% swagger method="post" path="/add_questionnaire" baseUrl="https://www.pepdata.com/api" summary="Adição de um registo" %}
{% swagger-description %}
Endpoint para adicionar um registo de clientes e transações.
{% endswagger-description %}

{% swagger-parameter in="header" name="Authorization" type="string" required="true" %}
key [API_KEY]
{% endswagger-parameter %}

{% swagger-parameter in="body" name="name" type="string" required="true" %}
Nome do registo ou transação
{% endswagger-parameter %}

{% swagger-parameter in="body" name="vatin" type="string" required="false" %}
NIF/NIPC do registo
{% endswagger-parameter %}

{% swagger-parameter in="body" name="id_custom" type="string" %}
Id personalizável do registo
{% endswagger-parameter %}

{% swagger-parameter in="body" name="questionnaire_data" type="json" %}
**Consoante cada tipo de registo**, são necessários objetos diferentes:



_individual_

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

__

_organization_

__

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

__

_transaction_

__

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

__

__
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Registo ou transação criado/a." %}
```javascript
{
    "version": 0.1,
    "timestamp": 1660060397561,
    "data": {
        "id": "aa199264-c62e-3763-e3a5-68127b070720"
    }
}
```
{% endswagger-response %}

{% swagger-response status="400: Bad Request" description="O registo não foi criado, já existe na lista." %}
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
{% endswagger %}

### Legenda

* **id:** Id do registo ou transação criado/a.

{% swagger method="post" path="/edit_questionnaire" baseUrl="https://www.pepdata.com/api" summary="Edição de um registo" %}
{% swagger-description %}
Endpoint para editar um registo de clientes e transações.
{% endswagger-description %}

{% swagger-parameter in="body" type="string" required="true" name="id" %}
Id do registo ou transação
{% endswagger-parameter %}

{% swagger-parameter in="body" name="questionnaire_data" type="json" %}
Poderá só editar o valor que necessita:



Verifique [add\_questionnaire](registrations.md#adicao-de-um-registo) (`questionnaire_data`) para saber quais as propriedades que são aceites.
{% endswagger-parameter %}

{% swagger-parameter in="header" name="Authorization" type="string" required="true" %}
key [API_KEY]
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Registo de clientes ou transações editado/a." %}
```javascript
{
    "version": 0.1,
    "timestamp": 1660061942863,
    "data": {
        "risk": 0
    }
}
```
{% endswagger-response %}
{% endswagger %}



{% swagger method="post" path="/delete_questionnaire" baseUrl="https://www.pepdata.com/api" summary="Eliminação um registo" %}
{% swagger-description %}
Endpoint para apagar um registo de clientes ou transações.
{% endswagger-description %}

{% swagger-parameter in="header" name="Authorization" type="string" required="true" %}
key [API_KEY]
{% endswagger-parameter %}

{% swagger-parameter in="body" type="string" required="true" name="id" %}
Id do registo ou transação
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="O registo de clientes ou transações foi apagado com sucesso." %}
```javascript
{
    // Response
}
```
{% endswagger-response %}
{% endswagger %}



{% swagger method="post" path="/unsubmit_questionnaire" baseUrl="https://www.pepdata.com/api" summary="Cancelar a submissão de um registo" %}
{% swagger-description %}
Endpoint para cancelar a submissão de um registo de clientes ou transações.
{% endswagger-description %}

{% swagger-parameter in="header" name="Authorization" type="string" required="true" %}
key [API_KEY]
{% endswagger-parameter %}

{% swagger-parameter in="body" name="id" type="string" required="true" %}
Id do registo ou transação
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Submissão do registo de clientes ou transações cancelada foi cancelada com sucesso." %}
```javascript
{
    risk: 0
}
```
{% endswagger-response %}
{% endswagger %}

{% hint style="warning" %}
Cancelar a submissão irá recalcular o risco do registo. Se tiver uma categoria de risco configurada manualmente, a mesma será perdida.
{% endhint %}

### Legenda

* **risk:** risco recalculado do registo de clientes ou transações.

{% swagger method="post" path="/send_questionnaire_invite" baseUrl="https://www.pepdata.com/api" summary="Enviar um convite de preenchimento do registo" %}
{% swagger-description %}
Endpoint para enviar convite de preenchimento de um registo de clientes ou transações.
{% endswagger-description %}

{% swagger-parameter in="header" name="Authorization" type="string" required="true" %}
key [API_KEY]
{% endswagger-parameter %}

{% swagger-parameter in="body" name="id" type="string" required="true" %}
Id do registo ou transação
{% endswagger-parameter %}

{% swagger-parameter in="body" name="client_email" type="string" required="true" %}
E-mail do cliente convidado
{% endswagger-parameter %}

{% swagger-parameter in="body" name="language" type="string" required="true" %}
Língua em que deve ser enviado o convite



Valores aceites:

**pt-PT** (Português)

**en** (Inglês)

**es** (Espanhol)
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Convite enviado com sucesso." %}
```javascript
{
    // Response
}
```
{% endswagger-response %}
{% endswagger %}



{% swagger method="post" path="/cancel_questionnaire_invite" baseUrl="https://www.pepdata.com/api" summary="Cancelar um convite de preenchimento do registo" %}
{% swagger-description %}
Endpoint para cancelar o convite de preenchimento de um registo de clientes ou transações.
{% endswagger-description %}

{% swagger-parameter in="header" name="Authorization" type="string" required="true" %}
key [API_KEY]
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
    // Response
}
```
{% endswagger-response %}
{% endswagger %}



{% swagger method="post" path="/assign_user_to_questionnaire" baseUrl="https://www.pepdata.com/api" summary="Atribuir um utilizador a um registo" %}
{% swagger-description %}
Endpoint para atribuir um utilizador a um registo de clientes ou transações.
{% endswagger-description %}

{% swagger-parameter in="header" name="Authorization" type="string" required="true" %}
key [API_KEY]
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
    // Response
}
```
{% endswagger-response %}
{% endswagger %}

{% swagger method="post" path="/assign_departments_to_questionnaire" baseUrl="https://www.pepdata.com/api" summary="Atribuir departamentos a um registo" %}
{% swagger-description %}
Endpoint para atribuir departamentos a um registo de clientes ou transações.
{% endswagger-description %}

{% swagger-parameter in="header" name="Authorization" type="string" required="true" %}
key [API_KEY]
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
    // Response
}
```
{% endswagger-response %}
{% endswagger %}



{% swagger method="post" path="/edit_questionnaire_approval_state" baseUrl="https://www.pepdata.com/api" summary="Editar o estado de aprovação de um registo" %}
{% swagger-description %}
Endpoint para editar o estado de aprovação de um registo de clientes ou transações.
{% endswagger-description %}

{% swagger-parameter in="header" name="Authorization" type="string" required="true" %}
key [API_KEY]
{% endswagger-parameter %}

{% swagger-parameter in="body" name="id" type="string" required="true" %}
Id do registo ou transação
{% endswagger-parameter %}

{% swagger-parameter in="body" name="approval_state" type="integer" required="true" %}
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
    // Response
}
```
{% endswagger-response %}
{% endswagger %}



{% swagger method="post" path="/revert_questionnaire_risk" baseUrl="https://www.pepdata.com/api" summary="Reverter o risco de um registo" %}
{% swagger-description %}
Endpoint para reverter o risco atual de um registo de clientes ou transações.
{% endswagger-description %}

{% swagger-parameter in="header" name="Authorization" type="string" required="true" %}
key [API_KEY]
{% endswagger-parameter %}

{% swagger-parameter in="body" type="string" required="true" name="id" %}
Id do registo ou transação
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="O risco do registo de clientes ou transações foi revertido com sucesso." %}
```javascript
{
    risk: 0
}
```
{% endswagger-response %}
{% endswagger %}

### Legenda <a href="#legenda-2" id="legenda-2"></a>

* risk: risco recalculado do registo de clientes ou transações.

{% swagger method="post" path="/reset_questionnaire_needs_attention" baseUrl="https://www.pepdata.com/api" summary="Redefinir o estado "Precisam de atenção" de um registo" %}
{% swagger-description %}
Endpoint para redefinir o estado "Precisam de atenção" de um registo de clientes ou transações.
{% endswagger-description %}

{% swagger-parameter in="header" name="Authorization" type="string" required="true" %}
key [API_KEY]
{% endswagger-parameter %}

{% swagger-parameter in="body" name="id" type="string" required="true" %}
Id do registo ou transação
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Estado "Precisam de atenção" do registo de clientes ou transações foi redefinido com sucesso. " %}
```javascript
{
    // Response
}
```
{% endswagger-response %}
{% endswagger %}

