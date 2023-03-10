# Importação de transações

A importação de tansações permite-lhe, com facilidade e rapidez, fazer o upload das suas transações para a plataforma da PEPData, criando automaticamente um registo para cada uma.

Para tal, por favor divida a informação a importar em 3 ficheiros distintos:

* Transações de bens
* Transações de serviços
* Transações de Subscrição de Fundos/Oportunidades

Após a criação de um ou mais destes ficheiros, poderá proceder à sua importação através do botão "Importar Registos", presente na página "Registo de Transações".

## Detalhes dos ficheiros a importar

### Detalhes Gerais

* A primeira linha deve conter o nome das colunas que representam a informação a importar
* Extensão .txt ou .csv
* Limitado a 700.000 linhas por cada importação

### Ficheiro das transações de bens

* Deve conter uma organização por linha
* Propriedades aceites (obrigatórias a negrito):

| Campos                         | Notas                                                                             |
| ------------------------------ | --------------------------------------------------------------------------------- |
| **name**                       |                                                                                   |
| id\_custom                     | Identificador da transação utilizado pela sua organização. Tem de ser único.      |
| description                    |                                                                                   |
| value\_in_\__euros             |                                                                                   |
| payment\_method                | Tipos de pagamento no formato: cash/installments                                  |
| installment\_in\_euros         |                                                                                   |
| installments\_frequency        | Frequência de pagamento: monthly, yearly, quarterly, semester, fortnightly, other |
| installments\_frequency\_other |                                                                                   |
| seller\_entity                 | Entidade de pagamento: self/external                                              |
| responsible\_email             |                                                                                   |
| acquisition\_purpose           |                                                                                   |
| observations                   |                                                                                   |

{% hint style="warning" %}
Assegure-se que nenhum dos valores inseridos, incluindo nome da transação, não possui vírgulas, caso contrário a importação não irá ser bem sucedida.
{% endhint %}

#### Ficheiro exemplo

{% file src="../../.gitbook/assets/transactions goods.txt" %}

### Ficheiro das transações de serviços

* Deve conter uma organização por linha
* Propriedades aceites (obrigatórias a negrito):

| Campos                         | Notas                                                                                            |
| ------------------------------ | ------------------------------------------------------------------------------------------------ |
| **name**                       |                                                                                                  |
| id\_custom                     | Identificador da transação utilizado pela sua organização. Tem de ser único.                     |
| description                    |                                                                                                  |
| occurrence                     | Tipos de ocorrência: punctual/regular                                                            |
| frequency                      | Frequência de pagamento: monthly, yearly, quarterly, semester, fortnightly, other                |
| value\_in\_euros               |                                                                                                  |
| provision\_start\_date         |                                                                                                  |
| provision\_end\_date           |                                                                                                  |
| provision\_date                |                                                                                                  |
| payment\_method                | Tipos de pagamento no formato:  cash/installments                                                |
| installment\_in\_euros         |                                                                                                  |
| installments\_frequency        | Frequência de pagamento das prestações: monthly, yearly, quarterly, semester, fortnightly, other |
| installments\_frequency\_other |                                                                                                  |
| seller\_entity                 | Entidade vendedora: self/external                                                                |
| responsible\_email             |                                                                                                  |
| acquisition\_purpose           |                                                                                                  |
| observations                   |                                                                                                  |

{% hint style="warning" %}
Assegure-se que nenhum dos valores inseridos, incluindo nome da transação, não possui vírgulas, caso contrário a importação não irá ser bem sucedida.
{% endhint %}

#### Ficheiro exemplo

{% file src="../../.gitbook/assets/transactions services (1).txt" %}

### Ficheiro das transações de subscrição de fundos/oportunidades

* Deve conter uma organização por linha
* Propriedades aceites (obrigatórias a negrito):

| Campos                                       | Notas                                                                        |
| -------------------------------------------- | ---------------------------------------------------------------------------- |
| **transaction\_name**                        |                                                                              |
| id\_custom                                   | Identificador da transação utilizado pela sua organização. Tem de ser único. |
| **fund\_name**                               |                                                                              |
| value\_in\_euros                             |                                                                              |
| iban                                         |                                                                              |
| swift                                        |                                                                              |
| number\_of\_subscribed\_participation\_units |                                                                              |
| contact\_email                               |                                                                              |

{% hint style="warning" %}
Assegure-se que nenhum dos valores inseridos, incluindo nome da transação, não possui vírgulas, caso contrário a importação não irá ser bem sucedida.
{% endhint %}

#### Ficheiro exemplo

{% file src="../../.gitbook/assets/transactions funds.txt" %}
