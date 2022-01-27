# Importação de clientes

A nova importação de clientes permite-lhe, com facilidade e rapidez, fazer o upload dos seus clientes para a plataforma da PEPData, criando automaticamente um registo para cada cliente.

Para tal, por favor divida a informação a importar em 3 ficheiros distintos:

* Organizações
  * Ficheiro com os seus clientes organizacionais
* Pessoas singulares
  * Ficheiro com os membros da administração e beneficiários efetivos dos seus clientes
* Relações entre pessoas singulares e organizações
  * Ficheiro que mapeia as relações entre as organizações e as pessoas singulares mencionadas anteriormente
  * Este deve ser o último ficheiro a ser importado, só sendo aceite caso os dois restantes já tenham sido inseridos

Após a criação destes 3 ficheiros, poderá proceder à sua importação através do botão "Importar Registos", presente na página "Registo de Clientes".

## Detalhes dos ficheiros a importar

### Detalhes Gerais

* A primeira linha deve conter o nome das colunas que representam a informação a importar
* Extensão .txt ou .csv
* Limitado a 700.000 linhas por cada importação

### Ficheiro das organizações

* Deve conter uma organização por linha
* Propriedades aceites (obrigatórias a negrito):

| Campos                | Notas                                                                                                                                                                                                                               |
| --------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| id\_custom            | Identificador do cliente utilizado pela sua organização. Tem de ser único.                                                                                                                                                          |
| **name**              |                                                                                                                                                                                                                                     |
| **vat\_number**       |                                                                                                                                                                                                                                     |
| responsible\_email    | Email do utilizador que irá ficar responsável pelo questionário do cliente. Tem de ser um utilizador inserido na sua organização.                                                                                                   |
| invited\_email        | Email da pessoa a convidar para preenchimento do questionário. Nota: o convite terá de ser enviado manualmente, após a inserção.                                                                                                    |
| corporate\_object     |                                                                                                                                                                                                                                     |
| foundation\_date      |                                                                                                                                                                                                                                     |
| nace\_codes           | Códigos CAE. Separados por ponto e vírgula caso existam múltiplos.                                                                                                                                                                  |
| constitution\_country |                                                                                                                                                                                                                                     |
| operations\_countries | Separados por ponto e vírgula caso existam múltiplos.                                                                                                                                                                               |
| is\_identified        | 0, no caso de não existir identificação.                                                                                                                                                                                            |
| address\_country      |                                                                                                                                                                                                                                     |
| address\_postal\_code |                                                                                                                                                                                                                                     |
| address               |                                                                                                                                                                                                                                     |
| address\_door         |                                                                                                                                                                                                                                     |
| address\_district     |                                                                                                                                                                                                                                     |
| address\_city         |                                                                                                                                                                                                                                     |
| has\_branch\_offices  | 1 ou 0, caso existam sucursais ou não, respetivamente.                                                                                                                                                                              |
| has\_adverse\_media   | 1 ou 0, caso existam sucursais ou não, respetivamente.                                                                                                                                                                              |
| adverse\_media        | Tipos de adverse media, no formato \[old/new]﻿\_\[serious/light]_\__\[allegations/﻿accusations/﻿convictions]. Separados por ponto e vírgula caso existam múltiplos. Exemplo: old\_serious_\__allegations; new\_light_\__convictions |

{% hint style="warning" %}
Assegure-se que nenhum dos valores inseridos, incluindo nome da organização, não possui vírgulas, caso contrário a importação não irá ser bem sucedida.
{% endhint %}

#### Ficheiro exemplo

{% file src="../../.gitbook/assets/organizations.csv" %}

### Ficheiro das pessoas singulares

* Deve conter uma pessoa singular por linha
* Propriedades aceites (obrigatórias a negrito):

| Campos                | Notas                                                                                                                                                                                                                               |
| --------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| id\_custom            | Identificador do cliente utilizado pela sua organização. Tem de ser único.                                                                                                                                                          |
| **name**              |                                                                                                                                                                                                                                     |
| **vat\_number**       | Caso não possua o número de contribuinte da pessoa singular poderá gerar um identificador único, que deverá possuir uma letra como primeiro caracter. Ex: ID659                                                                     |
| responsible\_email    | Email do utilizador que irá ficar responsável pelo questionário do cliente. Tem de ser um utilizador inserido na sua organização.                                                                                                   |
| invited\_email        | Email do utilizador a convidar. O convite terá que ser enviado manualmente, depois da inserção.                                                                                                                                     |
| email                 | Email da pessoa singular.                                                                                                                                                                                                           |
| birth\_date           |                                                                                                                                                                                                                                     |
| nationalities         | Separados por ponto e vírgula caso existam múltiplos.                                                                                                                                                                               |
| place\_of\_birth      |                                                                                                                                                                                                                                     |
| is\_identified        | 0, no caso de não existir identificação.                                                                                                                                                                                            |
| address\_type         | Valores aceites: residence, fiscal\_residence e headquarters.                                                                                                                                                                       |
| address\_country      |                                                                                                                                                                                                                                     |
| address\_postal\_code |                                                                                                                                                                                                                                     |
| address               |                                                                                                                                                                                                                                     |
| address\_door         |                                                                                                                                                                                                                                     |
| address\_district     |                                                                                                                                                                                                                                     |
| address\_city         |                                                                                                                                                                                                                                     |
| has\_adverse\_media   | 1 ou 0, caso existam sucursais ou não, respetivamente.                                                                                                                                                                              |
| adverse\_media        | Tipos de adverse media, no formato \[old/new]﻿\_\[serious/light]_\__\[allegations/﻿accusations/﻿convictions]. Separados por ponto e vírgula caso existam múltiplos. Exemplo: old\_serious_\__allegations; new\_light_\__convictions |

#### Ficheiro exemplo

{% file src="../../.gitbook/assets/individuals.csv" %}

### Ficheiro das relações entre pessoas singulares e organizações

* Deve conter uma relação por linha
* Propriedades aceites (obrigatórias a negrito):

| Campos                         | Notas                                                                                           |
| ------------------------------ | ----------------------------------------------------------------------------------------------- |
| **organization\_vat\_number**  | Este valor já deve existir no sistema                                                           |
| **individual\_vat\_number**    | Este valor já deve existir no sistema                                                           |
| **position\_in\_organization** | Pode ter texto livre ou beneficial\_owner, no caso da relação ser enquanto beneficiário efetivo |
| capital\_percentage            | Apenas pode ser preenchido caso o valor do campo position\_in\_company seja beneficial\_owner   |
| voting\_rights\_percentage     | Apenas pode ser preenchido caso o valor do campo position\_in\_company seja beneficial\_owner   |

#### Ficheiro exemplo

{% file src="../../.gitbook/assets/relationships.csv" %}
