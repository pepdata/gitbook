# Beneficiários Efetivos

{% hint style="warning" %}
Esta secção ainda se encontra na versão **beta**.
{% endhint %}

{% swagger method="post" path="/get_iberinform_rcbe_divergences" baseUrl="https://www.pepdata.com/api" summary="Comparação dos dados da plataforma da Iberinform com o portal RCBE" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="Authentication" required="true" %}
key [API_KEY]
{% endswagger-parameter %}

{% swagger-parameter in="body" name="vatin" required="true" %}
NIPC da organização a comparar
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
```javascript
{
    "data": {
        id_iberinform_0: {
            status: 'found',
            matches: [rcbe_person_0],
            divergences
        },
        id_iberinform_1: {
            status: 'ambiguous',
            matches: [rcbe_person_1, rcbe_person_2],
            divergences
        },
        id_iberinform_2: {
            status: 'ambiguous',
            matches: [rcbe_person_3],  //same as id_iberinform_3 match
            divergences
        },
        id_iberinform_3: {
            status: 'ambiguous',
            matches: [rcbe_person_3],  //same as id_iberinform_2 match
            divergences
        },
        id_iberinform_4: {
            status: 'not_found',
            matches: [],
            divergences
        },
        '': {
            status: 'not_found',
            matches: [rcbe_person_4, rcbe_person_5],
            divergences
        }
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
//    birth_date: boolean,
//    shares_percentage: boolean,
// }
```
{% endswagger-response %}
{% endswagger %}

### Legenda

* **id\_iberinform**: id do sistema da Iberinform. Pode ser vazio de forma a agregar todas as pessoas do RCBE sem match no sistema da Iberinform.
* **status**:&#x20;
  * found: encontrada uma correspondência unívoca no RCBE
  * ambiguous: encontradas correspondências ambíguas no RCBE
  * not\_found: não foram encontradas correspondências no RCBE
* **matches**: lista de pessoas presentes no RCBE que apresentaram correspondência com a pessoa.
* **rcbe\_person**: pessoa presente no RCBE. Ver Relevant Objects na response.
* **divergences**: objeto de divergências. Ver Relevant Objects na response.



{% swagger baseUrl="https://www.pepdata.com/api" path="/get_beneficial_owners" method="post" summary="Obtenção dos beneficiários efetivos a partir do RCBE" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="Authentication" type="string" required="true" %}
key [API_KEY]
{% endswagger-parameter %}

{% swagger-parameter in="body" name="vatin" type="string" required="true" %}
NIPC da organização a tratar
{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
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
{% endswagger-response %}
{% endswagger %}

{% hint style="danger" %}
**Atenção:** Infelizmente, o RCBE não apresenta informação estruturada em todas as propriedades. Deste modo, as propriedades acima descritas sem valor devem ser interpretadas como texto livre.
{% endhint %}



{% swagger method="post" path="/get_beneficial_owners_divergences" baseUrl="https://www.pepdata.com/api" summary="Comparação de beneficiários efetivos com o RCBE" %}
{% swagger-description %}
Endpoint para comparação entre os beneficiários efetivos do seu sistema e o portal do RCBE.
{% endswagger-description %}

{% swagger-parameter in="body" name="vatin" type="string" required="true" %}
NIPC da organização a comparar
{% endswagger-parameter %}

{% swagger-parameter in="header" name="Authentication" required="true" type="string" %}
key [API_KEY]
{% endswagger-parameter %}

{% swagger-parameter in="body" required="true" name="beneficial_owners" type="array" %}
Cada elemento deve conter o seguinte formato: \
{ \
&#x20;    "id": "Identificador da pessoa",

&#x20;    "name": "Nome completo da pessoa", \
&#x20;    "birth\_date": "DD/MM/YYYY",\
&#x20;    "capital\_percentage": (Opcional) valor do capital, em %. Exemplo: 91.725\
}
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
```javascript
{
    "data": {
        id_0: {
            status: 'found',
            matches: [rcbe_person_0],
            divergences
        },
        id_1: {
            status: 'ambiguous',
            matches: [rcbe_person_1, rcbe_person_2],
            divergences
        },
        id_2: {
            status: 'ambiguous',
            matches: [rcbe_person_3],  //same as id_iberinform_3 match
            divergences
        },
        id_3: {
            status: 'ambiguous',
            matches: [rcbe_person_3],  //same as id_iberinform_2 match
            divergences
        },
        id_4: {
            status: 'not_found',
            matches: [],
            divergences
        },
        '': {
            status: 'not_found',
            matches: [rcbe_person_4, rcbe_person_5],
            divergences
        }
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
//    birth_date: boolean,
//    shares_percentage: boolean,
// }
```
{% endswagger-response %}
{% endswagger %}

### Legenda

* **id**: identificador da pessoa a analisar. Este pode ter qualquer valor à escolha do utilizador, existindo apenas a obrigatoriedade de ser único entre os beneficial\_owners a comparar. Pode ser vazio de forma a agregar todas as pessoas do RCBE sem correspondência com os beneficial\_owners a comparar.
* **status**:&#x20;
  * found: encontrada uma correspondência unívoca no RCBE
  * ambiguous: encontradas correspondências ambíguas no RCBE
  * not\_found: não foram encontradas correspondências no RCBE
* **matches**: lista de pessoas presentes no RCBE que apresentaram correspondência com a pessoa.
* **rcbe\_person**: pessoa presente no RCBE. Ver Relevant Objects na response.
* **divergences**: objeto de divergências. Ver Relevant Objects na response.
