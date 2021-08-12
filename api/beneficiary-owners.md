# Beneficiários Efetivos

{% hint style="warning" %}
Esta secção ainda se encontra na versão **beta**.
{% endhint %}

{% api-method method="post" host="https://www.pepdata.com/api" path="/compare\_beneficiary\_owners" %}
{% api-method-summary %}
Comparação de beneficiários efetivos com o RCBE
{% endapi-method-summary %}

{% api-method-description %}
Endpoint para comparar beneficiários efetivos com o portal do RCBE.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authentication" type="string" required=true %}
key \[API\_KEY\]
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="vatin" type="string" required=true %}
NIPC da organização a comparar
{% endapi-method-parameter %}

{% api-method-parameter name="beneficiary\_onwers" type="array" required=true %}
Cada elemento deve conter o seguinte formato:   
{   
     "name": "Nome completo da pessoa",   
     "birth\_date": "DD/MM/YYYY",  
     "capital\_percentage": \(Opcional\) valor do capital, em %. Exemplo: 91.725  
}
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Ficheiro PDF com o comprovativo de consulta, resultados da comparação com o portal do RCBE e comprovativo da submissão dos resultados.
{% endapi-method-response-example-description %}

```

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

