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
  * found: encontrado um match unívoco no RCBE
  * ambiguous: encontrado um match ambíguo no RCBE
  * not\_found: match não encontrado no RCBE/Iberinform&#x20;
* **matches**: lista de pessoas presentes no RCBE que apresentaram match com o id\_iberinform.
* **rcbe\_person**: pessoa presente no RCBE. Ver Relevant Objects na response.
* **divergences**: objeto de divergências. Ver Relevant Objects na response.

{% swagger baseUrl="https://www.pepdata.com/api" path="/compare_beneficiary_owners" method="post" summary="Comparação de beneficiários efetivos com o RCBE" %}
{% swagger-description %}
Endpoint para comparar beneficiários efetivos com o portal do RCBE.
{% endswagger-description %}

{% swagger-parameter in="header" name="Authentication" type="string" required="true" %}
key [API_KEY]
{% endswagger-parameter %}

{% swagger-parameter in="body" name="vatin" type="string" %}
NIPC da organização a comparar
{% endswagger-parameter %}

{% swagger-parameter in="body" name="beneficiary_onwers" type="array" %}
Cada elemento deve conter o seguinte formato: 

\


{ 

\


     "name": "Nome completo da pessoa", 

\


     "birth_date": "DD/MM/YYYY",

\


     "capital_percentage": (Opcional) valor do capital, em %. Exemplo: 91.725

\


}
{% endswagger-parameter %}

{% swagger-response status="200" description="Ficheiro PDF com o comprovativo de consulta, resultados da comparação com o portal do RCBE e comprovativo da submissão dos resultados." %}
```
```
{% endswagger-response %}
{% endswagger %}
