# Aplicação de regras

Na [página de validações](./), pode realizar uma análise automática de cada validação que se encontre com um estado incompleto, através do botão “Aplicar Regras”.&#x20;

{% hint style="info" %}
Por pré-definição, as regras a aplicar estão desabilitadas, tendo de ser ativadas por si através da [página de configurações](../configuracoes/). No entanto, antes de o fazer, a leitura da seguinte informação é fortemente recomendada, uma vez que a aplicação das regras de validação, sem a sua correta compreensão, poderá provocar alterações indesejadas e complicadas ou impossíveis de reverter.
{% endhint %}

## Regras de validação

Existem duas regras de validação, que podem ser ativadas ou desativadas na [página de configurações](../configuracoes/):&#x20;

1. Considerar como não identificáveis os nomes que não tenham correspondência.&#x20;
2. Considerar como identificáveis todos os nomes com apenas uma correspondência possível e um elevado [grau de semelhança](../../glossario/glossario-aplicacao.md#grau-de-semelhanca).

No máximo, as regras serão aplicadas a 80.000 [validações](../../glossario/glossario-aplicacao.md#validacao) de cada vez.&#x20;

{% hint style="info" %}
### Como funciona a aplicação de regras?

Neste exemplo, considere que ambas as regras de validação se encontram ativas. Assim sendo, ao carregar em "Aplicar regras", o sistema irá proceder do seguinte modo, para cada [validação](../../glossario/glossario-aplicacao.md#validacao) incompleta:

1. Procura na base de dados da PEPData todas as pessoas identificáveis com um nome similar ao da [validação](../../glossario/glossario-aplicacao.md#validacao).
2. Através do passo anterior, e obtida uma lista de resultados sugeridos, como descrito na nota seguinte:&#x20;
   1. Caso não existam resultados sugeridos, uma vez que a regra 1 se encontra ativa, a [validação](../../glossario/glossario-aplicacao.md#validacao) irá ser definida como não sendo identificável.
   2. Caso exista apenas um resultado e o seu [grau de semelhança](../../glossario/glossario-aplicacao.md#grau-de-semelhanca) seja superior ao [threshold de validação](../configuracoes/#threshold-de-validacao), uma vez que a regra 2 se encontra ativa, a [validação](../../glossario/glossario-aplicacao.md#validacao) irá ser definida como identificável.
   3. Caso exista apenas um resultado e o [grau de semelhança](../../glossario/glossario-aplicacao.md#grau-de-semelhanca) seja inferior ou igual ao [threshold de validação](../configuracoes/#threshold-de-validacao), esta irá permanecer incompleta, sendo necessário realizar uma [análise manual](analise-manual.md).
   4. Caso existam múltiplos resultados a [validação](../../glossario/glossario-aplicacao.md#validacao) irá permanecer incompleta, sendo necessário realizar uma [análise manual](analise-manual.md).
{% endhint %}

{% hint style="info" %}
### Como são encontrados os resultados sugeridos?

#### Por nome

Todos os nomes que formam o nome da [validação](../../glossario/glossario-aplicacao.md#validacao) têm que constar no nome da pessoa identificável que aparece como resultado, com exceção das partículas (como "de", "da", "e", etc.). Exemplificando:

1. "João Pedro Silva" poderá ter como resultado o nome "João Pedro Soares da Silva".
2. "João Pedro Pereira" **não** poderá ter como resultado o nome "João Pedro Soares da Silva", uma vez que este não possui o nome "Pereira".
3. "João Pedro da Silva" poderá ter como resultado o nome "João Pedro Silva" uma vez que a [partícula ](https://www.irn.mj.pt/IRN/sections/irn/a\_registral/registo-civil/docs-do-civil/dar-o-nome/)"da" é ignorada.

Abreviaturas, caso existam, são consideradas. Exemplificando:

1. "João P Silva" poderá ter como resultado o nome "João Pedro Soares da Silva".

#### Por data de nascimento

A data de nascimento da [validação](../../glossario/glossario-aplicacao.md#validacao), caso exista, é utilizada para filtrar os resultados. Exemplificando:

1. Caso tenha introduzido a data de nascimento "01/01/1990" na [validação](../../glossario/glossario-aplicacao.md#validacao), só irão aparecer pessoas identificáveis com a mesma data de nascimento ou sem informação relativa à data de nascimento.

#### Por limite de resultados

No máximo, são-lhe mostrados os 20 resultados com maior [grau de semelhança](../../glossario/glossario-aplicacao.md#grau-de-semelhanca).&#x20;

#### Por opções auxiliares

As seguinte opções auxiliares podem ser ativadas ou desativadas na [página de configurações](../configuracoes/):&#x20;

* Os nomes introduzidos contêm sempre o primeiro nome próprio na primeira posição.
* Os nomes introduzidos contêm sempre o último apelido na última posição.

Ao estarem ativas, estas opções permitem que o sistema considere que o primeiro e último nome introduzidos correspondem sempre ao primeiro e último nome da pessoa, conduzindo a melhores resultados, nestas situações.&#x20;

Estas opções devem estar de acordo com a qualidade dos dados que recolhe dos seus clientes. &#x20;
{% endhint %}

##
