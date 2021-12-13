# Beneficiários Efetivos

{% hint style="warning" %}
Esta secção ainda se encontra na versão **beta**.
{% endhint %}

{% swagger baseUrl="https://www.pepdata.com/api" path="/compare_beneficiary_owners" method="post" summary="Comparação de beneficiários efetivos com o RCBE" %}
{% swagger-description %}
Endpoint para comparar beneficiários efetivos com o portal do RCBE.
{% endswagger-description %}

{% swagger-parameter in="header" name="Authentication" type="string" %}
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
