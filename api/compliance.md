# Compliance

## Adição de um individuo

<mark style="color:green;">`POST`</mark> `https://www.pepdata.com/api/compliance/add_individual`

Endpoint para adicionar um indivíduo a uma secção de compliance.

#### Headers

| Name                                            | Type   | Description     |
| ----------------------------------------------- | ------ | --------------- |
| Authorization<mark style="color:red;">\*</mark> | string | key \[API\_KEY] |

#### Request Body

| Name                                   | Type   | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| -------------------------------------- | ------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| name<mark style="color:red;">\*</mark> | string | Nome próprio                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| vatin                                  | string | NIF/NIPC                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| id\_custom                             | string | Id personalizável                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| section                                | string | <p>Secção onde o indivíduo irá ser adicionado.</p><p>Valores aceites:</p><p><strong>customers</strong></p><p><strong>suppliers</strong> <br>Default: <strong>customers</strong></p>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| data                                   | json   | <p><code>{</code></p><p><code>"personal_data": {</code></p><p><code>"email": "test@test.pt",</code></p><p><code>"birth_date": "2010-10-10",</code></p><p><code>"nationalities": ["Portugal"],</code></p><p><code>"birth_place": "Portugal"</code></p><p><code>},</code></p><p><code>"entity_proof": {</code></p><p><code>"identification_metadata": {</code></p><p><code>"document_number": 123456789,</code></p><p><code>"is_document_perpetual": false,</code></p><p><code>"document_validity": "2023-05-20",</code></p><p><code>"document_issuing_entity": "Test",</code></p><p><code>"document_issuing_date": "2013-05-20",</code></p><p><code>"document_issuing_location": "Test"</code></p><p><code>}</code></p><p><code>},</code></p><p><code>"address_data": {</code></p><p><code>"type": "residence",</code> ** <code>"country":"Portugal",</code></p><p><code>"cep":"1234-567",</code></p><p><code>"address_line_1":"Rua X",</code></p><p><code>"address_line_2":"nº123",</code></p><p><code>"city":"Lisboa",</code></p><p><code>"district":"Lisboa"</code></p><p><code>},</code></p><p><code>"suspicion_data": {</code></p><p><code>"is_suspect": false,</code></p><p><code>"reason": "Test"</code></p><p><code>},</code></p><p><code>}</code></p><p>**Valores aceites:</p><p><strong>residence</strong></p><p><strong>fiscal_residence</strong></p><p><strong>headquarters</strong></p> |
| adverse\_info\_data\_sources           | array  | <p>Especificação das fontes de dados a pesquisar.</p><p>Valores aceites:</p><p><strong>forensic</strong></p><p><strong>adverse_media</strong></p><p><strong>judicial_processes</strong></p>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |

{% hint style="info" %}
O envio dos resultados da pesquisa de informação adversa está dependente da configuração prévia de um webhook na página de configurações, uma vez que a resposta poderá demorar vários minutos a ser obtida, por ser realizada em tempo real.

Para garantir a segurança e integridade das chamadas ao webhook, usamos o método de autenticação Bearer. Isso significa que todas as chamadas ao webhook incluem um header "Authorization" contendo um token que precisa de ser validado. Esse token pode ser encontrado na página de configurações.
{% endhint %}

{% tabs %}
{% tab title="200: OK Indivíduo criado/a." %}
```javascript
{
    "version": 0.1,
    "timestamp": 1660060397561,
    "data": {
        "id_validation": "aa199264-c62e-3763-e3a5-68127b070720",
        "id_questionnaire": "89da8ec5-d4d8-48ff-915f-e1e9a6715c4a",
        "risk": 0,
        "risk_category": "low",
        "validation_status": "complete",
        "iperson": {
              "id": "0347e7ec-200f-4b6a-937c-96c66275e92c",
              "name": "João Pedro Pereira",
              "birth_date": "1933-05-25",
              "score": 76,
              "classifications": [
                    "pep",
                    "family_member",
                    "associate",
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
    }
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

* **id\_validation:** Id da validação associada ao indivíduo criado.
* **id\_questionnaire:** Id do questionário associado ao indivíduo criado.
* **risk:** valor do risco do questionário associado ao indivíduo criado.
* **risk\_category:** categoria em que se insere o valor do risco.
* **validation\_status:** estado da validação, podendo esta ser:
  * complete: Caso a aplicação tenha conseguido realizar a associação de maneira automática.
  * incomplete: Caso contrário.
* **iperson:** pessoa identificável associada ao indivíduo adicionado, caso a aplicação tenha conseguido realizar a associação de maneira automática.

## Adição de uma organização

<mark style="color:green;">`POST`</mark> `https://www.pepdata.com/api/compliance/add_organization`

Endpoint para adicionar uma organização a uma secção de compliance.

#### Headers

| Name                                            | Type   | Description     |
| ----------------------------------------------- | ------ | --------------- |
| Authorization<mark style="color:red;">\*</mark> | string | key \[API\_KEY] |

#### Request Body

| Name                                   | Type   | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| -------------------------------------- | ------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| name<mark style="color:red;">\*</mark> | string | Nome oficial                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| vatin                                  | string | NIF/NIPC                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| id\_custom                             | string | Id personalizável                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| section                                | string | <p>Secção onde a organização irá ser adicionada.</p><p>Valores aceites:</p><p><strong>customers</strong></p><p><strong>suppliers</strong> <br>Default: <strong>customers</strong></p>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| data                                   | json   | <p><code>{</code></p><p><code>"company_data": {</code></p><p><code>"object": "test",</code></p><p><code>"caes": ["01111"],</code></p><p><code>"country": "Portugal",</code></p><p><code>"foundation_date": "2005-02-01",</code></p><p><code>"countries_operations": ["Portugal"]</code></p><p><code>},</code></p><p><code>"entity_proof": {</code></p><p><code>"national_headquarters": true</code></p><p><code>},</code></p><p><code>"beneficiary_data": {</code></p><p><code>"codigo_rcbe": "123456"</code></p><p><code>},</code></p><p><code>"address_data": {</code></p><p><code>"country":"Portugal", "cep":"1234-567", "address_line_1":"Rua X", "address_line_2":"nº 123", "city":"Lisboa", "district":"Lisboa"</code></p><p><code>},</code></p><p><code>"suspicion_data": {</code></p><p><code>"is_suspect": false,</code></p><p><code>"reason": "Test"</code></p><p><code>},</code></p><p><code>}</code></p> |
| adverse\_info\_data\_sources           | array  | <p>Especificação das fontes de dados a pesquisar.</p><p>Valores aceites:</p><p><strong>forensic</strong></p><p><strong>adverse_media</strong></p><p><strong>judicial_processes</strong></p>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |

{% hint style="info" %}
O envio dos resultados da pesquisa de informação adversa está dependente da configuração prévia de um webhook na página de configurações, uma vez que a resposta poderá demorar vários minutos a ser obtida, por ser realizada em tempo real.

Para garantir a segurança e integridade das chamadas ao webhook, usamos o método de autenticação Bearer. Isso significa que todas as chamadas ao webhook incluem um header "Authorization" contendo um token que precisa de ser validado. Esse token pode ser encontrado na página de configurações.
{% endhint %}

{% tabs %}
{% tab title="200: OK Organização criado/a." %}
```javascript
{
    "version": 0.1,
    "timestamp": 1660060397561,
    "data": {
        "id_validation": "aa199264-c62e-3763-e3a5-68127b070720",
        "id_questionnaire": "89da8ec5-d4d8-48ff-915f-e1e9a6715c4a",
        "risk": 0,
        "risk_category": "low",
        "classifications": ["sanctioned_eu", "sanctioned_ofac"]
    }
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

* **id\_validation:** Id da validação associada à organização criada.
* **id\_questionnaire:** Id do questionário associado à organização criada.
* **risk:** valor do risco do questionário associado à organização criada.
* **risk\_category:** categoria em que se insere o valor do risco.
* **classifications:** classificações associadas à organização adicionada, caso a aplicação tenha conseguido realizar a associação de maneira automática.
