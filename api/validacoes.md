# Validações

## Obter validações

<mark style="color:green;">`POST`</mark> `https://www.pepdata.com/api/get_validations`

Endpoint para obter validações.

#### Headers

| Name                                             | Type   | Description     |
| ------------------------------------------------ | ------ | --------------- |
| Authentication<mark style="color:red;">\*</mark> | string | key \[API\_KEY] |

#### Request Body

| Name       | Type   | Description                                                                                                                                                                                                                                           |
| ---------- | ------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| page       | number | <p>Página das validações</p><p></p><p>Default: 1</p>                                                                                                                                                                                                  |
| source     | string | <p>Origem das validações</p><p></p><p>Default: all</p><p></p><p>Valores possíveis: </p><ul><li>all</li><li>upload</li><li>manual</li></ul>                                                                                                            |
| status     | string | <p></p><p>Estado das validações</p><p></p><p>Default: all</p><p></p><p>Valores possíveis: </p><ul><li>all</li><li>complete</li><li>complete_identified,</li><li>complete_not_identified</li><li>complete_needs_attention</li><li>incomplete</li></ul> |
| id         | string | Id da validação                                                                                                                                                                                                                                       |
| id\_custom | string | Id personalizável da validação                                                                                                                                                                                                                        |
| sort\_by   | string | <p>Propriedade usada para a ordenação das validações<br><br>Valores possíveis: </p><ul><li>added_at</li><li>determined_at</li><li>name</li></ul>                                                                                                      |
| sort\_dir  | string | <p>Ordenação descendente ou ascendente das validações<br><br>Valores possíveis: </p><ul><li>desc</li><li>asc</li></ul>                                                                                                                                |

{% tabs %}
{% tab title="200: OK Validações obtidas com sucesso." %}
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
{% endtab %}
{% endtabs %}

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

## Exportar validações

<mark style="color:green;">`POST`</mark> `https://www.pepdata.com/api/export_validations`

**Headers**

| Name                                             | Type   | Description     |
| ------------------------------------------------ | ------ | --------------- |
| Authentication<mark style="color:red;">\*</mark> | string | key \[API\_KEY] |

**Request Body**

| Name                                    | Type   | Description                                                                                                                                                                                                                                    |
| --------------------------------------- | ------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| from<mark style="color:red;">\*</mark>  | int    | Data de início do filtro, sob a forma de número de milissegundos desde 1 de Janeiro de 1970 00:00:00 UTC                                                                                                                                       |
| until<mark style="color:red;">\*</mark> | int    | Data de fim do filtro, sob a forma de número de milissegundos desde 1 de Janeiro de 1970 00:00:00 UTC                                                                                                                                          |
| status                                  | string | <p>Estado das validações</p><p></p><p>Default: all</p><p></p><p>Valores possíveis: </p><ul><li>all</li><li>complete</li><li>complete_identified,</li><li>complete_not_identified</li><li>complete_needs_attention</li><li>incomplete</li></ul> |
| format                                  | string | <p>Formato do ficheiro exportado<br><br>Default: xlsx<br><br>Valores possíveis:</p><ul><li>xlsx</li><li>csv</li></ul>                                                                                                                          |
| export\_by                              | string | <p>Exportar validações por data de adição ou data de determinação.<br><br>Default: added_at<br><br>Valores possíveis:</p><ul><li>added_at</li><li>determined_at</li></ul>                                                                      |
| timezone                                | string | <p>Fuso horário dos timestamps utilizados nos filtros<br><br>Default: Europe/Lisbon<br></p>                                                                                                                                                    |

**Response**

{% tabs %}
{% tab title="200: OK ficheiro exportado com sucesso" %}
{% file src="../.gitbook/assets/validações de 01-07-2024 a 29-07-2024.xlsx" %}
Exemplo de ficheiro de exportação de validações
{% endfile %}
{% endtab %}

{% tab title="400: Bad Request Campos obrigatórios vazios" %}
<pre class="language-json"><code class="lang-json">{
<strong>   "message": {
</strong>        "version": 0.1,
        "timestamp": 1722266342583,
        "message": "O campo 'from' não pode ficar vazio."
    }
}
</code></pre>
{% endtab %}

{% tab title="400: Bad Request Opções inválidas" %}
<pre class="language-json"><code class="lang-json">{
<strong>   "message": {
</strong>        "version": 0.1,
        "timestamp": 1722266342583,
        "message": "A opção do campo 'status' não é válida."
    }
}
</code></pre>
{% endtab %}
{% endtabs %}

## Obter alertas das validações

<mark style="color:green;">`POST`</mark> `https://www.pepdata.com/api/get_alerts`

#### Headers

| Name                                             | Type   | Description     |
| ------------------------------------------------ | ------ | --------------- |
| Authentication<mark style="color:red;">\*</mark> | string | key \[API\_KEY] |

#### Request Body

| Name              | Type         | Description                                                                                                                                                                              |
| ----------------- | ------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| id\_validation    | string       | Id da validação                                                                                                                                                                          |
| ids\_validations  | string array | Array de ids de validações                                                                                                                                                               |
| status            | string       | <p>Estado dos alertas</p><p></p><p>Default: unresolved<br></p><p>Valores possíveis: </p><ul><li>all</li><li>resolved</li><li>unresolved</li></ul>                                        |
| from              | int          | Data de início do filtro, sob a forma de número de milissegundos desde 1 de Janeiro de 1970 00:00:00 UTC                                                                                 |
| until             | int          | Data de fim do filtro, sob a forma de número de milissegundos desde 1 de Janeiro de 1970 00:00:00 UTC                                                                                    |
| include\_comments | boolean      | <p>Parâmetro para solicitar informação sobre os comentários associados aos alertas.</p><p></p><p>Default: false</p><p></p><p>Valores possíveis: </p><ul><li>true</li><li>false</li></ul> |
| page              | number       | <p>Página dos alertas.</p><p>Default: 1</p>                                                                                                                                              |

{% tabs %}
{% tab title="200: OK Alertas das validações obtidos com sucesso" %}
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
{% endtab %}

{% tab title="400: Bad Request Status de alerta inválido" %}
```
{
    "message": {
        "version": 0.1,
        "timestamp": 1588599744111,
        "message": "O campo 'estado' não é válido."
    }
}
```
{% endtab %}
{% endtabs %}

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

## Adicionar validação

<mark style="color:green;">`POST`</mark> `https://www.pepdata.com/api/add_validation`

Endpoint para adicionar uma validação.

#### Headers

| Name           | Type   | Description     |
| -------------- | ------ | --------------- |
| Authentication | string | key \[API\_KEY] |

#### Request Body

| Name                                   | Type    | Description                                                                                                                                                                    |
| -------------------------------------- | ------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| name<mark style="color:red;">\*</mark> | string  | Nome da validação                                                                                                                                                              |
| birth\_date                            | string  | <p>Data de nascimento da validação.</p><p><strong>Parâmetro usado apenas em validações de pessoas.</strong><br>Formato: yyyy-mm-dd<br>Default: null</p>                        |
| ignore\_duplicates                     | boolean | <p>Instrução para ignorar a verificação de duplicados.</p><p></p><p>Formato: 0/1</p><p></p><p>Default: 0</p>                                                                   |
| country\_nationality                   | string  | <p>País de nacionalidade da validação.</p><p><strong>Parâmetro usado apenas em validações de pessoas.</strong><br>Formato: Nome do país (ver nota abaixo)<br>Default: null</p> |
| country\_residence                     | string  | <p>País de residência da validação.</p><p><strong>Parâmetro usado apenas em validações de pessoas.</strong></p><p>Formato: Nome do país (ver nota abaixo)<br>Default: null</p> |
| country                                | String  | <p>País da validação.</p><p><strong>Parâmetro usado apenas em validações de organizações.</strong></p><p>Formato: Nome do país (ver nota abaixo)</p><p>Default: null</p>       |
| vatin                                  | string  | <p>NIF da validação</p><p></p><p>Default: null</p>                                                                                                                             |
| id\_custom                             | string  | <p>Id personalizável da validação</p><p></p><p>Default: null</p>                                                                                                               |
| type                                   | string  | <p>Tipo de entidade, podendo ser: "individual" ou "organization"</p><p></p><p>Default: "individual"</p>                                                                        |

{% tabs %}
{% tab title="200: OK Validação adicionada com sucesso." %}
```

{
    "data": {
        "id": "926b7dab-a3af-986f-2137-872adb95260f"
    },
    "version": "0.1",
    "timestamp": 1588599744111
}
```
{% endtab %}

{% tab title="409: Conflict A validação a adicionar já se encontra na base de dados." %}
```
{
    "message": "Esta validação parece já existir na base de dados"
    "version": 0.1,
    "timestamp": 1696943296957
}
```
{% endtab %}

{% tab title="400: Bad Request Nome inválido" %}


```json
{
    "message": {
        "version": 0.1,
        "timestamp": 1697017001540,
        "message": "O nome é inválido. Só são permitidos nomes:  • Com apenas caracteres latinos, apóstrofes, espaços, pontos ou hífenes;"
    }
}
```
{% endtab %}
{% endtabs %}

### Legenda

* **id**: id da validação criada.

{% hint style="info" %}
**country\_nationality, country\_residence e country**

Existem múltiplas formas distintas de se escrever o nome de cada país. A aplicação da PEPData consegue identificar todas as designações dos países presentes na [Lista dos Estados, territórios e moedas da União Europeia](https://publications.europa.eu/code/pt/pt-5000500.htm). No entanto, de forma a garantir maior robustez, recomendamos a utilização do formato [ISO 3166-1 alpha-2](https://en.wikipedia.org/wiki/ISO\_3166-1\_alpha-2), sempre que possível.
{% endhint %}

## Analisar validação

<mark style="color:green;">`POST`</mark> `https://www.pepdata.com/api/analyze_validation`

Endpoint para consultar os resultados obtidos da análise de uma validação.

#### Headers

| Name           | Type   | Description     |
| -------------- | ------ | --------------- |
| Authentication | string | key \[API\_KEY] |

#### Request Body

| Name                      | Type    | Description                                                                                                                                       |
| ------------------------- | ------- | ------------------------------------------------------------------------------------------------------------------------------------------------- |
| id                        | string  | Id da validação                                                                                                                                   |
| include\_iperson\_details | boolean | <p>Incluir informação acerca das classificações, ocupações e relações das pessoas identificáveis.<br>Formato: true/false</p><p>Default: false</p> |

{% tabs %}
{% tab title="200: OK Resultados da análise de validação obtidos com sucesso." %}
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
{% endtab %}

{% tab title="400: Bad Request Validação não encontrada" %}


```json
{
    "message": {
        "version": 0.1,
        "timestamp": 1697017451164,
        "message": "A validação não foi encontrada"
    }
}
```
{% endtab %}
{% endtabs %}

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

## Determinação de validação

<mark style="color:green;">`POST`</mark> `https://www.pepdata.com/api/determine_validation`

Endpoint para determinar uma validação.

#### Headers

| Name           | Type   | Description     |
| -------------- | ------ | --------------- |
| Authentication | string | key \[API\_KEY] |

#### Request Body

| Name       | Type   | Description                                               |
| ---------- | ------ | --------------------------------------------------------- |
| id         | string | Id da validação                                           |
| id\_entity | string | Id da pessoa ou organização identificável correspondente. |

{% tabs %}
{% tab title="200: OK A validação foi determinada com sucesso." %}
```
{
    "version": 0.1,
    "timestamp": 1695805850051,
    "data": {
        "message": "A validação foi determinada com sucesso."
    }
}
```
{% endtab %}

{% tab title="400: Bad Request Validação não encontrada" %}
```
{
    "message": {
        "version": 0.1,
        "timestamp": 1697017451164,
        "message": "A validação não foi encontrada"
    }
}
```
{% endtab %}
{% endtabs %}

## Apagar validação

<mark style="color:green;">`POST`</mark> `https://www.pepdata.com/api/delete_validation`

Endpoint para apagar uma validação.

#### Headers

| Name           | Type   | Description     |
| -------------- | ------ | --------------- |
| Authentication | string | key \[API\_KEY] |

#### Request Body

| Name | Type   | Description     |
| ---- | ------ | --------------- |
| id   | string | Id da validação |

{% tabs %}
{% tab title="200: OK A validação foi apagada com sucesso." %}
```
{
    "version": 0.1,
    "timestamp": 1695806667520,
    "data": {
        "message": "A validação foi apagada com sucesso."
    }
}
```
{% endtab %}

{% tab title="400: Bad Request Validação não encontrada" %}


```json
{
    "message": {
        "version": 0.1,
        "timestamp": 1697017451164,
        "message": "A validação não foi encontrada"
    }
}
```
{% endtab %}
{% endtabs %}

## Aplicação das regras

<mark style="color:green;">`POST`</mark> `https://www.pepdata.com/api/apply_rules`

Endpoint para aplicação das regras de validação.

#### Headers

| Name           | Type   | Description     |
| -------------- | ------ | --------------- |
| Authentication | string | key \[API\_KEY] |

{% tabs %}
{% tab title="200: OK Não existem validações elegíveis para aplicar as regras." %}
```javascript
{
    "version": 0.1,
    "timestamp": 1695983327878,
    "data": {
        "message": "Não existem validações elegíveis para aplicar as regras."
    }
}
```
{% endtab %}

{% tab title="400: Bad Request As regras já se encontram a ser aplicadas." %}
```javascript
{
    "message": {
        "version": 0.1,
        "timestamp": 1695984451235,
        "message": "Esta operação já está em progresso. Por favor aguarde até estar completa."
    }
}
```
{% endtab %}

{% tab title="200: OK As regras começaram a ser aplicadas." %}
```
{
    "version": 0.1,
    "timestamp": 1695983552463,
    "data": {
        "time_to_conclusion": 1
    }
}
```
{% endtab %}
{% endtabs %}

### Legenda

* **time\_to\_conclusion**: tempo estimado em segundos para a conclusão da operação.

{% hint style="warning" %}
A leitura da documentação relativa à [aplicação das regras de validação](../a-aplicacao/validacoes/aplicacao-de-regras.md) é fortemente recomendada, uma vez que a aplicação sem a sua correta compreensão poderá provocar alterações indesejadas.
{% endhint %}

{% hint style="info" %}
A [aplicação de regras](../a-aplicacao/validacoes/aplicacao-de-regras.md) pode demorar alguns minutos até se encontrar concluída, dependendo do número de validações incompletas existentes.
{% endhint %}

## Obter comentários

<mark style="color:green;">`POST`</mark> `https://www.pepdata.com/api/get_comments`

Endpoint para obter comentários.

#### Headers

| Name                                             | Type   | Description     |
| ------------------------------------------------ | ------ | --------------- |
| Authentication<mark style="color:red;">\*</mark> | string | key \[API\_KEY] |

#### Request Body

| Name           | Type   | Description                                                                                                                                              |
| -------------- | ------ | -------------------------------------------------------------------------------------------------------------------------------------------------------- |
| page           | number | <p>Página dos comentários.</p><p>Default: 1</p>                                                                                                          |
| type           | string | <p>Tipo de comentários. </p><p></p><p>Valores possíveis:</p><ul><li>determination</li><li>alert</li><li>judicial_process</li><li>adverse_media</li></ul> |
| id\_validation | string | Id da validação associada aos comentários.                                                                                                               |

{% tabs %}
{% tab title="200: OK Comentários obtidos com sucesso." %}
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
{% endtab %}

{% tab title="400: Bad Request Tipo de comentários inválido" %}


```json
{
    "message": {
        "version": 0.1,
        "timestamp": 1697728633346,
        "message": "O tipo de comentário não é válido."
    }
}
```
{% endtab %}
{% endtabs %}

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

## Adicionar um comentário

<mark style="color:green;">`POST`</mark> `https://www.pepdata.com/api/add_comment`

Endpoint para adicionar um comentário.

#### Headers

| Name                                             | Type   | Description     |
| ------------------------------------------------ | ------ | --------------- |
| Authentication<mark style="color:red;">\*</mark> | string | key \[API\_KEY] |

#### Request Body

| Name                                             | Type   | Description                                                                                                                                                |
| ------------------------------------------------ | ------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------- |
| id\_validation<mark style="color:red;">\*</mark> | string | Id da validação                                                                                                                                            |
| id\_iperson                                      | string | Id da pessoa identificável correspondente. **Este parâmetro é obrigatório caso o comentário a adicionar seja referente à identificação de uma validação.** |
| comment<mark style="color:red;">\*</mark>        | string | Comentário                                                                                                                                                 |
| id\_validation\_alert                            | string | Id do alerta de validação correspondente. **Este parâmetro é obrigatório caso o comentário a adicionar seja referente a um alerta de validação.**          |
| id\_validation\_judicial\_process                | string | Id do processo judicial associado correspondente. **Este parâmetro é obrigatório caso o comentário a adicionar seja referente a um processo judicial.**    |
| id\_validation\_adverse\_media                   | string | Id da notícia adversa associada correspondente. **Este parâmetro é obrigatório caso o comentário a adicionar seja referente a uma notícia adversa.**       |

{% tabs %}
{% tab title="200: OK Comentário adicionado com sucesso." %}
```
{
    "version": 0.1,
    "timestamp": 1697730099564,
    "data": {
        "id": "ac33a772-a869-1c36-8569-5cba9cd0542d"
    }
}
```
{% endtab %}

{% tab title="400: Bad Request Validação não encontrada" %}


```json
{
    "message": {
        "version": 0.1,
        "timestamp": 1697730211531,
        "message": "A validação não foi encontrada"
    }
}
```
{% endtab %}
{% endtabs %}

### Legenda

* **id**: id do comentário adicionado.

## Editar um comentário

<mark style="color:green;">`POST`</mark> `https://www.pepdata.com/api/edit_comment`

Endpoint para editar um comentário.

#### Headers

| Name                                             | Type   | Description     |
| ------------------------------------------------ | ------ | --------------- |
| Authentication<mark style="color:red;">\*</mark> | string | key \[API\_KEY] |

#### Request Body

| Name                                      | Type   | Description               |
| ----------------------------------------- | ------ | ------------------------- |
| id<mark style="color:red;">\*</mark>      | string | Id do comentário a editar |
| comment<mark style="color:red;">\*</mark> | string | Comentário                |

{% tabs %}
{% tab title="200: OK Comentário editado com sucesso." %}
```
{
    "version": 0.1,
    "timestamp": 1697730574961,
    "data": {
        "message": "Comentário editado com sucesso."
    }
}
```
{% endtab %}

{% tab title="400: Bad Request Id de comentário inválido." %}


```json
{
    "message": {
        "version": 0.1,
        "timestamp": 1697730622187,
        "message": "O comentário não foi encontrado."
    }
}
```
{% endtab %}
{% endtabs %}

## Apagar um comentário

<mark style="color:green;">`POST`</mark> `https://www.pepdata.com/api/delete_comment`

Endpoint para apagar um comentário.

#### Headers

| Name                                             | Type   | Description     |
| ------------------------------------------------ | ------ | --------------- |
| Authentication<mark style="color:red;">\*</mark> | string | key \[API\_KEY] |

#### Request Body

| Name                                 | Type   | Description               |
| ------------------------------------ | ------ | ------------------------- |
| id<mark style="color:red;">\*</mark> | string | Id do comentário a apagar |

{% tabs %}
{% tab title="200: OK Comentário apagado com sucesso." %}
```
{
    "version": 0.1,
    "timestamp": 1697730574961,
    "data": {
        "message": "Comentário apagado com sucesso."
    }
}
```
{% endtab %}

{% tab title="400: Bad Request Id de comentário inválido." %}


```json
{
    "message": {
        "version": 0.1,
        "timestamp": 1697730622187,
        "message": "O comentário não foi encontrado."
    }
}
```
{% endtab %}
{% endtabs %}

## Obter relações de uma validação

<mark style="color:green;">`POST`</mark> `https://www.pepdata.com/api/get_validation_relationships`

Endpoint para obter relações de uma validação.

#### Headers

| Name                                             | Type   | Description     |
| ------------------------------------------------ | ------ | --------------- |
| Authentication<mark style="color:red;">\*</mark> | string | key \[API\_KEY] |

#### Request Body

| Name                                             | Type   | Description                                  |
| ------------------------------------------------ | ------ | -------------------------------------------- |
| id\_validation<mark style="color:red;">\*</mark> | string | Id da validação                              |
| page                                             | number | <p>Página das relações.</p><p>Default: 1</p> |

{% tabs %}
{% tab title="200: OK Relações obtidas com sucesso" %}
```
{
    "version": 0.1,
    "timestamp": 1697795044035,
    "data": {
        "items": [
            {
                "id": "7f0c97de-6c71-1461-4d9b-da65b4670824",
                "id_relationship": "a86a80bf-0d90-cdfe-1869-726b898cc426",
                "relationship_type": "representative",
                "relationship_to": "António João Soares",
                "id_relationship_to": "df3250ff-382f-c9aa-346e-ef76dd3d333f",
                "id_relationship_from": "6474d5fc-205a-f750-2dd6-24c5d87a5ee5",
                "added_by": "Carlos Araujo",
                "added_at": 1697795029624
            },
            {
                "id": "3b402dbb-ccef-c773-7fac-3225ce7f0e25",
                "id_relationship": "7c5d3c73-b61c-44ae-6d0a-234e1ea2145b",
                "relationship_type": "manager",
                "relationship_to": "José Manuel Silva",
                "id_relationship_to": "3b981423-e1eb-f30f-b4ff-d72b8f34c43a",
                "id_relationship_from": "6474d5fc-205a-f750-2dd6-24c5d87a5ee5",
                "added_by": "Carlos Araujo",
                "added_at": 1697795038487
            }
        ],
        "count": 2,
        "total": 2,
        "page": 1,
        "max_results_per_page": 50
    }
}
```
{% endtab %}

{% tab title="400: Bad Request Validação não encontrada." %}


```json
{
    "message": {
        "version": 0.1,
        "timestamp": 1697795069776,
        "message": "A validação não foi encontrada"
    }
}
```
{% endtab %}
{% endtabs %}

### Legenda

* **id**: identificador da tabela de informações de relações.
* **id\_relationship:** id da relação.
* **relationship\_type:** tipo da relação
* **relationship\_to:** nome da validação para a qual se criou a relação.
* **id\_relationship\_to:** id da validação para a qual se criou a relação.
* **id\_relationship\_from:** id da validação a partir da qual se criou a relação.
* **added\_by:** utilizador responsável pela criação da relação.
* **added\_at:** data em que a relação foi adicionada, sob a forma de número de milissegundos desde 1 de Janeiro de 1970 00:00:00 UTC.

## Adicionar uma relação a uma validação.

<mark style="color:green;">`POST`</mark> `https://www.pepdata.com/api/add_validation_relationship`

Endpoint para adicionar uma relação a uma validação.

#### Headers

| Name                                             | Type   | Description     |
| ------------------------------------------------ | ------ | --------------- |
| Authentication<mark style="color:red;">\*</mark> | string | key \[API\_KEY] |

#### Request Body

| Name                                                         | Type   | Description                                                                                                                                                                            |
| ------------------------------------------------------------ | ------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| organization\_vat\_number<mark style="color:red;">\*</mark>  | string | NIF da validação a partir da qual se vai criar a relação. **Tem de ser obrigatoriamente uma validação de organização.**                                                                |
| vat\_number<mark style="color:red;">\*</mark>                | string | NIF da validação para a qual se vai criar a relação. **Tem de ser obrigatoriamente uma validação de pessoa caso o tipo de relação seja representative, manager ou beneficial\_owner.** |
| position\_in\_organization<mark style="color:red;">\*</mark> | string | <p>Tipo de relação.</p><p>Valores possíveis: representative, manager, owner, beneficial_owner</p>                                                                                      |

{% tabs %}
{% tab title="200: OK Relação adicionada com sucesso." %}
```
{
    "version": 0.1,
    "timestamp": 1697798272664,
    "data": {
        "id": "8e6c7899-7c13-33d1-0538-50faf20f123e"
    }
}
```
{% endtab %}

{% tab title="400: Bad Request Tipo de relação inválido." %}
```json
{
    "message": {
        "version": 0.1,
        "timestamp": 1697798319930,
        "message": "O tipo de relação não é válido."
    }
}
```
{% endtab %}
{% endtabs %}

### Legenda

* **id**: id da nova relação.

## Editar uma relação de validação

<mark style="color:green;">`POST`</mark> `https://www.pepdata.com/api/edit_validation_relationship`

Endpoint para editar uma relação de validação

#### Headers

| Name                                             | Type   | Description     |
| ------------------------------------------------ | ------ | --------------- |
| Authentication<mark style="color:red;">\*</mark> | string | key \[API\_KEY] |

#### Request Body

| Name                                                         | Type   | Description                                                                                                                                    |
| ------------------------------------------------------------ | ------ | ---------------------------------------------------------------------------------------------------------------------------------------------- |
| id\_relationship\_info<mark style="color:red;">\*</mark>     | string | identificador da tabela de informações das relações associado à relação a editar.                                                              |
| position\_in\_organization<mark style="color:red;">\*</mark> | string | <p>Tipo de relação.</p><p></p><p>Valores possíveis:</p><ul><li>representative</li><li>manager</li><li>owner</li><li>beneficial_owner</li></ul> |

{% tabs %}
{% tab title="200: OK Relação editada com sucesso." %}
```
{
    "version": 0.1,
    "timestamp": 1697798682365,
    "data": {
        "message": "Relação editada com sucesso."
    }
}
```
{% endtab %}

{% tab title="400: Bad Request Tipo de relação inválido." %}
```json
{
    "message": {
        "version": 0.1,
        "timestamp": 1697798319930,
        "message": "O tipo de relação não é válido."
    }
}
```
{% endtab %}
{% endtabs %}

## Apagar uma relação de validação

<mark style="color:green;">`POST`</mark> `https://www.pepdata.com/api/delete_validation_relationship`

Endpoint para apagar uma relação de validação

#### Headers

| Name                                             | Type   | Description     |
| ------------------------------------------------ | ------ | --------------- |
| Authentication<mark style="color:red;">\*</mark> | string | key \[API\_KEY] |

#### Request Body

| Name                                                     | Type   | Description                                                                       |
| -------------------------------------------------------- | ------ | --------------------------------------------------------------------------------- |
| id\_relationship\_info<mark style="color:red;">\*</mark> | string | identificador da tabela de informações das relações associado à relação a editar. |

{% tabs %}
{% tab title="200: OK Relação editada com sucesso." %}
```
{
    "version": 0.1,
    "timestamp": 1697798682365,
    "data": {
        "message": "Relação editada com sucesso."
    }
}
```
{% endtab %}

{% tab title="400: Bad Request Identificador da tabela de informações das relações inválido." %}
```json
{
    "message": {
        "version": 0.1,
        "timestamp": 1697798319930,
        "message": "O identificador da tabela de informações das relações não é válido."
    }
}
```
{% endtab %}
{% endtabs %}
