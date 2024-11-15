---
description: Pesquisa de adverse media sobre uma entidade individual ou coletiva.
---

# Adverse Info

## Obter adverse media

{% hint style="danger" %}
Este endpoint irá ser descontinuado em função do endpoint seguinte (ver abaixo).
{% endhint %}

<mark style="color:green;">`POST`</mark> `https://www.pepdata.com/api/get_adverse_media`

Endpoint para obter adverse media.

#### Headers

| Name                                            | Type   | Description     |
| ----------------------------------------------- | ------ | --------------- |
| Authorization<mark style="color:red;">\*</mark> | string | key \[API\_KEY] |

#### Request Body

| Name                                           | Type   | Description                      |
| ---------------------------------------------- | ------ | -------------------------------- |
| search\_term<mark style="color:red;">\*</mark> | string | Nome entidade/pessoa a pesquisar |

{% tabs %}
{% tab title="200: OK Informações sobre adverse media obtidas com sucesso." %}
```json
{
    "version": 0.1,
    "timestamp": 1683734308978,
    "data": {
        "icij_adverse_media": {
            "items": [
                {
                    "entity": "Lisa Fidalgo Corte-Real",
                    "source": "Panama Papers"
                }
            ],
        },
        "google_adverse_media": {
            "items": [
                {
                    "title": "Lisa Fidalgo Corte-Real vai ser julgada por ...",
                    "description": "Lisa Fidalgo Corte-Real vai ser julgada por corrupção ... vir a ser condenada também por branqueamento de capitais e fraude fiscal.",
                    "source": "https://test-link.pt",
                    "date": "2023-04-14"
                }
            ],
        },
        "judicial_processes": {
            "items": [
                {
                    "entry_number": 12345678,
                    "entry_date": "2022-04-13",
                    "distribution_date": "2022-04-13",
                    "end_date": "2023-04-13",
                    "organ": "Juízo de Execução de Águeda",
                    "process_code": "000/00.0A0AGD",
                    "process_value": "12460.27",
                    "observations": "Execução Ordinária (Ag.Execução) Entrega Electrónica - Refª 12345678"
                }
            ],
        }
    }
}
```
{% endtab %}

{% tab title="400: Bad Request O campo 'search_term' é obrigatório." %}
```json
{
    "message": {
        "version": 0.1,
        "timestamp": 1683734150315,
        "message": "O campo 'search_term' é obrigatório."
    }
}
```
{% endtab %}
{% endtabs %}

{% hint style="info" %}
A consulta inclui: **pesquisas em motores de busca** (associadas ao tema de PBCFT), **processos judiciais e listas de leaks** (Pandora Papers, Paradise Papers, Bahamas Leaks, Panama Papers e Offshore Leaks).\
\
As legendas serão referentes aos campos disponíveis em cada uma das diferentes fontes.
{% endhint %}

### Legenda ICIJ (International Consortium of Investigative Journalists)

* entity: nome da entidade
* source: lista onde foi encontrada informação da entidade

### Legenda motores de busca (Google)

* title: título da notícia
* description: descrição da notícia
* source: link para fonte da notícia
* date: data da notícia

### Legenda processos judiciais

* entry\_number: número de entrada do processo
* entry\_date: data de entrada
* distribution\_date: data de distribuição
* end\_date: data de extinção
* organ: unidade orgânica
* process\_code: código do processo
* process\_value: valor do processo (em euros)
* observations: espécie e observações

## Obter informação adversa

<mark style="color:green;">`POST`</mark> `https://www.pepdata.com/api/get_adverse_info`

Endpoint para obter informação adversa.

{% hint style="warning" %}
A utilização deste endpoint requer a configuração prévia de um webhook na página de configurações, uma vez que a resposta poderá demorar vários minutos a ser obtida, por ser realizada em tempo real.

Todas as chamadas ao webhook incluem um header "Authorization" que contém uma chave de autenticação  que precisa de ser validada. Essa chave de autenticação pode ser encontrada na página de configurações.
{% endhint %}

#### Headers

| Name                                            | Type   | Description     |
| ----------------------------------------------- | ------ | --------------- |
| Authorization<mark style="color:red;">\*</mark> | string | key \[API\_KEY] |

#### Request Body

| Name                                            | Type   | Description                                                                                                                                                                                 |
| ----------------------------------------------- | ------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| search\_term<mark style="color:red;">\*</mark>  | string | Nome entidade/pessoa a pesquisar                                                                                                                                                            |
| data\_sources<mark style="color:red;">\*</mark> | array  | <p>Especificação das fontes de dados a pesquisar.</p><p>Valores aceites:</p><p><strong>forensic</strong></p><p><strong>adverse_media</strong></p><p><strong>judicial_processes</strong></p> |
|                                                 |        |                                                                                                                                                                                             |

{% tabs %}
{% tab title="200: OK Informações sobre adverse media obtidas com sucesso." %}
```json
{
    "version": 0.1,
    "timestamp": 1683734308978,
    "data": {
        "forensic": {
            "items": [
                {
                    "entity": "Lisa Fidalgo Corte-Real",
                    "source": "Panama Papers"
                }
            ],
        },
        "adverse_media": {
            "items": [
                {
                    "title": "Lisa Fidalgo Corte-Real vai ser julgada por ...",
                    "description": "Lisa Fidalgo Corte-Real vai ser julgada por corrupção ... vir a ser condenada também por branqueamento de capitais e fraude fiscal.",
                    "source": "https://test-link.pt",
                    "date": "2023-04-14"
                }
            ],
        },
        "judicial_processes": {
            "items": [
                {
                    "entry_number": 12345678,
                    "entry_date": "2022-04-13",
                    "distribution_date": "2022-04-13",
                    "end_date": "2023-04-13",
                    "organ": "Juízo de Execução de Águeda",
                    "process_code": "000/00.0A0AGD",
                    "process_value": "12460.27",
                    "observations": "Execução Ordinária (Ag.Execução) Entrega Electrónica - Refª 12345678"
                }
            ],
        }
    }
}
```
{% endtab %}

{% tab title="400: Bad Request O campo 'search_term' é obrigatório." %}
```json
{
    "message": {
        "version": 0.1,
        "timestamp": 1683734150315,
        "message": "O campo 'search_term' é obrigatório."
    }
}
```
{% endtab %}
{% endtabs %}

### Legenda (Forensic)

* entity: nome da entidade
* source: lista onde foi encontrada informação da entidade

### Legenda (Adverse media)

* title: título da notícia
* description: descrição da notícia
* source: link para fonte da notícia
* date: data da notícia

### Legenda (Judicial Processes)

* entry\_number: número de entrada do processo
* entry\_date: data de entrada
* distribution\_date: data de distribuição
* end\_date: data de extinção
* organ: unidade orgânica
* process\_code: código do processo
* process\_value: valor do processo (em euros)
* observations: espécie e observações
