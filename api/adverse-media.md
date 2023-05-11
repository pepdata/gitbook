---
description: Pesquisa de adverse media sobre uma entidade individual ou coletiva.
---

# Adverse Media

{% swagger method="post" path="" baseUrl="https://www.pepdata.com/api/get_adverse_media" summary="Obter adverse media" expanded="false" %}
{% swagger-description %}
Endpoint para obter adverse media.
{% endswagger-description %}

{% swagger-parameter in="header" name="Authentication" type="string" required="true" %}
key [API_KEY]
{% endswagger-parameter %}

{% swagger-parameter in="body" name="search_term" type="string" required="true" %}
Nome entidade/pessoa a pesquisar
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Informações sobre adverse media obtidas com sucesso." %}


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
            "count": 1
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
            "count": 1
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
            "count": 1
        }
    }
}
```
{% endswagger-response %}

{% swagger-response status="400: Bad Request" description="O campo 'search_term' é obrigatório" %}


```json
{
    "message": {
        "version": 0.1,
        "timestamp": 1683734150315,
        "message": "O campo 'search_term' é obrigatório."
    }
}
```
{% endswagger-response %}
{% endswagger %}

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
