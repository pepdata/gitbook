# Titulares Reales

{% hint style="warning" %}
Esta sección está todavía en versión **beta**.
{% endhint %}

{% swagger baseUrl="https://www.pepdata.com/api" path="/compare_beneficiary_owners" method="post" summary="Comparación de los titulares reales con el RETIR" %}
{% swagger-description %}
Endpoint para comparar los beneficiarios reales con el portal RCBE.
{% endswagger-description %}

{% swagger-parameter in="header" name="Authentication" type="string" %}
key \[API\_KEY]
{% endswagger-parameter %}

{% swagger-parameter in="body" name="vatin" type="string" %}
CIF de la organización a comparar
{% endswagger-parameter %}

{% swagger-parameter in="body" name="beneficiary_onwers" type="array" %}
Cada elemento debe contener el siguiente formato:\
{ \
&#x20;    "name": "Nombre completo de la persona", \
&#x20;    "birth\_date": "DD/MM/YYYY",\
&#x20;    "capital\_percentage": (Opcional) valor del capital, en %. Ejemplo: 91.725\
}
{% endswagger-parameter %}

{% swagger-response status="200" description="Archivo PDF con la prueba de la consulta, los resultados de la comparación con el portal RCBE y la prueba de la presentación de los resultados." %}
```
```
{% endswagger-response %}
{% endswagger %}
