# Validações

{% api-method method="post" host="https://www.pepdata.com/api" path="/get\_validations" %}
{% api-method-summary %}
Obter validações
{% endapi-method-summary %}

{% api-method-description %}
Endpoint para obter validações.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authentication" type="string" required=true %}
key \[API\_KEY\]
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="page" type="number" required=false %}
Página das validações  
Default: 1
{% endapi-method-parameter %}

{% api-method-parameter name="source" type="string" required=false %}
Origem das validações  
Default: all  
Valores possíveis: all, upload, manual
{% endapi-method-parameter %}

{% api-method-parameter name="status" type="string" required=false %}
Estado das validações   
Default: incomplete  
Valores possíveis: all, complete, complete\_identified, complete\_not\_identified, complete\_needs\_attention, incomplete
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Validações obtidas com sucesso.
{% endapi-method-response-example-description %}

```
{
    "data": {
        "items": [
            {
                "id": "2a206d4a-0a5d-4a04-9a0c-cadae6e2cffa", 
                "name": "Lisa Fidalgo Corte-Real",
                "birth_date": "01-08-1986",
                "id_country": "PT",
                "source": "Manual",
                "added_at": 1588003603593,
                "added_by": "839a5871-fa0e-470a-af42-9110f8ef5b27",
                "decision": null,
                "id_iperson": null,
                "determined_at": null,
                "determined_by": null,
                "needs_attention": 0
            },
            {
                "id": "01a0ae72-bff9-47df-a7ec-843a7524d67e", 
                "name": "Baltasar Lousada Vieira",
                "birth_date": null,
                "id_country": null,
                "source": "Automatic",
                "added_at": 1588008603595,
                "added_by": "839a5871-fa0e-470a-af42-9110f8ef5b27",,
                "decision": 1,
                "id_iperson": "d37903e9-589b-4db8-a9e0-efd69d89bf6b",
                "determined_at": 1588009503831,
                "determined_by": "0d874a7f-a94b-4b0c-ba48-47a278f12065",
                "needs_attention": 0
            }
        ],
        "page": 1,
        "max_results_per_page": 50
        "total": 2
    },
    "version": "0.1",
    "timestamp": 1588599744111
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

### Legenda

* **id**: id da validação.
* **name**: nome da validação.
* **birth\_date**: data de nascimento da validação.
* **id\_country**: país da validação, no formato [ISO 3166-1 alpha-2](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2).
* **country\_sanctioned**: booleano que descreve se o país da validação se encontra [sancionado ](../glossario/glossario-aplicacao.md#pais-sancionado)\(1\) ou não \(0\).
* **source**: origem da validação. 
* **added\_at**: data a que a validação foi adicionada, sob a forma de número de milissegundos desde 1 de Janeiro de 1970 00:00:00 UTC.
* **added\_by**: id do utilizador que [adicionou ](../a-aplicacao/validacoes/#adicao-determinacao-e-estados-de-validacoes)a validação.
* **decision**: booleano que descreve se existiu correspondência com uma pessoa identificável \(1\) ou não \(0\).
* **id\_iperson**: id da pessoa identificável correspondente. null caso não tenha existido correspondência.
* **determined\_at**: data a que a validação foi determinada, sob a forma de número de milissegundos desde 1 de Janeiro de 1970 00:00:00 UTC.
* **determined\_by**: id do utilizador que [determinou ](../a-aplicacao/validacoes/#adicao-determinacao-e-estados-de-validacoes)a validação.
* **needs\_attention**: booleano que descreve se a validação [precisa de atenção](../a-aplicacao/validacoes/#validacoes-que-necessitam-de-atencao) \(1\) ou não \(0\).

{% api-method method="post" host="https://www.pepdata.com/api" path="/add\_validation" %}
{% api-method-summary %}
Adicionar validação
{% endapi-method-summary %}

{% api-method-description %}
Endpoint para adicionar uma validação.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authentication" type="string" required=true %}
key \[API\_KEY\]
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="ignore\_duplicates" type="boolean" required=false %}
Instrução para ignorar a verificação de duplicados.  
Formato: 0/1  
Default: 0
{% endapi-method-parameter %}

{% api-method-parameter name="name" type="string" required=true %}
Nome da validação
{% endapi-method-parameter %}

{% api-method-parameter name="birth\_date" type="string" required=false %}
Data de nascimento da validação.   
Formato: yyyy-mm-dd  
Default: null
{% endapi-method-parameter %}

{% api-method-parameter name="country" type="string" required=false %}
País da validação.   
Formato: Nome do país \(ver nota abaixo\)  
Default: null
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Validação adicionada com sucesso.
{% endapi-method-response-example-description %}

```

{
    "data": {
        "id": "926b7dab-a3af-986f-2137-872adb95260f"
    },
    "version": "0.1",
    "timestamp": 1588599744111
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}
A validação a adicionar já se encontra na base de dados.
{% endapi-method-response-example-description %}

```
{
    "message": "Esta validação parece já existir na base de dados"
    "version": "versão da API",
    "timestamp": X 
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

### Legenda

* **id**: id da validação criada.

{% hint style="info" %}
#### Country

* Existem múltiplas formas distintas de se escrever o nome de cada país. A aplicação da PEPData consegue identificar todas as designações dos países presentes na [Lista dos Estados, territórios e moedas da União Europeia](https://publications.europa.eu/code/pt/pt-5000500.htm). No entanto, de forma a garantir maior robustez, recomendamos a utilização do formato [ISO 3166-1 alpha-2](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2), sempre que possível.
{% endhint %}



{% api-method method="post" host="https://www.pepdata.com/api" path="/analyze\_validation" %}
{% api-method-summary %}
Analisar validação
{% endapi-method-summary %}

{% api-method-description %}
Endpoint para consultar os resultados obtidos da análise de uma validação.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authentication" type="string" required=true %}
key \[API\_KEY\]
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="id" type="string" required=true %}
Id da validação
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Resultados da análise de validação obtidos com sucesso.
{% endapi-method-response-example-description %}

```
{
    "data": {
        "items": [
            {
              "id": "0bdeb685-8d0b-41ec-a3ff-996188fe2b22",
              "name": "João Pedro Silva",
              "birth_date": null,
              "score": 95
            },
            {
              "id": "BFFD688C-4618-048D-9C14-8887B1BDA173",
              "name": "João Pedro Pereira",
              "birth_date": "1933-05-25",
              "score": 76
            }
        ]
    },
    "version": "0.1",
    "timestamp": 1588599744111
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

### Legenda

* **id**: id da pessoa identificável.
* **name**: nome da pessoa identificável.
* **birth\_date**: data de nascimento da pessoa identificável.
* **score**: [grau de semelhança](../glossario/glossario-aplicacao.md#grau-de-semelhanca).

{% api-method method="post" host="https://www.pepdata.com/api" path="/determine\_validation" %}
{% api-method-summary %}
Determinação de validação
{% endapi-method-summary %}

{% api-method-description %}
Endpoint para submeter uma validação.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authentication" type="string" required=true %}
key \[API\_KEY\]
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="id" type="string" required=true %}
Id da validação
{% endapi-method-parameter %}

{% api-method-parameter name="id\_iperson" type="string" required=false %}
Id da pessoa identificável correspondente. 
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
A validação foi submetida com sucesso.
{% endapi-method-response-example-description %}

```
{
    "data": {},
    "version": "0.1",
    "timestamp": 1588599744111
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="post" host="https://www.pepdata.com/api" path="/cancel\_validation" %}
{% api-method-summary %}
Cancelar determinação de validação
{% endapi-method-summary %}

{% api-method-description %}
Endpoint para cancelar a determinação de uma validação.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authentication" type="string" required=true %}
key \[API\_KEY\]
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="id" type="string" required=true %}
Id da validação
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
A determinação da validação foi cancelada com sucesso.
{% endapi-method-response-example-description %}

```
{
    "data": {},
    "version": "0.1",
    "timestamp": 1588599744111
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="post" host="https://www.pepdata.com/api" path="/delete\_validation" %}
{% api-method-summary %}
Apagar validação
{% endapi-method-summary %}

{% api-method-description %}
Endpoint para apagar uma validação.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authentication" type="string" required=true %}
key \[API\_KEY\]
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="id" type="string" required=true %}
Id da validação
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
A validação foi apagada com sucesso.
{% endapi-method-response-example-description %}

```
{
    "data": {},
    "version": "0.1",
    "timestamp": 1588599744111
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% hint style="info" %}
Apenas pode apagar validações [incompletas](../a-aplicacao/validacoes/#adicao-determinacao-e-estados-de-validacoes). Caso pretenda apagar uma validação completa, terá primeiro de cancelar a sua [determinação](../a-aplicacao/validacoes/#adicao-determinacao-e-estados-de-validacoes).
{% endhint %}

{% api-method method="post" host="https://www.pepdata.com/api" path="/apply\_rules" %}
{% api-method-summary %}
Aplicação das regras
{% endapi-method-summary %}

{% api-method-description %}
Endpoint para aplicação das regras de validação.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authentication" type="string" required=true %}
key \[API\_KEY\]
{% endapi-method-parameter %}
{% endapi-method-headers %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
As regras começaram a ser aplicadas. 
{% endapi-method-response-example-description %}

```
{
    "data": {
        "time_to_conclusion": X
    },
    "version": "0.1",
    "timestamp": 1588599744111
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

### Legenda

* **time\_to\_conclusion**: tempo **previsto** para a conclusão da aplicação das regras, em segundos.

{% hint style="warning" %}
A leitura da documentação relativa à [aplicação das regras de validação](../a-aplicacao/validacoes/aplicacao-de-regras.md) é fortemente recomendada, uma vez que a aplicação sem a sua correta compreensão poderá provocar alterações indesejadas.
{% endhint %}

{% hint style="info" %}
A [aplicação de regras](../a-aplicacao/validacoes/aplicacao-de-regras.md) pode demorar alguns minutos até se encontrar concluída, dependendo do número de validações incompletas existentes. O tempo de conclusão estimado é devolvido na resposta.
{% endhint %}

