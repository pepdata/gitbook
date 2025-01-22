# Beneficiários Efetivos

{% hint style="warning" %}
Esta secção ainda se encontra na versão **beta**.
{% endhint %}

## Comparação dos dados da plataforma da Iberinform com o portal RCBE

<mark style="color:green;">`POST`</mark> `https://www.pepdata.com/api/get_iberinform_rcbe_divergences`

#### Headers

| Name                                            | Type   | Description     |
| ----------------------------------------------- | ------ | --------------- |
| Authorization<mark style="color:red;">\*</mark> | string | key \[API\_KEY] |

#### Request Body

| Name                                    | Type    | Description                                                                                                         |
| --------------------------------------- | ------- | ------------------------------------------------------------------------------------------------------------------- |
| vatin<mark style="color:red;">\*</mark> | string  | NIPC da organização a comparar                                                                                      |
| include\_rcbe\_response                 | boolean | <p>Instrução para incorporar a resposta do RCBE.</p><p>\</p><p>Formato: false/true</p><p>\</p><p>Default: false</p> |

{% tabs %}
{% tab title="200: OK Informação recolhida com sucesso." %}
```javascript
{
    "data": {
        "id_iberinform_0": {
            status: 'found',
            matches: [rcbe_person_0],
            divergences
        },
        "id_iberinform_1": {
            status: 'ambiguous',
            matches: [rcbe_person_1, rcbe_person_2],
            divergences
        },
        "id_iberinform_2": {
            status: 'ambiguous',
            matches: [rcbe_person_3],  //same as id_iberinform_3 match
            divergences
        },
        "id_iberinform_3": {
            status: 'ambiguous',
            matches: [rcbe_person_3],  //same as id_iberinform_2 match
            divergences
        },
        "id_iberinform_4": {
            status: 'not_found',
            matches: [],
            divergences
        },
        "": {
            status: 'not_found',
            matches: [rcbe_person_4, rcbe_person_5],
            divergences
        },
        "rcbe_response": [
            {
		"name": "nome da pessoa",
		"birth_date": "DD/MM/YYYY",
		"nationality": "País_1; País_2;",
		"is_minor": "Não",
		"is_accompanied": "Não",
		"has_property_or_control": "Sim/Não",
		"asset_types": "Ações ou Quotas/Outros direitos de participação",
		"capital_percentage": "X %",
		"ownership_type",
		"ownership_structure",
		"has_voting_rights": "Sim/Não",
		"exerts_control",
		"is_top_manager",
		"is_founder": "Sim/Não",
		"is_administrator": "Sim/Não",
		"is_beneficiary",
		"has_control": "Sim/Não",
		"is_curator": "Sim/Não",
		"has_founder_admin_curator_category"
	    }
        ],
    },
    "version": "0.1",
    "timestamp": 1588599744111
}

// Relevant objects
// rcbe_person: {
//    name: name_rcbe,
//    birth_date: birth_date_rcbe,
//    shares_percentage: shares_percentage_rcbe,
// }
//
// divergences: {
//    name: boolean,
//    shares_percentage: boolean,
// }
```
{% endtab %}

{% tab title="400: Bad Request NIPC não encontrado" %}


```json
{
    "message": {
        "version": 0.1,
        "timestamp": 1697030777756,
        "message": "Não foi fornecido nenhum NIPC."
    }
}
```
{% endtab %}
{% endtabs %}

### Legenda

* **id\_iberinform**: id do sistema da Iberinform. Pode ser vazio de forma a agregar todas as pessoas do RCBE sem match no sistema da Iberinform.
* **status**:
  * found: encontrada uma correspondência unívoca no RCBE
  * ambiguous: encontradas correspondências ambíguas no RCBE
  * not\_found: não foram encontradas correspondências no RCBE
* **matches**: lista de pessoas presentes no RCBE que apresentaram correspondência com a pessoa.
* **rcbe\_person**: pessoa presente no RCBE. Ver Relevant Objects na response.
* **divergences**: objeto de divergências. Ver Relevant Objects na response.

## Obtenção dos beneficiários efetivos a partir do RCBE

<mark style="color:green;">`POST`</mark> `https://www.pepdata.com/api/get_beneficial_owners`

#### Headers

| Name                                            | Type   | Description     |
| ----------------------------------------------- | ------ | --------------- |
| Authorization<mark style="color:red;">\*</mark> | string | key \[API\_KEY] |

#### Request Body

| Name       | Type   | Description                  |
| ---------- | ------ | ---------------------------- |
| vatin      | string | NIPC da organização a tratar |
| rcbe\_code | string | Código RCBE                  |

{% tabs %}
{% tab title="200: OK Informação recolhida com sucesso" %}
```
{
    "data": {
        "items": [
            {
		"name": "nome da pessoa",
		"birth_date": "DD/MM/YYYY",
		"nationality": "País_1; País_2;",
		"is_minor": "Não",
		"is_accompanied": "Não",
		"has_property_or_control": "Sim/Não",
		"asset_types": "Ações ou Quotas/Outros direitos de participação",
		"capital_percentage": "X %",
		"ownership_type",
		"ownership_structure",
		"has_voting_rights": "Sim/Não",
		"exerts_control",
		"is_top_manager",
		"is_founder": "Sim/Não",
		"is_administrator": "Sim/Não",
		"is_beneficiary",
		"has_control": "Sim/Não",
		"is_curator": "Sim/Não",
		"has_founder_admin_curator_category"
	    }
        ]
    },
    "version": "0.1",
    "timestamp": 1646390980644
}
```
{% endtab %}

{% tab title="400: Bad Request NIPC inválido" %}


```json
{
    "message": {
        "version": 0.1,
        "timestamp": 1697030777756,
        "message": "O NIF/NIPC é inválido. Caso seja internacional, coloque o código do país no início. Ex.: FR12345678901 para um NIF francês."
    }
}
```
{% endtab %}

{% tab title="400: Bad Request Código RCBE inválido" %}
```
{
    "message": {
        "version": 0.1,
        "timestamp": 1697030777756,
        "message": "Declaração não encontrada para o código RCBE inserido."
    }
}
```
{% endtab %}

{% tab title="400: Bad Request Código RCBE expirado" %}
```
{
    "message": {
        "version": 0.1,
        "timestamp": 1697030777756,
        "message": "O código introduzido já não é válido. Existe um código RCBE mais recente para esta entidade, ou foi criado um rascunho que invalidou o código anterior."
    }
}
```
{% endtab %}
{% endtabs %}

{% hint style="danger" %}
**Atenção:** Infelizmente, o RCBE não apresenta informação estruturada em todas as propriedades. Deste modo, as propriedades acima descritas sem valor devem ser interpretadas como texto livre.
{% endhint %}



## Obtenção de relatório dos beneficiários efetivos a partir do RCBE

<mark style="color:green;">`POST`</mark> `https://www.pepdata.com/api/get_beneficial_owners_report`

**Headers**

| Name                                            | Type   | Value           |
| ----------------------------------------------- | ------ | --------------- |
| Authorization<mark style="color:red;">\*</mark> | string | key \[API\_KEY] |

**Body**

| Name             | Type   | Description                                                                                     |
| ---------------- | ------ | ----------------------------------------------------------------------------------------------- |
| vatin            | string | NIPC da organização a tratar                                                                    |
| rcbe\_code       | string | Código RCBE                                                                                     |
| reponsible\_name | string | <p>Nome do responsável pelo relatório.<br>Default: Nome do utilizador que efetuou o pedido.</p> |

**Response**

{% tabs %}
{% tab title="200: OK Report gerado com sucesso" %}
{% file src="../.gitbook/assets/PEPData - Relatório da Consulta do RCBE 123456789.pdf" %}
Exemplo de relatório RCBE
{% endfile %}
{% endtab %}

{% tab title="400: Bad Request NIPC inválido" %}
```json
{
    "message": {
        "version": 0.1,
        "timestamp": 1697030777756,
        "message": "O NIF/NIPC é inválido. Caso seja internacional, coloque o código do país no início. Ex.: FR12345678901 para um NIF francês."
    }
}
```
{% endtab %}

{% tab title="400: Bad Request Código RCBE inválido" %}
```
{
    "message": {
        "version": 0.1,
        "timestamp": 1697030777756,
        "message": "Declaração não encontrada para o código RCBE inserido."
    }
}
```
{% endtab %}

{% tab title="400: Bad Request Código RCBE expirado" %}
```
{
    "message": {
        "version": 0.1,
        "timestamp": 1697030777756,
        "message": "O código introduzido já não é válido. Existe um código RCBE mais recente para esta entidade, ou foi criado um rascunho que invalidou o código anterior."
    }
}
```
{% endtab %}
{% endtabs %}

{% hint style="danger" %}
**Atenção:** Infelizmente, o RCBE não apresenta informação estruturada em todas as propriedades. Deste modo, as propriedades acima descritas sem valor devem ser interpretadas como texto livre.
{% endhint %}
