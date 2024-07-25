# Importação

A importação permite-lhe, com facilidade e rapidez, fazer o upload dos seus clientes/fornecedores para a plataforma da PEPData, criando automaticamente um registo para cada um.

Para tal, por favor divida a informação a importar em 2 ficheiros distintos: um de Organizações e outro de Pessoas.

Após a criação destes ficheiros, poderá proceder à sua importação através do botão de importação.

## Detalhes dos ficheiros a importar

### Detalhes Gerais

* A primeira linha deve conter o nome das colunas que representam a informação a importar
* A separação de colunas deve ser feita por ;
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
| country\_constitution | A aplicação da PEPData suporta qualquer valor [ISO 3166](https://en.wikipedia.org/wiki/ISO\_3166), nome comum ou nome oficial de cada país.                                                                                           |
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

#### Ficheiro exemplo

{% file src="../../../.gitbook/assets/organizations (4).csv" %}

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
| country\_birth        | A aplicação da PEPData suporta qualquer valor [ISO 3166](https://en.wikipedia.org/wiki/ISO\_3166), nome comum ou nome oficial de cada país.                                                                                           |
| address\_type         | Valores aceites: residence, fiscal\_residence e headquarters.                                                                                                                                                                         |
| country\_address      | A aplicação da PEPData suporta qualquer valor [ISO 3166](https://en.wikipedia.org/wiki/ISO\_3166), nome comum ou nome oficial de cada país.                                                                                           |
| is\_identified        | 0, no caso de não existir identificação.                                                                                                                                                                                              |
| address\_postal\_code |                                                                                                                                                                                                                                       |
| address               |                                                                                                                                                                                                                                       |
| address\_door         |                                                                                                                                                                                                                                       |
| address\_district     |                                                                                                                                                                                                                                       |
| address\_city         |                                                                                                                                                                                                                                       |
| adverse\_media        | Tipos de adverse media, no formato \[old/new]﻿\_\[serious/light]_\__\[allegations/﻿accusations/﻿convictions]. Separados por ponto e vírgula caso existam múltiplos. Exemplo: old\_serious\_\__allegations; new\_light_\_\_convictions |

#### Ficheiro exemplo

{% file src="../../../.gitbook/assets/individuals (5).csv" %}

### Ficheiro das relações entre pessoas singulares e organizações

* Deve conter uma relação por linha
* Propriedades aceites (obrigatórias a negrito):

| Campos                         | Notas                                                                                                                                                                                                                                                                                                  |
| ------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **organization\_vat\_number**  | NIPC da organização a inserir as relações. Esta organização já deve existir no sistema.                                                                                                                                                                                                                |
| **vat\_number**                | NIF/NIPC da relação a ser inserida. Este indivíduo/organização já deve existir no sistema.                                                                                                                                                                                                             |
| **position\_in\_organization** | Pode ter texto livre (ex: "Presidente", "Gerente", etc.), "owner", no caso da relação ser enquanto acionista ou detentor de direitos de voto, ou "beneficial\_owner" caso seja beneficiário efetivo. Caso o vat\_number seja de uma organização, este campo deve ter obrigatoriamente o valor "owner". |
| capital\_percentage            | <p>Apenas pode ser preenchido caso o valor do campo position_in_organization seja "owner" ou "beneficial_owner". Nota: a separação das casas decimais deve ser feita com ".", ex: 19.96<br>Não inclua o símbolo de percentagem.</p>                                                                    |
| voting\_rights\_percentage     | <p>Apenas pode ser preenchido caso o valor do campo position_in_organization seja "owner" ou "beneficial_owner". Nota: a separação das casas decimais deve ser feita com ".", ex: 19.96<br>Não inclua o símbolo de percentagem.</p>                                                                    |

#### Ficheiro exemplo

{% file src="../../../.gitbook/assets/relationships (2).csv" %}
