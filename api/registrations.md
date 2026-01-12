# Registos

{% hint style="warning" %}
Esta secção da API ainda está em desenvolvimento, pelo que poderá sofrer alterações consideráveis. Esta página encontra-se em desenvolvimento.
{% endhint %}

## Obter registos

<mark style="color:green;">`POST`</mark> `https://www.pepdata.com/api/get_questionnaires`

Endpoint para obter os registos de clientes e transações.

#### Headers

| Name                                            | Type   | Description     |
| ----------------------------------------------- | ------ | --------------- |
| Authorization<mark style="color:red;">\*</mark> | string | key \[API\_KEY] |

#### Request Body

| Name                                   | Type    | Description                                                                                                                                                                                                           |
| -------------------------------------- | ------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| id                                     | string  | Id do registo ou transação                                                                                                                                                                                            |
| id\_custom                             | string  | Id personalizável do registo ou transação                                                                                                                                                                             |
| search\_term                           | string  | <p>Termo de pesquisa:</p><p>Pesquisa sobre as colunas name, vatin e id_custom</p>                                                                                                                                     |
| page                                   | integer | <p>Página dos registos ou transações</p><p>\</p><p>Default: 1</p>                                                                                                                                                     |
| type<mark style="color:red;">\*</mark> | string  | <p>Tipo de registos</p><p>Valores aceites:</p><p><strong>customer</strong></p><p><strong>supplier</strong></p><p><strong>employee</strong></p><p><strong>transaction</strong></p><p><strong>relationship</strong></p> |
| status                                 | string  | <p>Estado do registo<br>Valores aceites:<br><strong>rejected</strong><br><strong>to_decide</strong><br><strong>approved</strong><br><strong>incomplete</strong><br><strong>needs_attention</strong></p>               |

{% tabs %}
{% tab title="200: OK Registos obtidos com sucesso." %}
```javascript
{
    "data": {
        "items": [
            {
                "id": "7dd49ce1-9385-0cd1-7835-828393771ea0",
                "name": "individual",
                "name_normalized": "individual",
                "vatin": null,
                "value": "{\"entity_proof\":{\"type\":\"\",\"identification_metadata\":{\"document_number\":\"\",\"document_validity\":\"\",\"is_document_perpetual\":\"\",\"document_issuing_entity\":\"\",\"document_issuing_date\":\"\",\"document_issuing_location\":\"\"},\"documentUpload\":{\"files\":[],\"type\":null,\"source\":null,\"extraData\":null,\"is_trustworthy\":null}},\"personal_data\":{\"name\":\"individual\",\"vatin\":null,\"email\":\"\",\"birth_date\":\"\",\"nationalities\":[],\"birth_place\":\"\",\"documentUpload\":{\"files\":[]}},\"address_data\":{\"type\":null,\"country\":null,\"cep\":\"\",\"address_line_1\":\"\",\"address_line_2\":\"\",\"city\":\"\",\"district\":\"\",\"documentUpload\":{\"files\":[],\"type\":null,\"source\":null,\"extraData\":null,\"is_trustworthy\":null}},\"occupation_data\":{\"type\":null,\"profession\":\"\",\"employer\":\"\",\"eni\":{\"commercial_name\":\"\",\"is_same_address\":null,\"address\":{\"country\":null,\"cep\":\"\",\"address_line_1\":\"\",\"address_line_2\":\"\",\"city\":\"\",\"district\":\"\"},\"cae\":\"\"},\"documentUpload\":{\"files\":[],\"type\":null,\"source\":null,\"extraData\":null,\"is_trustworthy\":null}},\"data_verification\":{\"type\":null,\"client_email\":\"\",\"documentUpload\":{\"files\":[],\"type\":null,\"source\":null,\"extraData\":null,\"is_trustworthy\":null},\"invite_sent\":false},\"adverse_media_data\":{\"adverse_media\":[]},\"suspicion_data\":{\"is_suspect\":null,\"reason\":\"\"},\"questionnaire_id\":\"7dd49ce1-9385-0cd1-7835-828393771ea0\",\"name\":\"individual\"}",
                "entity_type": "individual",
                "main_entity_subtype": "regular",
                "relations": null,
                "added_by": "cd9f4a64-ab25-4efb-bf31-323ee2280095",
                "added_at": 1693489958769,
                "submitted_at": null,
                "submitted_by": null,
                "approval_state": null,
                "approval_change_reason": null,
                "risk": 0,
                "manual_risk": null,
                "risk_change_reason": null,
                "saved_at": 1693491414116,
                "assigned_to": null,
                "is_disabled": false,
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
                "language": null,qu
                "organization_id_country": "PT",
                "id_iperson": "ID1",
                "id_iorganization": null,
                "determined_at": null,
                "adverse_media_searched_at": null,
                "judicial_processes_searched_at": null,
                "forensics_searched_at": null,
                "type": "customer",
                "id_questionnaire_data": "4ba763f9-6675-949b-482c-35c689991d65",
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
{% endtab %}
{% endtabs %}

### Legenda

* **id**: id do registo.
* **name:** nome do registo.
* **name\_normalized**: nome normalizado do registo.
* **vatin:** NIF/NIPC do registo.
* **value:** informação do registo.
* **entity\_type:** tipo de entidade (individual, coletiva ou transação).
* **main\_entity\_subtype:** subtipo da entidade (representante, beneficiário, etc..).
* **relations**: relações associadas ao registo.
* **added\_by:** id do utilizador que adicionou o registo.
* **added\_at:** data a que o registo foi adicionado, sob a forma de número de milissegundos desde 1 de Janeiro de 1970 00:00:00 UTC.
* **submitted\_at:** data a que o registo foi submetido, sob a forma de número de milissegundos desde 1 de Janeiro de 1970 00:00:00 UTC.
* **submitted\_by:** id do utilizador que submeteu o registo.
* **approval\_state:** estado de aprovação do registo (_**0 -**_ aguarda decisão, _**1 -**_ aprovado, _**-1**_ - rejeitado).
* **approval\_change\_reason:** justificação para alteração do estado de aprovação.
* **risk:** valor do risco do registo.
* **manual\_risk:** valor do risco associado manualmente.
* **risk\_change\_reason:** justificação para alteração de categoria de risco.
* **saved\_at:** data a que o registo foi gravado pela última vez, sob a forma de número de milissegundos desde 1 de Janeiro de 1970 00:00:00 UTC.
* **assigned\_to:** id do responsável do registo.
* **is\_disabled:** registo inativo.
* **id\_invited\_user:** id do utilizador convidado ao preenchimento do registo.
* **locked\_by:** id do utilizador que tem o registo aberto.
* **locked\_at:** data a que o registo foi aberto pela última vez, sob a forma de número de milissegundos desde 1 de Janeiro de 1970 00:00:00 UTC.
* **invited\_submission\_by:** id do utilizador convidado que aceitou o convite ao preenchimento.
* **invited\_submission\_at:** data a que o convite ao preenchimento foi aceite, sob a forma de número de milissegundos desde 1 de Janeiro de 1970 00:00:00 UTC.
* **data\_treatment\_accepted\_at:** data a que o foram aceites as codições de tratamento dos dados do utilizador convidado, sob a forma de número de milissegundos desde 1 de Janeiro de 1970 00:00:00 UTC.
* **needs\_attention:** array de objetos com informação sobre o motivo de cada um dos alertas.
* **id\_organization:** id da organização que criou o registo.
* **id\_custom:** id personalizável inserido pelo utilizador.
* **invited\_at:** data a que o convite ao preenchimento foi enviado, sob a forma de número de milissegundos desde 1 de Janeiro de 1970 00:00:00 UTC.
* **invited\_by\_organization\_name:** nome da organização que enviou o convite ao preenchimento.
* **language:** língua em que foi enviado o convite ao preenchimento.
* **organization\_id\_country:** país da organização que criou o registo em formato [ISO 3166-1 alpha-2](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2).
* **id\_iperson:** id da pessoa identificável correspondente. null caso não tenha existido correspondência.
* **id\_iorganization:** id da organização identificável correspondente. null caso não tenha existido correspondência.
* **determined\_at:** data a que o registo foi determinado, sob a forma de número de milissegundos desde 1 de Janeiro de 1970 00:00:00 UTC.
* **adverse\_media\_searched\_at:** data a que a última pesquisa de adverse media foi realizada, sob a forma de número de milissegundos desde 1 de Janeiro de 1970 00:00:00 UTC.
* **judicial\_processes\_searched\_at:** data a que a última pesquisa de processos judiciais foi realizada, sob a forma de número de milissegundos desde 1 de Janeiro de 1970 00:00:00 UTC.
* **forensics\_searched\_at:** data a que a última pesquisa de informação forense foi realizada, sob a forma de número de milissegundos desde 1 de Janeiro de 1970 00:00:00 UTC.
* **type:** tipo de registo,
* **id\_questionnaire\_data:** id do registo onde está guardada a informação do questionário.
* **risk\_category:** categoria em que se insere o valor do risco.

## Adição de um registo

<mark style="color:green;">`POST`</mark> `https://www.pepdata.com/api/add_questionnaire`

Endpoint para adicionar um registo de clientes e transações.

#### Headers

| Name                                            | Type   | Description     |
| ----------------------------------------------- | ------ | --------------- |
| Authorization<mark style="color:red;">\*</mark> | string | key \[API\_KEY] |

#### Request Body

| Name                                   | Type   | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| -------------------------------------- | ------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| name<mark style="color:red;">\*</mark> | string | Nome do registo ou transação                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| vatin                                  | string | NIF/NIPC do registo                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| id\_custom                             | string | Id personalizável do registo                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| questionnaire\_type                    | string | <p>Tipo de registo</p><p>Default: customer</p><p>Valores aceites:</p><p><strong>customer</strong></p><p><strong>supplier</strong></p><p><strong>employee</strong></p><p><strong>transaction</strong></p><p><strong>relationship</strong></p>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| type<mark style="color:red;">\*</mark> | string | <p>Tipo de entidade</p><p>Valores aceites:</p><p><strong>individual</strong> (Registo de pessoa individual)</p><p><strong>organization</strong> ( Registo de pessoa coletiva)</p><p><strong>transaction</strong> (Transação)</p>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| questionnaire\_data                    | json   | <p><strong>Consoante cada tipo de registo</strong>, são necessários objetos diferentes:</p><p><em>individual</em></p><p><code>{</code></p><p><code>"personal_data": {</code></p><p><code>"email": "test@test.pt",</code></p><p><code>"birth_date": "2010-10-10",</code></p><p><code>"nationalities": ["Portugal"],</code></p><p><code>"birth_place": "Portugal"</code></p><p><code>},</code></p><p><code>"entity_proof": {</code></p><p><code>"identification_metadata": {</code></p><p><code>"document_number": 123456789,</code></p><p><code>"is_document_perpetual": false,</code></p><p><code>"document_validity": "2023-05-20",</code></p><p><code>"document_issuing_entity": "Test",</code></p><p><code>"document_issuing_date": "2013-05-20",</code></p><p><code>"document_issuing_location": "Test"</code></p><p><code>}</code></p><p><code>},</code></p><p><code>"address_data": {</code></p><p><code>"type": "residence",</code> ** <code>"country":"Portugal",</code></p><p><code>"cep":"1234-567",</code></p><p><code>"address_line_1":"Rua X",</code></p><p><code>"address_line_2":"nº123",</code></p><p><code>"city":"Lisboa",</code></p><p><code>"district":"Lisboa"</code></p><p><code>},</code></p><p><code>"suspicion_data": {</code></p><p><code>"is_suspect": false,</code></p><p><code>"reason": "Test"</code></p><p><code>},</code></p><p><code>}</code></p><p>**Valores aceites:</p><p><strong>residence</strong></p><p><strong>fiscal_residence</strong></p><p><strong>headquarters</strong></p><p></p><p><em>organization</em></p><p><code>{</code></p><p><code>"company_data": {</code> </p><p><code>"alternative_names": ["Alternative Name 1"],</code> </p><p><code>"object": "test",</code></p><p><code>"caes": ["01111"],</code></p><p><code>"country": "Portugal",</code></p><p><code>"foundation_date": "2005-02-01",</code></p><p><code>"countries_operations": ["Portugal"]</code></p><p><code>},</code></p><p><code>"entity_proof": {</code></p><p><code>"national_headquarters": true</code></p><p><code>},</code></p><p><code>"beneficiary_data": {</code></p><p><code>"codigo_rcbe": "123456"</code></p><p><code>},</code></p><p><code>"address_data": {</code></p><p><code>"country":"Portugal", "cep":"1234-567", "address_line_1":"Rua X", "address_line_2":"nº 123", "city":"Lisboa", "district":"Lisboa"</code></p><p><code>},</code></p><p><code>"suspicion_data": {</code></p><p><code>"is_suspect": false,</code></p><p><code>"reason": "Test"</code></p><p><code>},</code></p><p><code>}</code></p><p><em>transaction</em></p><p><code>{</code></p><p><code>"buyer": {</code></p><p><code>"acquisition_purpose": "test purpose",</code></p><p><code>},</code></p><p><code>"basic_information": {</code></p><p><code>"sell_type": "good",</code></p><p><code>"description": "test description",</code></p><p><code>"observations": "test observations"</code></p><p><code>},</code></p><p><code>"suspicion_data": {</code></p><p><code>"is_suspect": false,</code></p><p><code>"reason": "Test"</code></p><p><code>},</code></p><p><code>}</code></p> |

{% tabs %}
{% tab title="200: OK Registo ou transação criado/a." %}
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
{% endtab %}

{% tab title="409: Conflict Já existe um registo com o mesmo nif/nipc ou ID personalizado." %}
```javascript
{
    "message": {
        "version": 0.1,
        "timestamp": 1660060761083,
        "message": "Já existe um registo com o mesmo nif/nipc ou ID personalizado."
    }
}
```
{% endtab %}

{% tab title="409: Conflict (Transação) Já existe um registo com o mesmo ID personalizado. " %}
```javascript
"message": {
    "version": 0.1,
    "timestamp": 1660060761083,
    "message": "Já existe um registo com o mesmo ID personalizado."
}
```
{% endtab %}

{% tab title="400: Bad Request NIF/NIPC inválido" %}


```json
{
    "message": {
        "version": 0.1,
        "timestamp": 1697022273147,
        "message": "NIF/NIPC: O NIF/NIPC é inválido. Caso seja internacional, coloque o código do país no início. Ex.: FR12345678901 para um NIF francês."
    }
}
```
{% endtab %}
{% endtabs %}

### Legenda

* **id:** Id do registo ou transação criado/a.
* **risk:** valor do risco do registo/transação criado/a.
* **risk\_category:** categoria em que se insere o valor do risco do registo/transação criado/a.

## Edição de um registo

<mark style="color:green;">`POST`</mark> `https://www.pepdata.com/api/edit_questionnaire`

Endpoint para editar um registo de clientes e transações.

#### Headers

| Name                                            | Type   | Description     |
| ----------------------------------------------- | ------ | --------------- |
| Authorization<mark style="color:red;">\*</mark> | string | key \[API\_KEY] |

#### Request Body

| Name                                 | Type   | Description                                                                                                                                                                                                              |
| ------------------------------------ | ------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| id<mark style="color:red;">\*</mark> | string | Id do registo ou transação                                                                                                                                                                                               |
| questionnaire\_data                  | json   | <p>Poderá só editar o valor que necessita:</p><p>Verifique <a href="registrations.md#adicao-de-um-registo">add_questionnaire</a> (<code>questionnaire_data</code>) para saber quais as propriedades que são aceites.</p> |

{% tabs %}
{% tab title="200: OK Registo de clientes ou transações editado/a." %}
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
{% endtab %}

{% tab title="400: Bad Request Registo de cliente ou transação não encontrado" %}


```json
{
    "message": {
        "version": 0.1,
        "timestamp": 1697023212378,
        "message": "O registo pretendido não foi encontrado."
    }
}
```
{% endtab %}
{% endtabs %}

### Legenda

* **risk:** valor do risco do registo/transação editado/a.
* **risk\_category:** categoria em que se insere o valor do risco do registo/transação editado/a.

## Eliminação de registos

<mark style="color:green;">`POST`</mark> `https://www.pepdata.com/api/delete_questionnaire`

Endpoint para apagar registos de clientes ou transações.

#### Headers

| Name                                            | Type   | Description     |
| ----------------------------------------------- | ------ | --------------- |
| Authorization<mark style="color:red;">\*</mark> | string | key \[API\_KEY] |

#### Request Body

| Name                                  | Type  | Description                 |
| ------------------------------------- | ----- | --------------------------- |
| ids<mark style="color:red;">\*</mark> | array | Ids dos registos a eliminar |

{% tabs %}
{% tab title="200: OK O registo de clientes ou transações foi apagado com sucesso." %}
```javascript
{
    "version": 0.1,
    "timestamp": 1695892485159,
    "data": {
        "message": "Registo(s) eliminado(s) com sucesso."
    }
}
```
{% endtab %}

{% tab title="400: Bad Request Registo de cliente ou transação não encontrado. " %}
```
{
    "message": {
        "version": 0.1,
        "timestamp": 1697023212378,
        "message": "O registo pretendido não foi encontrado."
    }
}
```
{% endtab %}
{% endtabs %}

{% hint style="warning" %}
**Importante:** Poderá obter um erro ao eliminar um registo caso este tenha dependências com outros registos.
{% endhint %}

## Cancelar a submissão de um registo

<mark style="color:green;">`POST`</mark> `https://www.pepdata.com/api/unsubmit_questionnaire`

Endpoint para cancelar a submissão de um registo de clientes ou transações.

#### Headers

| Name                                            | Type   | Description     |
| ----------------------------------------------- | ------ | --------------- |
| Authorization<mark style="color:red;">\*</mark> | string | key \[API\_KEY] |

#### Request Body

| Name                                 | Type   | Description                |
| ------------------------------------ | ------ | -------------------------- |
| id<mark style="color:red;">\*</mark> | string | Id do registo ou transação |

{% tabs %}
{% tab title="200: OK Submissão do registo de clientes ou transações cancelada foi cancelada com sucesso." %}
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
{% endtab %}

{% tab title="400: Bad Request Registo de cliente ou transação não encontrado. " %}
```
{
    "message": {
        "version": 0.1,
        "timestamp": 1697023212378,
        "message": "O registo pretendido não foi encontrado."
    }
}
```
{% endtab %}
{% endtabs %}

{% hint style="warning" %}
Cancelar a submissão irá recalcular o risco do registo. Se tiver uma categoria de risco configurada manualmente, a mesma será perdida.
{% endhint %}

### Legenda

* **risk:** valor do risco do registo de clientes/transações.
* **risk\_category:** categoria em que se insere o valor do risco do registo de clientes/transações.

## Enviar um convite de preenchimento do registo

<mark style="color:green;">`POST`</mark> `https://www.pepdata.com/api/send_questionnaire_invite`

Endpoint para enviar convite de preenchimento de um registo de clientes ou transações.

#### Headers

| Name                                            | Type   | Description     |
| ----------------------------------------------- | ------ | --------------- |
| Authorization<mark style="color:red;">\*</mark> | string | key \[API\_KEY] |

#### Request Body

| Name                                            | Type   | Description                                                                                                                                                                                                  |
| ----------------------------------------------- | ------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| id<mark style="color:red;">\*</mark>            | string | Id do registo ou transação                                                                                                                                                                                   |
| client\_email<mark style="color:red;">\*</mark> | string | E-mail do cliente convidado                                                                                                                                                                                  |
| language                                        | string | <p>Língua em que deve ser enviado o convite</p><p>Default: pt-PT</p><p>Valores aceites:</p><p><strong>pt-PT</strong> (Português)</p><p><strong>en</strong> (Inglês)</p><p><strong>es</strong> (Espanhol)</p> |

{% tabs %}
{% tab title="200: OK Convite enviado com sucesso." %}
```javascript
{
    "version": 0.1,
    "timestamp": 1695997097315,
    "data": {
        "message": "Convite enviado para {{client_email}}."
    }
}
```
{% endtab %}

{% tab title="400: Bad Request Registo de cliente ou transação não encontrado. " %}
```
{
    "message": {
        "version": 0.1,
        "timestamp": 1697023212378,
        "message": "O registo pretendido não foi encontrado."
    }
}
```
{% endtab %}
{% endtabs %}

## Cancelar um convite de preenchimento do registo

<mark style="color:green;">`POST`</mark> `https://www.pepdata.com/api/cancel_questionnaire_invite`

Endpoint para cancelar o convite de preenchimento de um registo de clientes ou transações.

#### Headers

| Name                                            | Type   | Description     |
| ----------------------------------------------- | ------ | --------------- |
| Authorization<mark style="color:red;">\*</mark> | string | key \[API\_KEY] |

#### Request Body

| Name                                            | Type   | Description                 |
| ----------------------------------------------- | ------ | --------------------------- |
| id<mark style="color:red;">\*</mark>            | string | Id do registo ou transação  |
| client\_email<mark style="color:red;">\*</mark> | string | E-mail do cliente convidado |

{% tabs %}
{% tab title="200: OK Convite cancelado com sucesso." %}
```javascript
{
    "version": 0.1,
    "timestamp": 1695997713238,
    "data": {
        "message": "Convite de {{client_email}} foi cancelado."
    }
}
```
{% endtab %}

{% tab title="400: Bad Request Registo de cliente ou transação não encontrado. " %}
```
{
    "message": {
        "version": 0.1,
        "timestamp": 1697023212378,
        "message": "O registo pretendido não foi encontrado."
    }
}
```
{% endtab %}
{% endtabs %}

## Atribuir um utilizador a um registo

<mark style="color:green;">`POST`</mark> `https://www.pepdata.com/api/assign_user_to_questionnaire`

Endpoint para atribuir um utilizador a um registo de clientes ou transações.

#### Headers

| Name                                            | Type   | Description     |
| ----------------------------------------------- | ------ | --------------- |
| Authorization<mark style="color:red;">\*</mark> | string | key \[API\_KEY] |

#### Request Body

| Name                                       | Type   | Description                |
| ------------------------------------------ | ------ | -------------------------- |
| id<mark style="color:red;">\*</mark>       | string | Id do registo ou transação |
| id\_user<mark style="color:red;">\*</mark> | string | Id do utilizador           |

{% tabs %}
{% tab title="200: OK O utilizador foi atribuído ao registo de clientes ou transações com sucesso." %}
```javascript
{
    "version": 0.1,
    "timestamp": 1695999232282,
    "data": {
        "message": "Responsável modificado para {{user_name}}."
    }
}
```
{% endtab %}

{% tab title="400: Bad Request Registo de cliente ou transação não encontrado. " %}
```
{
    "message": {
        "version": 0.1,
        "timestamp": 1697023212378,
        "message": "O registo pretendido não foi encontrado."
    }
}
```
{% endtab %}
{% endtabs %}

## Atribuir departamentos a um registo

<mark style="color:green;">`POST`</mark> `https://www.pepdata.com/api/assign_departments_to_questionnaire`

Endpoint para atribuir departamentos a um registo de clientes ou transações.

#### Headers

| Name                                            | Type   | Description     |
| ----------------------------------------------- | ------ | --------------- |
| Authorization<mark style="color:red;">\*</mark> | string | key \[API\_KEY] |

#### Request Body

| Name                                          | Type   | Description                                                       |
| --------------------------------------------- | ------ | ----------------------------------------------------------------- |
| id<mark style="color:red;">\*</mark>          | string | Id do registo ou transação                                        |
| departments<mark style="color:red;">\*</mark> | json   | <p>Array de departamentos</p><p>Exemplo:</p><p>["Financeiro"]</p> |

{% tabs %}
{% tab title="200: OK Os departamentos foram atribuídos ao registo de clientes ou transações com sucesso." %}
```javascript
{
    "version": 0.1,
    "timestamp": 1696001921643,
    "data": {
        "message": "Departamentos atribuídos com sucesso."
    }
}
```
{% endtab %}

{% tab title="400: Bad Request Departamentos inválidos" %}


```json
{
    "message": {
        "version": 0.1,
        "timestamp": 1697025396376,
        "message": "Ocorreu um erro ao associar departamentos ao registo. Verifique se os departamentos que está a associar existem na página de 'Configurações'."
    }
}
```
{% endtab %}
{% endtabs %}

## Editar o estado de aprovação de um registo

<mark style="color:green;">`POST`</mark> `https://www.pepdata.com/api/edit_questionnaire_approval_state`

Endpoint para editar o estado de aprovação de um registo de clientes ou transações.

#### Headers

| Name                                            | Type   | Description     |
| ----------------------------------------------- | ------ | --------------- |
| Authorization<mark style="color:red;">\*</mark> | string | key \[API\_KEY] |

#### Request Body

| Name                                                       | Type   | Description                                                                                                                                                        |
| ---------------------------------------------------------- | ------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| id<mark style="color:red;">\*</mark>                       | string | Id do registo ou transação                                                                                                                                         |
| approval\_state<mark style="color:red;">\*</mark>          | string | <p>Estado de aprovação</p><p>Valores aceites:</p><p><strong>-1</strong> (Rejeitado)</p><p><strong>0</strong> (Por decidir)</p><p><strong>1</strong> (Aprovado)</p> |
| approval\_change\_reason<mark style="color:red;">\*</mark> | string | Justificação para alteração do estado de aprovação                                                                                                                 |

{% tabs %}
{% tab title="200: OK Estado de aprovação do registo de clientes ou transações foi alterado com sucesso." %}
```javascript
{
    "version": 0.1,
    "timestamp": 1696002523053,
    "data": {
        "message": "Estado de aprovação editado com sucesso."
    }
}
```
{% endtab %}

{% tab title="400: Bad Request Registo de cliente ou transação não encontrado. " %}
```
{
    "message": {
        "version": 0.1,
        "timestamp": 1697023212378,
        "message": "O registo pretendido não foi encontrado."
    }
}
```
{% endtab %}
{% endtabs %}

## Editar o estado de um registo (Activo/Inactivo)

<mark style="color:green;">`POST`</mark> `https://www.pepdata.com/api/edit_qestionnaire_active_state`

Endpoint para alterar o estado (ativo/inativo) de um registo ou transações.

#### Headers

| Name                                            | Type   | Description     |
| ----------------------------------------------- | ------ | --------------- |
| Authorization<mark style="color:red;">\*</mark> | string | key \[API\_KEY] |

#### Request Body

| Name                                       | Type    | Description                                                                                                                                       |
| ------------------------------------------ | ------- | ------------------------------------------------------------------------------------------------------------------------------------------------- |
| id<mark style="color:red;">\*</mark>       | string  | Id do registo ou transação                                                                                                                        |
| disabled<mark style="color:red;">\*</mark> | boolean | <p>Estado do registo ou transação<br></p><p>Valores aceites:<br><strong>true</strong> registo inativo<br><strong>false</strong> registo ativo</p> |

{% tabs %}
{% tab title="200: OK A alteração do estado do registo foi alterada com sucesso." %}
```javascript
{
    "version": 0.1,
    "timestamp": 1696238603806,
    "data": {
        "disabled": false
    }
}
```
{% endtab %}

{% tab title="400: Bad Request Registo de cliente ou transação não encontrado. " %}
```
{
    "message": {
        "version": 0.1,
        "timestamp": 1697023212378,
        "message": "O registo pretendido não foi encontrado."
    }
}
```
{% endtab %}
{% endtabs %}

## Reverter o risco de um registo

<mark style="color:green;">`POST`</mark> `https://www.pepdata.com/api/revert_questionnaire_risk`

Endpoint para reverter o risco atual de um registo de clientes ou transações.

#### Headers

| Name                                            | Type   | Description     |
| ----------------------------------------------- | ------ | --------------- |
| Authorization<mark style="color:red;">\*</mark> | string | key \[API\_KEY] |

#### Request Body

| Name                                 | Type   | Description                |
| ------------------------------------ | ------ | -------------------------- |
| id<mark style="color:red;">\*</mark> | string | Id do registo ou transação |

{% tabs %}
{% tab title="200: OK O risco do registo de clientes ou transações foi revertido com sucesso." %}
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
{% endtab %}

{% tab title="400: Bad Request Registo de cliente ou transação não encontrado. " %}
```
{
    "message": {
        "version": 0.1,
        "timestamp": 1697023212378,
        "message": "O registo pretendido não foi encontrado."
    }
}
```
{% endtab %}
{% endtabs %}

### Legenda <a href="#legenda-2" id="legenda-2"></a>

* **risk:** risco calculado do registo de clientes ou transações.
* **risk\_category:** categoria em que se insere o valor do risco do registo de clientes/transações.

## Redefinir o estado&#x20;

<mark style="color:green;">`POST`</mark> `https://www.pepdata.com/api/reset_questionnaire_needs_attention`

Endpoint para redefinir o estado "Precisam de atenção" de um registo de clientes ou transações.

#### Headers

| Name                                            | Type   | Description     |
| ----------------------------------------------- | ------ | --------------- |
| Authorization<mark style="color:red;">\*</mark> | string | key \[API\_KEY] |

#### Request Body

| Name                                 | Type   | Description                |
| ------------------------------------ | ------ | -------------------------- |
| id<mark style="color:red;">\*</mark> | string | Id do registo ou transação |

{% tabs %}
{% tab title="200: OK Estado " %}
```javascript
{
    "version": 0.1,
    "timestamp": 1696239199674,
    "data": {
        "message": "Estado 'Needs attention' redefinido com sucesso."
    }
}
```
{% endtab %}

{% tab title="400: Bad Request Registo de cliente ou transação não encontrado. " %}
```
{
    "message": {
        "version": 0.1,
        "timestamp": 1697023212378,
        "message": "O registo pretendido não foi encontrado."
    }
}
```
{% endtab %}
{% endtabs %}

## Submeter os registos&#x20;

<mark style="color:green;">`POST`</mark> `https://www.pepdata.com/api/submit_questionnaires`

Endpoint que submete automaticamente todos os registos não submetidos.\*

**\*Esta operação está limitada a 8000 registos de cada vez.**

#### Headers

| Name                                            | Type   | Description     |
| ----------------------------------------------- | ------ | --------------- |
| Authorization<mark style="color:red;">\*</mark> | string | key \[API\_KEY] |

#### Request Body

| Name                                   | Type   | Description                                                                                                                  |
| -------------------------------------- | ------ | ---------------------------------------------------------------------------------------------------------------------------- |
| type<mark style="color:red;">\*</mark> | string | <p>Tipo dos registos a submeter</p><p>Valores aceites:</p><p><strong>customers</strong><br><strong>transactions</strong></p> |

{% tabs %}
{% tab title="200: OK Os registos foram submetidos com sucesso. " %}
```javascript
{
    "version": 0.1,
    "timestamp": 1695983552463,
    "data": {
        "time_to_conclusion": 1
    }
}
```
{% endtab %}

{% tab title="400: Bad Request O tipo de registos não é válido." %}
```
{
    "message": {
        "version": 0.1,
        "timestamp": 1708706955487,
        "message": "O tipo não é válido."
    }
}
```
{% endtab %}
{% endtabs %}

### Legenda <a href="#legenda-2" id="legenda-2"></a>

* **time\_to\_conclusion:** tempo estimado em segundos para a conclusão da operação.

## Exportar o relatório de risco

<mark style="color:green;">`POST`</mark> `https://www.pepdata.com/api/export_risk_pdf`

Endpoint para obter o relatório de risco de um registo em formato pdf.

#### Headers

| Name                                            | Type   | Description     |
| ----------------------------------------------- | ------ | --------------- |
| Authorization<mark style="color:red;">\*</mark> | string | key \[API\_KEY] |

#### Request Body

| Name                                 | Type   | Description                |
| ------------------------------------ | ------ | -------------------------- |
| id<mark style="color:red;">\*</mark> | string | Id do registo ou transação |

**Response**

{% tabs %}
{% tab title="200: OK Report gerado com sucesso" %}
{% file src="../.gitbook/assets/PEPData - Relatório de Avaliação de risco.pdf" %}
Exemplo de relatório de avaliação de risco
{% endfile %}
{% endtab %}

{% tab title="400: Bad Request Registo não encontrado" %}
```json
{
    "message": {
        "version": 0.1,
        "timestamp": 1697030777756,
        "message": "O registo pretendido não foi encontrado."
    }
}
```
{% endtab %}
{% endtabs %}
