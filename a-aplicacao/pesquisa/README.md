# Pesquisar

Esta página permite-lhe pesquisar por nome, listando todas as [pessoas identificáveis](../../glossario/glossario-aplicacao.md#pessoa-identificavel) com nomes semelhantes ao introduzido.

Na listagem de resultados irão aparecer os nomes e datas de nascimento das pessoas encontradas, podendo ver o seu perfil através do botão “👁”.

![Página de pesquisa](../../.gitbook/assets/search.gif)

{% hint style="info" %}
#### Como são encontrados os resultados sugeridos?

**Por nome**

Todos os nomes que formam o nome da [validação](../../glossario/glossario-aplicacao.md#validacao) têm que constar no nome da [pessoa identificável ](../../glossario/glossario-aplicacao.md#pessoa-identificavel)que aparece como resultado. Exemplificando:

1. "João Pedro Silva" poderá ter como resultado o nome "João Pedro Soares da Silva".
2. "João Pedro Pereira" **não** poderá ter como resultado o nome "João Pedro Soares da Silva", uma vez que este não possui o nome "Pereira".

Abreviaturas, caso existam, são consideradas. Exemplificando:

1. "João P Silva" poderá ter como resultado o nome "João Pedro Soares da Silva".

**Por limite de resultados**

No máximo, são-lhe mostrados os 25 resultados com maior [grau de semelhança](../../glossario/glossario-aplicacao.md#grau-de-semelhanca).
{% endhint %}
