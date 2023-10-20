# Validações

{% swagger baseUrl="https://www.pepdata.com/api" path="/get_validations" method="post" summary="Obter validações" %}
{% swagger-description %}
Endpoint para obter validações.
{% endswagger-description %}

{% swagger-parameter in="header" name="Authentication" type="string" required="true" %}
key \[API\_KEY]
{% endswagger-parameter %}

{% swagger-parameter in="body" name="page" type="number" required="false" %}
Página das validações

\\

Default: 1
{% endswagger-parameter %}

{% swagger-parameter in="body" name="source" type="string" required="false" %}
Origem das validações

\\

Default: all

\\

Valores possíveis: all, upload, manual
{% endswagger-parameter %}

{% swagger-parameter in="body" name="status" type="string" required="false" %}
Estado das validações

\\

Default: all

\\

Valores possíveis: all, complete, complete\_identified, complete\_not\_identified, complete\_needs\_attention, incomplete
{% endswagger-parameter %}

{% swagger-parameter in="body" name="id" type="string" required="false" %}
Id da validação
{% endswagger-parameter %}

{% swagger-parameter in="body" name="id_custom" type="string" required="false" %}
Id personalizável da validação
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Validações obtidas com sucesso." %}
<pre><code>{
    "version": 0.1,
    "timestamp": 1688640113263,
    "data": {
        "count": 2,
        "total": 2,
        "page": 1,
        "max_results_per_page": 50,
        "items": [
            {
                "id": "0984f9f1-1895-dc5b-6530-9075825225aa",
                "vatin": "628579388",
                "source": "Automatic",
                "name": "António Jorge Melo Lourenço Neco Rodrigues Fernandes",
                "birth_date": "1931-07-19",
                "id_country_nationality": "PT",
                "id_country_address": null,
                "decision": null,
                "id_iperson": 9bbf3184-8ced-4095-9cad-7e4dc664c9ee,
                "iperson_classifications": [
                    "PEP",
                    "Familiar",
                    "Associado
                ],
                "relations": [
                    {
                        "name": "António Silva",
                        "vatin": null,
                        "id_iperson": "5e809bc7-927e-3dc3-0ff8-ab9022843a5a",
                        "id_iorganization": null,
                        "relationship_type": "representative",
                        "id_relationship_info": "d0a4effc-576e-a4a2-f32e-9e594d7144ba"
                    }
                ],
                "added_by": "cd9f4a64-ab25-4efb-bf31-323ee2280095",
                "added_at": 1688639245750,
                "determined_at": null,
                "determined_by": null,
                "identifiable_country": null,
                "id_organization": "6cc1b6c1-33a9-4095-a4a4-aaca0db8d647",
                "id_custom": null,
                "entity_type": "individual",
                "id_iorganization": null,
                "adverse_media_searched_at": null,
                "judicial_processes_searched_at": null,
                "alerts": [],
<strong>                "country_nationality": "Portugal"
</strong>            },
            {
                "id": "a58dd84e-7e89-9904-5acf-2b1fbfcc8a31",
                "vatin": "595596160",
                "source": "Automatic",
                "name": "Maria Edite Nieto",
                "birth_date": null,
                "id_country_nationality": "PT",
                "id_country_address": null,
                "decision": null,
                "id_iperson": null,
                "iperson_classifications": null,
                "relations": null,
                "added_by": "cd9f4a64-ab25-4efb-bf31-323ee2280095",
                "added_at": 1688639245750,
                "determined_at": null,
                "determined_by": null,
                "identifiable_country": null,
                "id_organization": "6cc1b6c1-33a9-4095-a4a4-aaca0db8d647",
                "id_custom": null,
                "entity_type": "individual",
                "id_iorganization": null,
                "adverse_media_searched_at": null,
                "judicial_processes_searched_at": null,
                "alerts": [
                    {
                        "id": "1d71c856-8dde-4815-9dce-1683e176a6f1",
                        "added_at": 1689244974065,
                        "resolved_by": null,
                        "resolved_at": null,
                        "reasons": [
                            "Há um novo resultado que pode corresponder a esta validação: Maria Edite Neto"
                        ]
                    }
                ],
                "country_nationality": "Portugal"
            },
        ]
    }
}
</code></pre>
{% endswagger-response %}
{% endswagger %}

### Legenda

* **id**: id da validação.
* **vatin**: NIF da validação.
* **source**: origem da validação.
* **name**: nome da validação.
* **birth\_date**: data de nascimento da validação.
* **id\_country\_nationality**: código do país da nacionalidade, no formato [ISO 3166-1 alpha-2](https://en.wikipedia.org/wiki/ISO\_3166-1\_alpha-2).
* **id\_country\_address**: código do país de residência, no formato [ISO 3166-1 alpha-2](https://en.wikipedia.org/wiki/ISO\_3166-1\_alpha-2).
* **decision**: booleano que descreve se existiu correspondência com uma pessoa identificável.
* **id\_iperson**: id da pessoa identificável correspondente. null caso não tenha existido correspondência.
* **iperson\_classifications:** lista de classificações da pessoa identificável, possíveis valores:
  * Associado
  * Familiar
  * Titular de Outros Cargos
  * PEP
  * Sancionado (EU)
  * Sancionado (HM Treasury)
  * Sancionado (OFAC)
  * Sancionado (UN)
* **relations**: lista de relações associadas à validação. Contém as seguintes propriedades:
  * **name:** nome da relação.
  * **vatin:** NIF da relação.
  * **id\_iperson:** id da pessoa identificável associada à relação.
  * **id\_iorganization:** id da organização identificável associada à relação.
  * **relationship\_type:** tipo da relação. Valores possíveis:
    * representative
    * manager
    * beneficiary
    * beneficial\_owner
  * **id\_relationship\_info:** id da relação.
* **added\_by**: id do utilizador que [adicionou ](../a-aplicacao/validacoes/#adicao-determinacao-e-estados-de-validacoes)a validação.
* **added\_at**: data a que a validação foi adicionada, sob a forma de número de milissegundos desde 1 de Janeiro de 1970 00:00:00 UTC.
* **determined\_at**: data a que a validação foi determinada, sob a forma de número de milissegundos desde 1 de Janeiro de 1970 00:00:00 UTC.
* **determined\_by**: id do utilizador que [determinou ](../a-aplicacao/validacoes/#adicao-determinacao-e-estados-de-validacoes)a validação.
* **identifiable\_country:** booleano que descreve se o país da validação se encontra [sancionado](../glossario/glossario-aplicacao.md#pais-sancionado).
* **id\_organization:** id da organização que criou a validação.
* **id\_custom**: id personalizável inserido pelo utilizador.
* **entity\_type:** tipo da validação, podendo ser: "individual" ou "organization".
* **id\_iorganization:** id da organização identificável correspondente. null caso não tenha existido correspondência.
* **adverse\_media\_searched\_at:** data da última procura de notícias adversas associadas ao nome da validação.
* **judicial\_processes\_searched\_at:** data da última procura de processos judiciais associados ao nome da validação.
* **alerts:** alertas relacionados com a validação e que ainda estejam por resolver.
* **country\_nationality:** país de nacionalidade.

{% swagger method="post" path="_alerts" baseUrl="https://www.pepdata.com/api/get" summary="Obter alertas das validações" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="body" name="id_validation" type="string" required="false" %}
Id da validação
{% endswagger-parameter %}

{% swagger-parameter in="header" name="Authentication" type="string" required="true" %}
key \[API\_KEY]
{% endswagger-parameter %}

{% swagger-parameter in="body" name="ids_validations" type="string array" required="false" %}
Array de ids de validações
{% endswagger-parameter %}

{% swagger-parameter in="body" name="status" type="string" required="false" %}
Estado dos alertas

Default: unresolved\
Valores possíveis: all, resolved, unresolved
{% endswagger-parameter %}

{% swagger-parameter in="body" name="from" type="int" required="false" %}
Data de início do filtro, sob a forma de número de milissegundos desde 1 de Janeiro de 1970 00:00:00 UTC
{% endswagger-parameter %}

{% swagger-parameter in="body" name="until" type="int" required="false" %}
Data de fim do filtro, sob a forma de número de milissegundos desde 1 de Janeiro de 1970 00:00:00 UTC
{% endswagger-parameter %}

{% swagger-parameter in="body" name="page" type="number" %}
Página dos alertas.

Default: 1
{% endswagger-parameter %}

{% swagger-parameter in="body" name="include_comments" type="boolean" %}
Parâmetro para solicitar informação sobre os comentários associados aos alertas.

Valores possíveis: true, false

Default: false
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Alertas das validações obtidos com sucesso" %}
<pre><code><strong>{
</strong>    "data": {
        "items": [
            {
                "id": "53fef9d4-e3d4-ed03-5e79-38ba066050f7",
                "id_validation": "3462600c-8b9a-6384-c321-4587104ce0f1",
                "name": "José Codinha Manso",
                "birth_date": null,
                "id_country_nationality": "JP",
                "added_at": 1687873995707,
                "resolved_at": null,
                "resolved_by": null,
                "status": "unresolved",
                "reason": "Podem ter sido encontradas novas adverse media relativas a esta pessoa.",
                "country_nationality": "Japan",
                "comments": [
                    {
                        "id": "ff959c5f-8dbb-130c-f904-b0b02359d113",
                        "comment": "Comentário 1"
                    },
                    {
                        "id": "2b0c4c70-6730-9056-b3c2-bb8dc21125d3",
                        "comment": "Comentário 2"
                    }
                ]
            }
        ],
        "count": 1,
<strong>        "total": 1,
</strong>        "page": 1,
        "max_results_per_page": 50
    }
    "version": "0.1",
    "timestamp": 1588599744111
}
</code></pre>
{% endswagger-response %}

{% swagger-response status="400: Bad Request" description="Status de alerta inválido" %}
```
{
    "message": {
        "version": 0.1,
        "timestamp": 1588599744111,
        "message": "O campo 'estado' não é válido."
    }
}
```
{% endswagger-response %}
{% endswagger %}

### Legenda

* **id**: id do alerta.
* **id\_validation:** id da validação.
* **name**: nome da pessoa identificável.
* **birth\_date**: data de nascimento da pessoa identificável.
* **id\_country\_nationality**: código do país da nacionalidade, no formato [ISO 3166-1 alpha-2](https://en.wikipedia.org/wiki/ISO\_3166-1\_alpha-2).
* **added\_at**: data a que o alerta foi criado, sob a forma de número de milissegundos desde 1 de Janeiro de 1970 00:00:00 UTC.
* **resolved\_at:** data a que o alerta foi resolvido, sob a forma de número de milissegundos desde 1 de Janeiro de 1970 00:00:00 UTC.
* **resolved\_by:** utilizador que resolveu o alerta.
* **status:** estado do alerta.
* **reason**: razão da criação do alerta.
* **country\_nationality:** país de nacionalidade.
* **comments:** comentários associados ao alerta.
  * **id:** id do comentário.
  * **comment:** comentário.

{% swagger baseUrl="https://www.pepdata.com/api" path="/add_validation" method="post" summary="Adicionar validação" %}
{% swagger-description %}
Endpoint para adicionar uma validação.
{% endswagger-description %}

{% swagger-parameter in="header" name="Authentication" type="string" required="false" %}
key \[API\_KEY]
{% endswagger-parameter %}

{% swagger-parameter in="body" name="name" type="string" required="true" %}
Nome da validação
{% endswagger-parameter %}

{% swagger-parameter in="body" name="birth_date" type="string" required="false" %}
Data de nascimento da validação.

**Parâmetro usado apenas em validações de pessoas.**\
Formato: yyyy-mm-dd\
Default: null
{% endswagger-parameter %}

{% swagger-parameter in="body" name="ignore_duplicates" type="boolean" required="false" %}
Instrução para ignorar a verificação de duplicados.

\\

Formato: 0/1

\\

Default: 0
{% endswagger-parameter %}

{% swagger-parameter in="body" name="country_nationality" type="string" required="false" %}
País de nacionalidade da validação.

**Parâmetro usado apenas em validações de pessoas.**\
Formato: Nome do país (ver nota abaixo)\
Default: null
{% endswagger-parameter %}

{% swagger-parameter in="body" name="country_address" type="string" required="false" %}
País de residência da validação.

**Parâmetro usado apenas em validações de pessoas.**

Formato: Nome do país (ver nota abaixo)\
Default: null
{% endswagger-parameter %}

{% swagger-parameter in="body" name="country" required="false" %}
País da validação.

**Parâmetro usado apenas em validações de organizações.**

Formato: Nome do país (ver nota abaixo)

Default: null
{% endswagger-parameter %}

{% swagger-parameter in="body" name="vatin" type="string" required="false" %}
NIF da validação

\\

Default: null
{% endswagger-parameter %}

{% swagger-parameter in="body" name="id_custom" type="string" required="false" %}
Id personalizável da validação

\\

Default: null
{% endswagger-parameter %}

{% swagger-parameter in="body" name="type" type="string" required="false" %}
Tipo de entidade, podendo ser: "individual" ou "organization"

\\

Default: "individual"
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Validação adicionada com sucesso." %}
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

{% swagger-response status="409: Conflict" description="A validação a adicionar já se encontra na base de dados." %}
```
{
    "message": "Esta validação parece já existir na base de dados"
    "version": 0.1,
    "timestamp": 1696943296957
}
```
{% endswagger-response %}

{% swagger-response status="400: Bad Request" description="Nome inválido" %}


```json
{
    "message": {
        "version": 0.1,
        "timestamp": 1697017001540,
        "message": "O nome é inválido. Só são permitidos nomes:  • Com apenas caracteres latinos, apóstrofes, espaços, pontos ou hífenes;"
    }
}
```
{% endswagger-response %}
{% endswagger %}

### Legenda

* **id**: id da validação criada.

{% hint style="info" %}
**country\_nationality, country\_address e country**

Existem múltiplas formas distintas de se escrever o nome de cada país. A aplicação da PEPData consegue identificar todas as designações dos países presentes na [Lista dos Estados, territórios e moedas da União Europeia](https://publications.europa.eu/code/pt/pt-5000500.htm). No entanto, de forma a garantir maior robustez, recomendamos a utilização do formato [ISO 3166-1 alpha-2](https://en.wikipedia.org/wiki/ISO\_3166-1\_alpha-2), sempre que possível.
{% endhint %}

{% swagger baseUrl="https://www.pepdata.com/api" path="/analyze_validation" method="post" summary="Analisar validação" %}
{% swagger-description %}
Endpoint para consultar os resultados obtidos da análise de uma validação.
{% endswagger-description %}

{% swagger-parameter in="header" name="Authentication" type="string" required="false" %}
key \[API\_KEY]
{% endswagger-parameter %}

{% swagger-parameter in="body" name="id" type="string" required="false" %}
Id da validação
{% endswagger-parameter %}

{% swagger-parameter in="body" name="include_iperson_details" type="boolean" required="false" %}
Incluir informação acerca das classificações, ocupações e relações das pessoas identificáveis.\
Formato: true/false

Default: false
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Resultados da análise de validação obtidos com sucesso." %}
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
        ],
        "count": 2
    },
    "version": "0.1",
    "timestamp": 1588599744111
}
```
{% endswagger-response %}

{% swagger-response status="400: Bad Request" description="Validação não encontrada" %}


```json
{
    "message": {
        "version": 0.1,
        "timestamp": 1697017451164,
        "message": "A validação não foi encontrada"
    }
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
Endpoint para determinar uma validação.
{% endswagger-description %}

{% swagger-parameter in="header" name="Authentication" type="string" required="false" %}
key \[API\_KEY]
{% endswagger-parameter %}

{% swagger-parameter in="body" name="id" type="string" required="false" %}
Id da validação
{% endswagger-parameter %}

{% swagger-parameter in="body" name="id_entity" type="string" required="false" %}
Id da pessoa ou organização identificável correspondente.
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="A validação foi determinada com sucesso." %}
```
{
    "version": 0.1,
    "timestamp": 1695805850051,
    "data": {
        "message": "A validação foi determinada com sucesso."
    }
}
```
{% endswagger-response %}

{% swagger-response status="400: Bad Request" description="Validação não encontrada" %}
```
{
    "message": {
        "version": 0.1,
        "timestamp": 1697017451164,
        "message": "A validação não foi encontrada"
    }
}
```
{% endswagger-response %}
{% endswagger %}

{% swagger baseUrl="https://www.pepdata.com/api" path="/delete_validation" method="post" summary="Apagar validação" %}
{% swagger-description %}
Endpoint para apagar uma validação.
{% endswagger-description %}

{% swagger-parameter in="header" name="Authentication" type="string" required="false" %}
key \[API\_KEY]
{% endswagger-parameter %}

{% swagger-parameter in="body" name="id" type="string" required="false" %}
Id da validação
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="A validação foi apagada com sucesso." %}
```
{
    "version": 0.1,
    "timestamp": 1695806667520,
    "data": {
        "message": "A validação foi apagada com sucesso."
    }
}
```
{% endswagger-response %}

{% swagger-response status="400: Bad Request" description="Validação não encontrada" %}


```json
{
    "message": {
        "version": 0.1,
        "timestamp": 1697017451164,
        "message": "A validação não foi encontrada"
    }
}
```
{% endswagger-response %}
{% endswagger %}

{% swagger baseUrl="https://www.pepdata.com/api" path="/apply_rules" method="post" summary="Aplicação das regras" %}
{% swagger-description %}
Endpoint para aplicação das regras de validação.
{% endswagger-description %}

{% swagger-parameter in="header" name="Authentication" type="string" required="false" %}
key \[API\_KEY]
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="As regras começaram a ser aplicadas." %}
```
{
    "version": 0.1,
    "timestamp": 1695983552463,
    "data": {
        "time_to_conclusion": 1
    }
}
```
{% endswagger-response %}

{% swagger-response status="200: OK" description="Não existem validações elegíveis para aplicar as regras." %}
```javascript
{
    "version": 0.1,
    "timestamp": 1695983327878,
    "data": {
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
        "timestamp": 1695984451235,
        "message": "Esta operação já está em progresso. Por favor aguarde até estar completa."
    }
}
```
{% endswagger-response %}
{% endswagger %}

### Legenda

* **time\_to\_conclusion**: tempo estimado em segundos para a conclusão da operação.

{% hint style="warning" %}
A leitura da documentação relativa à [aplicação das regras de validação](../a-aplicacao/validacoes/aplicacao-de-regras.md) é fortemente recomendada, uma vez que a aplicação sem a sua correta compreensão poderá provocar alterações indesejadas.
{% endhint %}

{% hint style="info" %}
A [aplicação de regras](../a-aplicacao/validacoes/aplicacao-de-regras.md) pode demorar alguns minutos até se encontrar concluída, dependendo do número de validações incompletas existentes.
{% endhint %}

{% swagger baseUrl="https://www.pepdata.com/api" path="/get_comments" method="post" summary="Obter comentários" %}
{% swagger-description %}
Endpoint para obter comentários.
{% endswagger-description %}

{% swagger-parameter in="header" name="Authentication" type="string" required="true" %}
key \[API\_KEY]
{% endswagger-parameter %}

{% swagger-parameter in="body" name="page" type="number" required="false" %}
Página dos comentários.

Default: 1
{% endswagger-parameter %}

{% swagger-parameter in="body" name="id_validation" type="string" %}
Id da validação associada aos comentários.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="type" type="string" required="false" %}
Tipo de alertas. Valores possíveis: determination, alert, judicial\_process, adverse\_media
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Comentários obtidos com sucesso." %}
```
{
    "version": 0.1,
    "timestamp": 1697728294225,
    "data": {
        "count": 2,
        "total": 2,
        "items": [
            {
                "id": "ff959c5f-8dbb-130c-f904-b0b02359d113",
                "comment": "Comentário 1",
                "added_at": 1697704218743,
                "added_by": "António Jesus",
                "id_validation": "a086cf5f-99ad-12d6-7a80-3d9a47a638d0",
                "id_iperson": null,
                "id_validation_alert": "e9b629b3-0566-c119-1de3-a86d8436205d",
                "id_validation_judicial_process": null,
                "id_validation_adverse_media": null,
                "id_added_by": "cd9f4a64-ab25-4efb-bf31-323ee2280095"
            },
            {
                "id": "12cdbdba-685d-73d5-fc35-017ecb17c166",
                "comment": "Comentário 2",
                "added_at": 1697704304926,
                "added_by": "António Jesus",
                "id_validation": "6f95d22f-9751-3d02-0784-0c6288c79c66",
                "id_iperson": "91a1d1c0-bfd0-6e4b-3574-08c40bc9e577",
                "id_validation_alert": null,
                "id_validation_judicial_process": null,
                "id_validation_adverse_media": null,
                "id_added_by": "cd9f4a64-ab25-4efb-bf31-323ee2280095"
            }
        ],
        "page": 1,
        "max_results_per_page": 50
    }
}
```
{% endswagger-response %}

{% swagger-response status="400: Bad Request" description="Tipo de alerta inválido" %}


```json
{
    "message": {
        "version": 0.1,
        "timestamp": 1697728633346,
        "message": "O tipo de comentário não é válido."
    }
}
```
{% endswagger-response %}
{% endswagger %}

### Legenda

* **id**: id do comentário.
* **comment**: comentário.
* **added\_at**: data em que o comentário foi adicionado, sob a forma de número de milissegundos desde 1 de Janeiro de 1970 00:00:00 UTC.
* **added\_by**: utilizador que adicionou o comentário.
* **id\_validation**: id da validação associada ao comentário.
* **id\_iperson**: id da pessoa identificável correspondente, caso o tipo do comentário seja "determination".
* **id\_validation\_alert**: id do alerta de validação correspondente, caso o tipo do comentário seja "alert".
* **id\_validation\_judicial\_process:** id do processo judicial associado correspondente, caso o tipo de comentário seja "judicial\_process".
* **id\_validation\_adverse\_media:** id da notícia adversa associada correspondente, caso o tipo de comentário seja "adverse\_media".
* **id\_added\_by:** id do utilizador que adicionou o comentário.

{% swagger baseUrl="https://www.pepdata.com/api" path="add_comment" method="post" summary="Adicionar um comentário" %}
{% swagger-description %}
Endpoint para adicionar um comentário.
{% endswagger-description %}

{% swagger-parameter in="header" name="Authentication" type="string" required="true" %}
key \[API\_KEY]
{% endswagger-parameter %}

{% swagger-parameter in="body" name="id_validation" type="string" required="true" %}
Id da validação
{% endswagger-parameter %}

{% swagger-parameter in="body" name="comment" required="true" type="string" %}
Comentário
{% endswagger-parameter %}

{% swagger-parameter in="body" name="id_iperson" type="string" required="false" %}
Id da pessoa identificável correspondente. **Este parâmetro é obrigatório caso o comentário a adicionar seja referente à identificação de uma validação.**
{% endswagger-parameter %}

{% swagger-parameter in="body" name="id_validation_alert" type="string" %}
Id do alerta de validação correspondente. **Este parâmetro é obrigatório caso o comentário a adicionar seja referente a um alerta de validação.**
{% endswagger-parameter %}

{% swagger-parameter in="body" name="id_validation_judicial_process" type="string" %}
Id do processo judicial associado correspondente. **Este parâmetro é obrigatório caso o comentário a adicionar seja referente a um processo judicial.**
{% endswagger-parameter %}

{% swagger-parameter in="body" name="id_validation_adverse_media" type="string" %}
Id da notícia adversa associada correspondente. **Este parâmetro é obrigatório caso o comentário a adicionar seja referente a uma notícia adversa.**
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Comentário adicionado com sucesso." %}
```
{
    "version": 0.1,
    "timestamp": 1697730099564,
    "data": {
        "id": "ac33a772-a869-1c36-8569-5cba9cd0542d"
    }
}
```
{% endswagger-response %}

{% swagger-response status="400: Bad Request" description="Validação não encontrada" %}


```json
{
    "message": {
        "version": 0.1,
        "timestamp": 1697730211531,
        "message": "A validação não foi encontrada"
    }
}
```
{% endswagger-response %}
{% endswagger %}

### Legenda

* **id**: id do comentário adicionado.

{% swagger baseUrl="https://www.pepdata.com/api" path="edit_comment" method="post" summary="Editar um comentário" %}
{% swagger-description %}
Endpoint para editar um comentário.
{% endswagger-description %}

{% swagger-parameter in="header" name="Authentication" type="string" required="true" %}
key \[API\_KEY]
{% endswagger-parameter %}

{% swagger-parameter in="body" name="id" type="string" required="true" %}
Id do comentário a editar
{% endswagger-parameter %}

{% swagger-parameter in="body" name="comment" required="true" type="string" %}
Comentário
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Comentário editado com sucesso." %}
```
{
    "version": 0.1,
    "timestamp": 1697730574961,
    "data": {
        "message": "Comentário editado com sucesso."
    }
}
```
{% endswagger-response %}

{% swagger-response status="400: Bad Request" description="Id de comentário inválido." %}


```json
{
    "message": {
        "version": 0.1,
        "timestamp": 1697730622187,
        "message": "O comentário não foi encontrado."
    }
}
```
{% endswagger-response %}
{% endswagger %}

{% swagger baseUrl="https://www.pepdata.com/api" path="delete_comment" method="post" summary="Apagar um comentário" %}
{% swagger-description %}
Endpoint para apagar um comentário.
{% endswagger-description %}

{% swagger-parameter in="header" name="Authentication" type="string" required="true" %}
key \[API\_KEY]
{% endswagger-parameter %}

{% swagger-parameter in="body" name="id" type="string" required="true" %}
Id do comentário a apagar
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Comentário apagado com sucesso." %}
```
{
    "version": 0.1,
    "timestamp": 1697730574961,
    "data": {
        "message": "Comentário apagado com sucesso."
    }
}
```
{% endswagger-response %}

{% swagger-response status="400: Bad Request" description="Id de comentário inválido." %}


```json
{
    "message": {
        "version": 0.1,
        "timestamp": 1697730622187,
        "message": "O comentário não foi encontrado."
    }
}
```
{% endswagger-response %}
{% endswagger %}
