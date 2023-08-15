# Integração da lista PEPData

{% swagger method="get" path="/get_list_xml_export" baseUrl="https://www.pepdata.com/api" summary="Efetua o download da lista PEPData em formato XML" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="Authentication" type="string" required="true" %}
key [API_KEY]
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}

{% endswagger-response %}
{% endswagger %}
