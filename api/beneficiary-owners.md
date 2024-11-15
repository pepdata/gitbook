# Titulares Reales

{% hint style="warning" %}
Esta sección está todavía en versión **beta**.
{% endhint %}

## Comparación de los titulares reales con el RETIR

<mark style="color:green;">`POST`</mark> `https://www.pepdata.com/api/compare_beneficiary_owners`

Endpoint para comparar los beneficiarios reales con el portal RCBE.

#### Headers

| Name                                            | Type   | Description     |
| ----------------------------------------------- | ------ | --------------- |
| Authorization<mark style="color:red;">\*</mark> | string | key \[API\_KEY] |

#### Request Body

| Name                | Type   | Description                                                                                                                                                                                                                                 |
| ------------------- | ------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| vatin               | string | CIF de la organización a comparar                                                                                                                                                                                                           |
| beneficiary\_onwers | array  | <p>Cada elemento debe contener el siguiente formato:<br>{ <br>     "name": "Nombre completo de la persona", <br>     "birth_date": "DD/MM/YYYY",<br>     "capital_percentage": (Opcional) valor del capital, en %. Ejemplo: 91.725<br>}</p> |

{% tabs %}
{% tab title="200 Archivo PDF con la prueba de la consulta, los resultados de la comparación con el portal RCBE y la prueba de la presentación de los resultados." %}
```
```
{% endtab %}
{% endtabs %}
