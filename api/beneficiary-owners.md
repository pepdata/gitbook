# Beneficiários Efectivos

{% hint style="warning" %}
Esta sección está todavía en versión **beta**.
{% endhint %}

{% api-method method="post" host="https://www.pepdata.com/api" path="/compare\_beneficiary\_owners" %}
{% api-method-summary %}
Comparación de los beneficiarios reales con el RCBE
{% endapi-method-summary %}

{% api-method-description %}
Endpoint para comparar los beneficiarios reales con el portal RCBE.
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
CIF de la organización a comparar
{% endapi-method-parameter %}

{% api-method-parameter name="beneficiary\_onwers" type="array" required=true %}
Cada elemento debe contener el siguiente formato:  
{   
     "name": "Nombre completo de la persona",   
     "birth\_date": "DD/MM/YYYY",  
     "capital\_percentage": \(Opcional\) valor del capital, en %. Ejemplo: 91.725  
}
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Archivo PDF con la prueba de la consulta, los resultados de la comparación con el portal RCBE y la prueba de la presentación de los resultados.
{% endapi-method-response-example-description %}

```

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

