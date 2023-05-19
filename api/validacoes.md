# Validações

{% swagger baseUrl="https://www.pepdata.com/api" path="/get_validations" method="post" summary="Obter validações" %}
{% swagger-description %}
Endpoint para obter validações.
{% endswagger-description %}

{% swagger-parameter in="header" name="Authentication" type="string" required="true" %}
key [API_KEY]
{% endswagger-parameter %}

{% swagger-parameter in="body" name="page" type="number" %}
Página das validações

\


Default: 1
{% endswagger-parameter %}

{% swagger-parameter in="body" name="source" type="string" %}
Origem das validações

\


Default: all

\


Valores possíveis: all, upload, manual
{% endswagger-parameter %}

{% swagger-parameter in="body" name="status" type="string" %}
Estado das validações 

\


Default: all

\


Valores possíveis: all, complete, complete_identified, complete_not_identified, complete_needs_attention, incomplete
{% endswagger-parameter %}

{% swagger-parameter in="body" name="id" type="string" %}
Id da validação
{% endswagger-parameter %}

{% swagger-parameter in="body" name="id_custom" type="string" %}
Id personalizável da validação
{% endswagger-parameter %}

{% swagger-response status="200" description="Validações obtidas com sucesso." %}
```
{
    "data": {
        "items": [
            {
                "id": "2a206d4a-0a5d-4a04-9a0c-cadae6e2cffa", 
                "name": "Lisa Fidalgo Corte-Real",
                "birth_date": "1986-01-08",
                "id_country": "PT",
                "country_sanctioned": false,
                "source": "Manual",
                "added_at": 1588003603593,
                "added_by": "839a5871-fa0e-470a-af42-9110f8ef5b27",
                "decision": null,
                "id_iperson": null,
                "determined_at": null,
                "determined_by": null,
                "needs_attention": false,
                "id_custom": "ID1"
            },
            {
                "id": "01a0ae72-bff9-47df-a7ec-843a7524d67e", 
                "name": "Baltasar Lousada Vieira",
                "birth_date": null,
                "id_country": null,
                "country_sanctioned": false,
                "source": "Automatic",
                "added_at": 1588008603595,
                "added_by": "839a5871-fa0e-470a-af42-9110f8ef5b27",,
                "decision": true,
                "id_iperson": "d37903e9-589b-4db8-a9e0-efd69d89bf6b",
                "determined_at": 1588009503831,
                "determined_by": "0d874a7f-a94b-4b0c-ba48-47a278f12065",
                "needs_attention": false,
                "id_custom": null
            }
        ],
        "page": 1,
        "max_results_per_page": 50
    },
    "version": "0.1",
    "timestamp": 1588599744111
}
```
{% endswagger-response %}
{% endswagger %}

### Legenda

* **id**: id da validação.
* **vatin**: NIF da validação.
* **name**: nome da validação.
* **birth\_date**: data de nascimento da validação.
* **id\_country\_nationality**: código do país da nacionalidade, no formato [ISO 3166-1 alpha-2](https://en.wikipedia.org/wiki/ISO\_3166-1\_alpha-2).
* **id\_country\_address**: código do país de residência, no formato [ISO 3166-1 alpha-2](https://en.wikipedia.org/wiki/ISO\_3166-1\_alpha-2).
* **country\_sanctioned**: booleano que descreve se o país da validação se encontra [sancionado](../glossario/glossario-aplicacao.md#pais-sancionado).
* **source**: origem da validação.&#x20;
* **added\_at**: data a que a validação foi adicionada, sob a forma de número de milissegundos desde 1 de Janeiro de 1970 00:00:00 UTC.
* **added\_by**: id do utilizador que [adicionou ](../a-aplicacao/validacoes/#adicao-determinacao-e-estados-de-validacoes)a validação.
* **decision**: booleano que descreve se existiu correspondência com uma pessoa identificável.
* **id\_iperson**: id da pessoa identificável correspondente. null caso não tenha existido correspondência.
* **determined\_at**: data a que a validação foi determinada, sob a forma de número de milissegundos desde 1 de Janeiro de 1970 00:00:00 UTC.
* **determined\_by**: id do utilizador que [determinou ](../a-aplicacao/validacoes/#adicao-determinacao-e-estados-de-validacoes)a validação.
* **needs\_attention**: booleano que descreve se a validação [precisa de atenção](../a-aplicacao/validacoes/#validacoes-que-necessitam-de-atencao).
* **id\_custom**: id personalizável inserido pelo utilizador.

{% hint style="info" %}
**id\_country\_nationality e id\_country\_address**

* Existem múltiplas formas distintas de se escrever o nome de cada país. A aplicação da PEPData consegue identificar todas as designações dos países presentes na [Lista dos Estados, territórios e moedas da União Europeia](https://publications.europa.eu/code/pt/pt-5000500.htm). No entanto, de forma a garantir maior robustez, recomendamos a utilização do formato [ISO 3166-1 alpha-2](https://en.wikipedia.org/wiki/ISO\_3166-1\_alpha-2), sempre que possível.
{% endhint %}

{% swagger baseUrl="https://www.pepdata.com/api" path="/add_validation" method="post" summary="Adicionar validação" %}
{% swagger-description %}
Endpoint para adicionar uma validação.
{% endswagger-description %}

{% swagger-parameter in="header" name="Authentication" type="string" %}
key [API_KEY]
{% endswagger-parameter %}

{% swagger-parameter in="body" name="ignore_duplicates" type="boolean" %}
Instrução para ignorar a verificação de duplicados.

\


Formato: 0/1

\


Default: 0
{% endswagger-parameter %}

{% swagger-parameter in="body" name="vatin" type="string" %}
NIF da validação

\


Default: null
{% endswagger-parameter %}

{% swagger-parameter in="body" name="name" type="string" %}
Nome da validação
{% endswagger-parameter %}

{% swagger-parameter in="body" name="birth_date" type="string" %}
Data de nascimento da validação. 

\


Formato: yyyy-mm-dd

\


Default: null
{% endswagger-parameter %}

{% swagger-parameter in="body" name="country_nationality" type="string" %}
País de nacionalidade da validação. 

\


Formato: Nome do país (ver nota abaixo)

\


Default: null
{% endswagger-parameter %}

{% swagger-parameter in="body" name="country_address" type="string" %}
País de residência da validação.

Formato: Nome do país (ver nota abaixo)\
Default: null
{% endswagger-parameter %}

{% swagger-parameter in="body" name="id_custom" type="string" %}
Id personalizável da validação

\


Default: null
{% endswagger-parameter %}

{% swagger-response status="200" description="Validação adicionada com sucesso." %}
```

{
    "data": {
        "id": "926b7dab-a3af-986f-2137-872adb95260f"
    },
    "version": "0.1",
    "timestamp": 1588599744111
}
```
{% endswagger-response %}

{% swagger-response status="400" description="A validação a adicionar já se encontra na base de dados." %}
```
{
    "message": "Esta validação parece já existir na base de dados"
    "version": "versão da API",
    "timestamp": X 
}
```
{% endswagger-response %}
{% endswagger %}

### Legenda

* **id**: id da validação criada.



{% swagger baseUrl="https://www.pepdata.com/api" path="/analyze_validation" method="post" summary="Analisar validação" %}
{% swagger-description %}
Endpoint para consultar os resultados obtidos da análise de uma validação.
{% endswagger-description %}

{% swagger-parameter in="header" name="Authentication" type="string" %}
key [API_KEY]
{% endswagger-parameter %}

{% swagger-parameter in="body" name="id" type="string" %}
Id da validação
{% endswagger-parameter %}

{% swagger-parameter in="body" name="include_iperson_details" type="boolean" %}
Incluir informação acerca das classificações, ocupações e relações das pessoas identificáveis.\
Formato: true/false

Default: false
{% endswagger-parameter %}

{% swagger-response status="200" description="Resultados da análise de validação obtidos com sucesso." %}
```
{
    "data": {
        "items": [
            {
              "id": "0bdeb685-8d0b-41ec-a3ff-996188fe2b22",
              "name": "João Pedro Silva",
              "birth_date": null,
              "score": 95
              "classifications": [
                    "PEP"
                ],
                "occupations": [
                    {
                        "organization": "Governo da República Portuguesa",
                        "organ": "Ministério dos Negócios Estrangeiros",
                        "position": "Ministro",
                        "source": "https://test-link.com",
                        "start_date": null,
                        "end_date": null,
                        "comments": null
                    }
                ],
                "relationships": []
            },
            {
              "id": "BFFD688C-4618-048D-9C14-8887B1BDA173",
              "name": "João Pedro Pereira",
              "birth_date": "1933-05-25",
              "score": 76,
              "classifications": [
                    "PEP",
                    "Familiar"
                ],
                "occupations": [
                    {
                        "organization": "Governo da República Portuguesa",
                        "organ": "Ministério dos Negócios Estrangeiros",
                        "position": "Ministro",
                        "source": "https://test-link.com",
                        "start_date": "2005-01-01",
                        "end_date": "2030-01-01",
                        "comments": null
                    }
                ],
                "relationships": [
                    {
                        "relationship_type": "son",
                        "relationship_to": "Flávio Alberto Roldão",
                        "source": "https://test-link.com",
                        "end_date": null,
                        "comments": null
                    },
                    {
                        "relationship_type": "spouse",
                        "relationship_to": "Albertina Hermínia da Corte",
                        "source": "https://test-link.com",
                        "end_date": null,
                        "comments": null
                    }
                ]
            }
        ]
    },
    "version": "0.1",
    "timestamp": 1588599744111
}
```
{% endswagger-response %}
{% endswagger %}

### Legenda

* **id**: id da pessoa identificável.
* **name**: nome da pessoa identificável.
* **birth\_date**: data de nascimento da pessoa identificável.
* **score**: [grau de semelhança](../glossario/glossario-aplicacao.md#grau-de-semelhanca).
* **classifications**: classificações da pessoa identificável.
* **occupations**: lista de ocupações da pessoa identificável:
  * **organization**: organização da ocupação.
  * **organ**: orgão da ocupação.
  * **position**: posição na ocupação.
  * **source**: link da fonte que relaciona a pessoa identificável à ocupação.
  * **start\_date:** data de início da ocupação.
  * **end\_date:** data de fim da ocupação.
  * **comments:** notas relevantes sobre a ocupação.
* **relationships**: lista de relações da pessoa identificável
  * **relationship\_type**: tipo de relação.
  * **relationship\_to:** nome do familiar da pessoa identificável.
  * **source:** link da fonte com informação sobre a relação.
  * **end\_date:** data de fim da relação.
  * **comments:** notas relevantes sobre a relação.

{% swagger baseUrl="https://www.pepdata.com/api" path="/determine_validation" method="post" summary="Determinação de validação" %}
{% swagger-description %}
Endpoint para submeter uma validação.
{% endswagger-description %}

{% swagger-parameter in="header" name="Authentication" type="string" %}
key [API_KEY]
{% endswagger-parameter %}

{% swagger-parameter in="body" name="id" type="string" %}
Id da validação
{% endswagger-parameter %}

{% swagger-parameter in="body" name="id_iperson" type="string" %}
Id da pessoa identificável correspondente. 
{% endswagger-parameter %}

{% swagger-response status="200" description="A validação foi submetida com sucesso." %}
```
{
    "data": {},
    "version": "0.1",
    "timestamp": 1588599744111
}
```
{% endswagger-response %}
{% endswagger %}

{% swagger baseUrl="https://www.pepdata.com/api" path="/cancel_validation" method="post" summary="Cancelar determinação de validação" %}
{% swagger-description %}
Endpoint para cancelar a determinação de uma validação.
{% endswagger-description %}

{% swagger-parameter in="header" name="Authentication" type="string" %}
key [API_KEY]
{% endswagger-parameter %}

{% swagger-parameter in="body" name="id" type="string" %}
Id da validação
{% endswagger-parameter %}

{% swagger-response status="200" description="A determinação da validação foi cancelada com sucesso." %}
```
{
    "data": {},
    "version": "0.1",
    "timestamp": 1588599744111
}
```
{% endswagger-response %}
{% endswagger %}

{% swagger baseUrl="https://www.pepdata.com/api" path="/delete_validation" method="post" summary="Apagar validação" %}
{% swagger-description %}
Endpoint para apagar uma validação.
{% endswagger-description %}

{% swagger-parameter in="header" name="Authentication" type="string" %}
key [API_KEY]
{% endswagger-parameter %}

{% swagger-parameter in="body" name="id" type="string" %}
Id da validação
{% endswagger-parameter %}

{% swagger-response status="200" description="A validação foi apagada com sucesso." %}
```
{
    "data": {},
    "version": "0.1",
    "timestamp": 1588599744111
}
```
{% endswagger-response %}
{% endswagger %}

{% swagger baseUrl="https://www.pepdata.com/api" path="/apply_rules" method="post" summary="Aplicação das regras" %}
{% swagger-description %}
Endpoint para aplicação das regras de validação.
{% endswagger-description %}

{% swagger-parameter in="header" name="Authentication" type="string" %}
key [API_KEY]
{% endswagger-parameter %}

{% swagger-response status="200" description="As regras começaram a ser aplicadas. " %}
```
{
    "data": {
        "time_to_conclusion": X
    },
    "version": "0.1",
    "timestamp": 1588599744111
}
```
{% endswagger-response %}

{% swagger-response status="200: OK" description="Não existem validações elegíveis para aplicar as regras." %}
```javascript
{
    "message": {
        "version": 0.1,
        "timestamp": 1654613096539,
        "message": "Não existem validações elegíveis para aplicar as regras."
    }
}
```
{% endswagger-response %}

{% swagger-response status="400: Bad Request" description="As regras já se encontram a ser aplicadas." %}
```javascript
{
    "message": {
        "version": 0.1,
        "timestamp": 1588599744111,
        "message": "Esta operação já está em progresso. Por favor aguarde até estar completa."
    }
}
```
{% endswagger-response %}
{% endswagger %}

### Legenda

* **time\_to\_conclusion**: tempo **previsto** para a conclusão da aplicação das regras, em segundos.

{% hint style="warning" %}
A leitura da documentação relativa à [aplicação das regras de validação](../a-aplicacao/validacoes/aplicacao-de-regras.md) é fortemente recomendada, uma vez que a aplicação sem a sua correta compreensão poderá provocar alterações indesejadas.
{% endhint %}

{% hint style="info" %}
A [aplicação de regras](../a-aplicacao/validacoes/aplicacao-de-regras.md) pode demorar alguns minutos até se encontrar concluída, dependendo do número de validações incompletas existentes. O tempo de conclusão estimado é devolvido na resposta.
{% endhint %}
