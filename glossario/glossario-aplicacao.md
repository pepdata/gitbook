---
description: >-
  Esta página contém o significado de várias palavras utilizadas na aplicação da
  PEPData, de forma a facilitar a sua compreensão e utilização.
---

# Glossário da Aplicação

### Associado

[Pessoa reconhecida como estreitamente associada](glossario-legal-portugal.md#pessoa-reconhecida-como-estreitamente-associada).

### Classificação

Classe ou conjunto de classes atribuídas a uma [pessoa identificável](glossario-aplicacao.md#pessoa-identificavel), podendo estas ser:

1. [Pessoa Politicamente Exposta](glossario-legal-portugal.md#pessoa-politicamente-exposta) (PEP)
2. [Familiar](glossario-aplicacao.md#familiar)
3. [Associado](glossario-aplicacao.md#associado)
4. [Sancionado](glossario-aplicacao.md#sancionado)
5. [Titular de Outros Cargos Políticos ou Públicos](glossario-legal-portugal.md#titular-de-outros-cargos-politicos-ou-publicos)

### Familiar

[Membro próximo da família](glossario-legal-portugal.md#membro-proximo-da-familia).

### Grau de semelhança

Percentagem de semelhança entre dois nomes, podendo variar entre 0, no caso dos nomes serem totalmente diferentes, e 100%, no caso dos nomes serem iguais. Este resultado é calculado através de um algoritmo desenhado pela PEPData que, no processo de comparação, ignora as diferenças de acentuação, capitalização e a existência de [partículas](https://www.irn.mj.pt/IRN/sections/irn/a\_registral/registo-civil/docs-do-civil/dar-o-nome/) (como "de", "da", "e", etc.) o que o torna mais robusto.\
Exemplo: o grau de semelhança entre os nomes "joao silva lopes" e "João da Silva e Lopes" é de 100%.

### Ocupação

Trabalho ou profissão de uma [pessoa identificável](glossario-aplicacao.md#pessoa-identificavel). É constituído por um cargo, um [órgão](glossario-aplicacao.md#orgao) e uma [organização](glossario-aplicacao.md#organizacao).

### Organização

Empresa ou entidade estatal.\
Exemplos: Governo Português, Academia da Força Aérea, TAP.

### Organização identificável

Empresa ou entidade que necessite de ser identificada de acordo com a lei.

### Órgão

Departamento, divisão ou subdivisão dentro de uma [organização](glossario-aplicacao.md#organizacao).\
Exemplos: Departamento Administrativo e Financeiro, Divisão de Ordenamento, Órgão de Gestão.

### País identificável

São considerados como identificáveis os seguintes tipos de países:

1. País terceiro de risco elevado que apresenta deficiências estratégicas no regime de combate ao branqueamento de capitais e financiamento do terrorismo,[ de acordo com a UE](https://eur-lex.europa.eu/eli/reg\_del/2023/410).
2. Países com sanções abrangentes por [parte dos EUA](https://home.treasury.gov/policy-issues/financial-sanctions/sanctions-programs-and-country-information).
3. Países constantes na "lista negra" ou "lista cinzenta" do [FATF/GAFI](https://www.fatf-gafi.org/en/countries/black-and-grey-lists.html).
4. Países pertencentes à lista dos países, territórios e regiões com regimes de tributação privilegiada, claramente mais favoráveis, mantidas pelo [Governo Português](https://data.dre.pt/eli/port/309-A/2020/12/31/p/dre).

### Pessoa Identificável

Pessoa que, devido às suas [ações](glossario-aplicacao.md#sancionado), [ocupações](glossario-aplicacao.md#ocupacao), relações familiares ou societárias, necessite de ser identificada, de acordo com a lei.

### Regra

Norma, definida pelo utilizador da aplicação, que define o modo como a [classificação](glossario-aplicacao.md#classificacao) automática das [validações](glossario-aplicacao.md#validacao) irá ser aplicada.

## Relação

Relação entre duas entidades.

### Sancionado

Pessoa cujo nome conste numa das seguintes listas:

* [Nações Unidas (ONU)](https://www.un.org/securitycouncil/)
* [União Europeia (UE)](https://www.sanctionsmap.eu/#/main)
* [Departamento do Tesouro dos EUA (OFAC)](https://www.treasury.gov/resource-center/sanctions/SDN-List/Pages/default.aspx)
* [Tesouro de Sua Majestade do Reino Unido (HM Treasury)](https://www.gov.uk/government/organisations/hm-treasury)

### Validação

Pessoa adicionada, por parte do utilizador da aplicação, que pode, ou não, ter correspondência com uma [pessoa identificável](glossario-aplicacao.md#pessoa-identificavel) que conste na base de dados da PEPData.\
Uma validação pode ser _analisada_ ao se visualizar as [pessoas identificáveis](glossario-aplicacao.md#pessoa-identificavel) sugeridas pela aplicação como possível correspondência.\
Uma validação pode ser _determinada_ quando se estipula se existe uma correspondência entre esta e uma [pessoa identificável](glossario-aplicacao.md#pessoa-identificavel).
