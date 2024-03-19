# Pesquisa

## Pesquisa de pessoa identificável

<mark style="color:green;">`POST`</mark> `https://www.pepdata.com/api/search_iperson`

Endpoint para pesquisar uma pessoa identificável.

#### Headers

| Name                                             | Type   | Description     |
| ------------------------------------------------ | ------ | --------------- |
| Authentication<mark style="color:red;">\*</mark> | string | key \[API\_KEY] |

#### Request Body

| Name                                   | Type   | Description                                                                                           |
| -------------------------------------- | ------ | ----------------------------------------------------------------------------------------------------- |
| name<mark style="color:red;">\*</mark> | string | Nome da pessoa a pesquisar                                                                            |
| birth\_date                            | string | <p>Data de nascimento da validação.</p><p>\</p><p>Formato: yyyy-mm-dd</p><p>\</p><p>Default: null</p> |

{% tabs %}
{% tab title="200: OK Pesquisa realizada com sucesso." %}
```
{
    "data": {
        "items": [
            {
              "id": "0bdeb685-8d0b-41ec-a3ff-996188fe2b22",
              "name": "João Pedro Silva",
              "birth_date": null,
              "death_date": null,
              "id_country": "PT",
              "score": 95,
              "country": "Portugal"
            },
            {
              "id": "d7c48e2d-8699-4064-b94c-d6e2106fdf85",
              "name": "João Pedro Pereira",
              "birth_date": "1933-05-25",
              "death_date": null,
              "id_country": "PT",
              "score": 76,
              "country": "Portugal"
            }
        ]
    },
    "version": "0.1",
    "timestamp": 1588599744111
}
```
{% endtab %}

{% tab title="400: Bad Request Nome inválido" %}


```json
{
    "message": {
        "version": 0.1,
        "timestamp": 1697029877505,
        "message": "O nome é inválido. Só são permitidos nomes:  • Com apenas caracteres latinos, apóstrofes, espaços, pontos ou hífenes;"
    }
}
```
{% endtab %}
{% endtabs %}

### Legenda

* **id**: id da pessoa identificável.
* **name**: nome da pessoa identificável.
* **birth\_date**: data de nascimento da pessoa identificável.
* **death\_date**: data de morte da pessoa identificável.
* **id\_country**: país primário da pessoa identificável, no formato [ISO 3166-1 alpha-2](https://en.wikipedia.org/wiki/ISO\_3166-1\_alpha-2).
* **source**: fonte da lista de sanções, caso exista: EU, OFAC, HMTreasury ou UN.
* **score**: [grau de semelhança](../glossario/glossario-aplicacao.md#grau-de-semelhanca).
* **country:** país primário da pessoa identificável.

{% hint style="info" %}
De forma a obter melhores resultados, recomenda-se que leia a documentação referente à área de [pesquisa](../a-aplicacao/pesquisa/).
{% endhint %}

## Pesquisa de organizações sancionadas

<mark style="color:green;">`POST`</mark> `https://www.pepdata.com/api/search_organization`

Endpoint para pesquisar uma organização sancionada.

#### Headers

| Name                                             | Type   | Description     |
| ------------------------------------------------ | ------ | --------------- |
| Authentication<mark style="color:red;">\*</mark> | string | key \[API\_KEY] |

#### Request Body

| Name                                   | Type   | Description                     |
| -------------------------------------- | ------ | ------------------------------- |
| name<mark style="color:red;">\*</mark> | string | Nome da organização a pesquisar |

{% tabs %}
{% tab title="200: OK Pesquisa realizada com sucesso." %}
```
{
    "data": {
        "items": [
            {
                "id": "894e61ca-0264-0ed2-542c-d5aa53ef407c",
                "name": "Fekete Szeptember",
                "score": 100
            }
        ]
    },
    "version": "0.1",
    "timestamp": 1588599744111
}
```
{% endtab %}

{% tab title="400: Bad Request Nome não introduzido" %}


```json
{
    "message": {
        "version": 0.1,
        "timestamp": 1697030330542,
        "message": "Por favor introduza o nome a pesquisar."
    }
}
```
{% endtab %}
{% endtabs %}

### Legenda

* **id:** id da organização sancionada.
* **name**: nome da organização sancionada.
* **score**: [grau de semelhança](../glossario/glossario-aplicacao.md#grau-de-semelhanca).

{% hint style="info" %}
Este endpoint executa uma pesquisa nas organizações presentes nas seguintes listas de sanções internacionais:

* United Nations Security Council Consolidated List
* EU Financial Sanctions Database
* OFAC Specially Designated Nationals and Blocked Persons List
* HM Treasury Financial Sanctions Targets

**Importante:** de momento, o nome da organização deverá coincidir com o nome presente na lista de sanções para que sejam devolvidos resultados.
{% endhint %}
