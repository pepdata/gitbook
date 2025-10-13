# Beneficiários Efetivos

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

| Name              | Type   | Description                                                                                     |
| ----------------- | ------ | ----------------------------------------------------------------------------------------------- |
| vatin             | string | NIPC da organização a tratar                                                                    |
| rcbe\_code        | string | Código RCBE                                                                                     |
| responsible\_name | string | <p>Nome do responsável pelo relatório.<br>Default: Nome do utilizador que efetuou o pedido.</p> |

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
