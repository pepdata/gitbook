# Integração da lista PEPData

## Efetua o download da lista PEPData em formato XML

<mark style="color:blue;">`GET`</mark> `https://www.pepdata.com/api/get_list_xml_export`

#### Headers

| Name                                             | Type   | Description     |
| ------------------------------------------------ | ------ | --------------- |
| Authentication<mark style="color:red;">\*</mark> | string | key \[API\_KEY] |

{% tabs %}
{% tab title="200: OK " %}

{% endtab %}
{% endtabs %}

## Efetua o download da lista PEPData em formato ZIP

<mark style="color:blue;">`GET`</mark> `https://www.pepdata.com/api/get_list_xml_export_zip/{token}`

{% hint style="info" %}
A informação "token" deve ser substituida pelo token de autorização especifico da organização.&#x20;
{% endhint %}

#### Headers

| Name                                             | Type   | Description     |
| ------------------------------------------------ | ------ | --------------- |
| Authentication<mark style="color:red;">\*</mark> | string | key \[API\_KEY] |

{% tabs %}
{% tab title="200: OK" %}

{% endtab %}
{% endtabs %}
