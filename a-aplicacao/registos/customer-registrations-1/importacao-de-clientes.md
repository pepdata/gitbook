# Importação de fornecedores

A importação de fornecedores permite-lhe, com facilidade e rapidez, fazer o upload dos seus clientes para a plataforma da PEPData, criando automaticamente um registo para cada um.

Para tal, por favor divida a informação a importar em 2 ficheiros distintos:

* Organizações
  * Ficheiro que inclui os seus clientes empresa
* Pessoas
  * Ficheiro com os membros da administração ou beneficiários efetivos

Após a criação destes ficheiros, poderá proceder à sua importação através do botão "Importar fornecedores", presente na página "Fornecedores".

## Detalhes dos ficheiros a importar

### Detalhes Gerais

* A primeira linha deve conter o nome das colunas que representam a informação a importar
* Extensão .txt ou .csv
* Limitado a 700.000 linhas por cada importação

### Ficheiro das organizações

* Deve conter uma organização por linha
* Propriedades aceites (obrigatórias a negrito):

| Campos                | Notas                                                                                                                                                                                                                                 |
| --------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| id\_custom            | Identificador do cliente utilizado pela sua organização. Tem de ser único.                                                                                                                                                            |
| **name**              |                                                                                                                                                                                                                                       |
| **vat\_number**       | Os números de contribuinte internacionais devem conter o código do país correspondente no início. Ex: FR12345678901 para um número de contribuinte francês.                                                                           |
| responsible\_email    | Email do utilizador que irá ficar responsável pelo questionário do cliente. Tem de ser um utilizador inserido na sua organização.                                                                                                     |
| invited\_email        | Email da pessoa a convidar para preenchimento do questionário. Nota: o convite terá de ser enviado manualmente, após a inserção.                                                                                                      |
| corporate\_object     |                                                                                                                                                                                                                                       |
| foundation\_date      |                                                                                                                                                                                                                                       |
| nace\_codes           | Códigos CAE. Separados por ponto e vírgula caso existam múltiplos.                                                                                                                                                                    |
| country               | A aplicação da PEPData suporta qualquer valor [ISO 3166](https://en.wikipedia.org/wiki/ISO\_3166), nome comum ou nome oficial de cada país.                                                                                           |
| operations\_countries | Separados por ponto e vírgula caso existam múltiplos.                                                                                                                                                                                 |
| is\_identified        | 0, no caso de não existir identificação.                                                                                                                                                                                              |
| country\_address      | A aplicação da PEPData suporta qualquer valor [ISO 3166](https://en.wikipedia.org/wiki/ISO\_3166), nome comum ou nome oficial de cada país.                                                                                           |
| address\_postal\_code |                                                                                                                                                                                                                                       |
| address               |                                                                                                                                                                                                                                       |
| address\_door         |                                                                                                                                                                                                                                       |
| address\_district     |                                                                                                                                                                                                                                       |
| address\_city         |                                                                                                                                                                                                                                       |
| has\_branch\_offices  | 1 ou 0, caso existam sucursais ou não, respetivamente.                                                                                                                                                                                |
| adverse\_media        | Tipos de adverse media, no formato \[old/new]﻿\_\[serious/light]_\__\[allegations/﻿accusations/﻿convictions]. Separados por ponto e vírgula caso existam múltiplos. Exemplo: old\_serious\_\__allegations; new\_light_\_\_convictions |

{% hint style="warning" %}
Assegure-se que nenhum dos valores inseridos, incluindo nome da organização, não possui vírgulas, caso contrário a importação não irá ser bem sucedida.
{% endhint %}

#### Ficheiro exemplo

{% file src="../../../.gitbook/assets/organizations (1).csv" %}

### Ficheiro das pessoas

* Deve conter uma pessoa singular por linha
* Propriedades aceites (obrigatórias a negrito):

| Campos                | Notas                                                                                                                                                                                                                                 |
| --------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| id\_custom            | Identificador do cliente utilizado pela sua organização. Tem de ser único.                                                                                                                                                            |
| **name**              | Poderá ver [aqui](importacao-de-clientes.md#regras-a-cumprir) as regras a cumprir relativamente aos nomes.                                                                                                                            |
| **vat\_number**       | Caso não possua o número de contribuinte da pessoa singular poderá gerar um identificador único, que deverá possuir uma letra como primeiro caracter. Ex: ID659                                                                       |
| responsible\_email    | Email do utilizador que irá ficar responsável pelo questionário do cliente. Tem de ser um utilizador inserido na sua organização.                                                                                                     |
| invited\_email        | Email do utilizador a convidar. O convite terá que ser enviado manualmente, depois da inserção.                                                                                                                                       |
| email                 | Email da pessoa singular.                                                                                                                                                                                                             |
| birth\_date           | A data de nascimento deve seguir o formato dd-mm-yyyy, dd/mm/yyyy, yyyy-mm-dd ou yyyy/mm/dd.                                                                                                                                          |
| nationalities         | Separados por ponto e vírgula caso existam múltiplos.                                                                                                                                                                                 |
| country               | A aplicação da PEPData suporta qualquer valor [ISO 3166](https://en.wikipedia.org/wiki/ISO\_3166), nome comum ou nome oficial de cada país.                                                                                           |
| address\_type         | Valores aceites: residence, fiscal\_residence e headquarters.                                                                                                                                                                         |
| country\_address      | A aplicação da PEPData suporta qualquer valor [ISO 3166](https://en.wikipedia.org/wiki/ISO\_3166), nome comum ou nome oficial de cada país.                                                                                           |
| address\_postal\_code |                                                                                                                                                                                                                                       |
| address               |                                                                                                                                                                                                                                       |
| address\_door         |                                                                                                                                                                                                                                       |
| address\_district     |                                                                                                                                                                                                                                       |
| address\_city         |                                                                                                                                                                                                                                       |
| adverse\_media        | Tipos de adverse media, no formato \[old/new]﻿\_\[serious/light]_\__\[allegations/﻿accusations/﻿convictions]. Separados por ponto e vírgula caso existam múltiplos. Exemplo: old\_serious\_\__allegations; new\_light_\_\_convictions |

#### Ficheiro exemplo

{% file src="../../../.gitbook/assets/individuals (2).csv" %}

