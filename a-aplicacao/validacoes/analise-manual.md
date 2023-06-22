# Análise manual

Na [página de validações](./), pode completar uma validação através do respetivo botão em forma de lupa, que lhe dá acesso a uma janela de análise.

Esta janela poderá sugerir nomes de [pessoas identificáveis](../../glossario/glossario-aplicacao.md#pessoa-identificavel) (no caso de se tratar de uma validação de pessoa singular) ou [organizações identificáveis](../../glossario/glossario-aplicacao.md#organizacao-identificavel) (no caso de se tratar de uma validação de organização) relevantes, com o respetivo [grau de semelhança](../../glossario/glossario-aplicacao.md#grau-de-semelhanca) relativo ao nome da [validação](../../glossario/glossario-aplicacao.md#validacao).

<figure><img src="../../.gitbook/assets/analisar validação PT.jpg" alt=""><figcaption><p>Janela de análise manual</p></figcaption></figure>

Na linha de cada [pessoa identificável](../../glossario/glossario-aplicacao.md#pessoa-identificavel), pode ver o seu perfil através do botão “👁”, definir uma correspondência através do botão “✓” ou adicionar/remover pessoas da lista de não correspondência através dos ícones em forma de pessoa.

Caso se trate de uma validação de organização, em cada linha de [organização identificável](../../glossario/glossario-aplicacao.md#organizacao-identificavel), poderá definir uma correspondência através do botão “✓” ou adicionar/remover organizações da lista de não correspondência através dos ícones em forma de edifício.

Caso não exista uma correspondência, ou nenhuma das sugestões da aplicação esteja correta, pode validar o nome como não sendo identificável através do botão “✗ Não identificável”.

Uma [validação](../../glossario/glossario-aplicacao.md#validacao) está concluída após definir se existe correspondência entre esta e uma pessoa/organização identificável que conste na base de dados da PEPData.

{% hint style="info" %}
### Como são encontrados os resultados sugeridos?

#### Por nome

Nas validações de pessoas singulares, todos os nomes que formam o nome da validação têm que constar no nome da [pessoa identificável](../../glossario/glossario-aplicacao.md#pessoa-identificavel) que aparece como resultado, com exceção das [partículas](https://www.irn.mj.pt/IRN/sections/irn/a\_registral/registo-civil/docs-do-civil/dar-o-nome/) (como "de", "da", "e", etc.). Exemplificando:

1. "João Pedro Silva" poderá ter como resultado o nome "João Pedro Soares da Silva".
2. "João Pedro Pereira" **não** poderá ter como resultado o nome "João Pedro Soares da Silva", uma vez que este não possui o nome "Pereira".
3. "João Pedro da Silva" poderá ter como resultado o nome "João Pedro Silva" uma vez que a [partícula ](https://www.irn.mj.pt/IRN/sections/irn/a\_registral/registo-civil/docs-do-civil/dar-o-nome/)"da" é ignorada.

Nas validações de pessoas singulares, as abreviaturas, caso existam, são consideradas. Exemplificando:

1. "João P Silva" poderá ter como resultado o nome "João Pedro Soares da Silva".

No caso das validações de organizações, a pesquisa vai tentar encontrar algum resultado em que o nome corresponda exatamente ao nome da validação.

#### Por data de nascimento (válido apenas para validações de pessoas singulares)

Nas validações de pessoas singulares, a data de nascimento da validação, caso exista, é utilizada para filtrar os resultados. Exemplificando:

1. Caso tenha introduzido a data de nascimento "01/01/1990" na validação, só irão aparecer [pessoas identificáveis](../../glossario/glossario-aplicacao.md#pessoa-identificavel) com a mesma data de nascimento ou sem informação relativa à data de nascimento.

#### Por limite de resultados

No caso das validações de pessoas singulares, no máximo, são-lhe mostrados os 20 resultados com maior grau de semelhança.

No caso das validações de organizações, é-lhe apresentado, caso exista, um resultado cujo nome corresponda exatamente ao nome da validação.&#x20;

#### Por opções auxiliares (apenas válido para validações de pessoas singulares)

As seguinte opções auxiliares podem ser ativadas ou desativadas na [página de configurações](../configuracoes/):&#x20;

* Os nomes introduzidos contêm sempre o primeiro nome próprio na primeira posição.
* Os nomes introduzidos contêm sempre o último apelido na última posição.

Ao estarem ativas, estas opções permitem que o sistema considere que o primeiro e último nome introduzidos correspondem sempre ao primeiro e último nome da pessoa, conduzindo a melhores resultados, nestas situações.&#x20;

Estas opções devem estar de acordo com a qualidade dos dados que recolhe dos seus clientes. &#x20;
{% endhint %}

## Outras funcionalidades

### Adicionar Pessoa (disponível em validações de pessoas singulares)

Caso tenha a certeza que uma determinada [validação](../../glossario/glossario-aplicacao.md#validacao) deva ser considerada como pessoa identificável e esta não se encontre nas sugestões, poderá adicioná-la à base de dados da PEPData. Após a adição, será então possível considerar a [validação](../../glossario/glossario-aplicacao.md#validacao) como sendo identificável.

{% hint style="info" %}
A pessoa adicionada por si apenas será visível para a sua organização. A PEPData, no futuro, irá rever o perfil da mesma. Caso esta pessoa seja [identificável](../../glossario/glossario-aplicacao.md#pessoa-identificavel), segundo a lei em vigor, a PEPData irá levantar a restrição e passará a disponibilizá-la a todos os clientes.
{% endhint %}

&#x20;
