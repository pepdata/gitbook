# Importação

A importação de tansações permite-lhe, com facilidade e rapidez, fazer o upload das suas transações para a plataforma da PEPData, criando automaticamente um registo para cada uma.

Para tal, por favor divida a informação a importar em 3 ficheiros distintos:

* Transações de bens
* Transações de serviços
* Transações de Subscrição de Fundos/Oportunidades

Após a criação de um ou mais destes ficheiros, poderá proceder à sua importação através do botão "Importar Registos", presente na página "Registo de Transações".

## Detalhes dos ficheiros a importar

### Detalhes Gerais

* A primeira linha deve conter o nome das colunas que representam a informação a importar
* A separação de colunas deve ser feita por ponto e vírgula (;), para ficheiros .txt e .csv
* Extensão: .txt, .csv ou xlsx
* Limitado a 700.000 linhas por cada importação

### Ficheiro das transações de bens

* Deve conter uma organização por linha
* Propriedades aceites (obrigatórias a negrito):

| Campos                         | Notas                                                                             |
| ------------------------------ | --------------------------------------------------------------------------------- |
| **name**                       |                                                                                   |
| id\_custom                     | Identificador da transação utilizado pela sua organização. Tem de ser único.      |
| description                    |                                                                                   |
| value\_in\_euros               | Exemplo: 100,45                                                                   |
| payment\_method                | Tipos de pagamento no formato: prompt/installments                                |
| installment\_in\_euros         | Exemplo: 100,45                                                                   |
| installments\_frequency        | Frequência de pagamento: monthly, yearly, quarterly, semester, fortnightly, other |
| installments\_frequency\_other |                                                                                   |
| seller\_entity                 | Entidade de pagamento: self/external                                              |
| responsible\_email             |                                                                                   |
| acquisition\_purpose           |                                                                                   |
| observations                   |                                                                                   |

#### Ficheiro exemplo

{% file src="../../../.gitbook/assets/transactions goods (3).txt" %}

### Ficheiro das transações de serviços

* Deve conter uma organização por linha
* Propriedades aceites (obrigatórias a negrito):

| Campos                         | Notas                                                                                                                              |
| ------------------------------ | ---------------------------------------------------------------------------------------------------------------------------------- |
| **name**                       |                                                                                                                                    |
| id\_custom                     | Identificador da transação utilizado pela sua organização. Tem de ser único.                                                       |
| description                    |                                                                                                                                    |
| occurrence                     | Tipos de ocorrência: punctual/regular                                                                                              |
| frequency                      | Frequência de pagamento: monthly, yearly, quarterly, semester, fortnightly, other                                                  |
| value\_in\_euros               | Exemplo: 100,45                                                                                                                    |
| provision\_start\_date         | <p>Deve seguir um dos seguintes formatos:</p><ul><li>dd-mm-yyyy</li><li>dd/mm/yyyy</li><li>yyyy-mm-dd</li><li>yyyy/mm/dd</li></ul> |
| provision\_end\_date           | <p>Deve seguir um dos seguintes formatos:</p><ul><li>dd-mm-yyyy</li><li>dd/mm/yyyy</li><li>yyyy-mm-dd</li><li>yyyy/mm/dd</li></ul> |
| provision\_date                | <p>Deve seguir um dos seguintes formatos:</p><ul><li>dd-mm-yyyy</li><li>dd/mm/yyyy</li><li>yyyy-mm-dd</li><li>yyyy/mm/dd</li></ul> |
| payment\_method                | Tipos de pagamento no formato: prompt/installments                                                                                 |
| installment\_in\_euros         | Exemplo: 100,45                                                                                                                    |
| installments\_frequency        | Frequência de pagamento das prestações: monthly, yearly, quarterly, semester, fortnightly, other                                   |
| installments\_frequency\_other |                                                                                                                                    |
| seller\_entity                 | Entidade vendedora: self/external                                                                                                  |
| responsible\_email             |                                                                                                                                    |
| acquisition\_purpose           |                                                                                                                                    |
| observations                   |                                                                                                                                    |

#### Ficheiro exemplo

{% file src="../../../.gitbook/assets/transactions services (2).txt" %}

### Ficheiro das transações de subscrição de fundos/oportunidades

* Deve conter uma organização por linha
* Propriedades aceites (obrigatórias a negrito):

| Campos                                       | Notas                                                                        |
| -------------------------------------------- | ---------------------------------------------------------------------------- |
| **transaction\_name**                        |                                                                              |
| id\_custom                                   | Identificador da transação utilizado pela sua organização. Tem de ser único. |
| **fund\_name**                               |                                                                              |
| value\_in\_euros                             | Exemplo: 100,45                                                              |
| iban                                         |                                                                              |
| swift                                        |                                                                              |
| number\_of\_subscribed\_participation\_units |                                                                              |
| contact\_email                               |                                                                              |

#### Ficheiro exemplo

{% file src="../../../.gitbook/assets/transactions funds (1).txt" %}

### Ficheiro das relações entre pessoas singulares/coletivas e transações

* Deve conter uma transação por linha
* Propriedades aceites (obrigatórios a negrito):

| Campos                      | Notas                                                                                                                                            |
| --------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------ |
| **transaction\_id**         | Identificador da transação utilizado pela sua organização. Tem de ser único.                                                                     |
| **vat\_number**             | NIF/NIPC da relação a ser inserida. Este indivíduo/organização já deve existir no sistema.                                                       |
| **relationship\_type**      | <p>Tipo de relação.<br><br>Valores aceites:</p><ul><li>seller</li><li>buyer</li><li>seller_representative</li><li>buyer_representative</li></ul> |
| representative\_vat\_number | NIF/NIPC do representante da relação a ser inserida. Este indivíduo já deve existir no sistema.                                                  |

#### Ficheiro exemplo

{% file src="../../../.gitbook/assets/transactions relationships.txt" %}
