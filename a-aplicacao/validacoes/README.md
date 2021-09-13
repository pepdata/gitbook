# Validações

Esta página ajuda-o a determinar se os seus clientes, potenciais clientes ou beneficiários são [pessoas identificáveis](../../glossario/glossario-aplicacao.md#pessoa-identificavel), servindo também como repositório de toda a informação relacionada com os mesmos. A PEPData denomina cada nome adicionado por si como sendo uma [validação](../../glossario/glossario-aplicacao.md#validacao).

![Tabela de valida&#xE7;&#xF5;es](../../.gitbook/assets/image%20%2814%29.png)

## Adição, determinação e estados de validações

As [validações](../../glossario/glossario-aplicacao.md#validacao) podem ser adicionadas [manualmente](adicao-manual.md), uma a uma, ou [automaticamente](importacao-de-validacoes.md), o que lhe possibilita adicionar centenas de milhares de [validações](../../glossario/glossario-aplicacao.md#validacao) de uma só vez.

Um vez adicionada, uma [validação](../../glossario/glossario-aplicacao.md#validacao) irá ter o seu estado como _Incompleto_, o que significa que ainda não foi determinado se esta corresponde a uma [pessoa identificável](../../glossario/glossario-aplicacao.md#pessoa-identificavel). Esta determinação, à semelhança da adição, pode também ser feita [manualmente](analise-manual.md), uma a uma, ou [automaticamente](aplicacao-de-regras.md), o que lhe possibilita a determinação de centenas de milhares de [validações](../../glossario/glossario-aplicacao.md#validacao) de uma só vez. Após esta operação, o estado da [validação](../../glossario/glossario-aplicacao.md#validacao) irá passar a _Completo_. 

Uma validação _Completa_ poderá ser: 

* Completa - Identificada: caso tenha existido correspondência com uma pessoa identificável da base de dados da PEPData ou o seu país seja sancionado. 
* Completa - Não Identificada: caso não tenha existido correspondência com uma pessoa identificável da base de dados da PEPData e o seu país não seja sancionado.

## Validações que necessitam de atenção

A base de dados de [pessoas identificáveis](../../glossario/glossario-aplicacao.md#pessoa-identificavel) da PEPData está constantemente a ser atualizada, fazendo com que existam diariamente novas pessoas a ser introduzidas. Estas podem também ser removidas da plataforma, caso deixe de existir motivo para continuarem a ser identificadas, ex: ter passado 12 meses desde a última vez que ocuparam um cargo relevante e não terem qualquer outra [classificação](../../glossario/glossario-aplicacao.md#classificacao).

Neste sentido, cada vez que existam atualizações que requeiram a sua atenção, exemplo: uma validação que identificou como PEP ter deixado de o ser, as validações afetadas irão passar a ser sinalizadas como "Precisam de atenção".

{% hint style="info" %}
Esta sinalização não altera de qualquer modo a decisão tomada anteriormente em relação à validação.   
Exemplo: caso uma validação esteja como _Completa – não identificada_ e tenha sido adicionada uma [pessoa identificável](../../glossario/glossario-aplicacao.md#pessoa-identificavel) com o mesmo nome, a validação irá ser sinalizada mas irá continuar como _Completa – não identificada_.   
A aplicação, neste ponto, procura apenas auxiliar o utilizador, ficando a decisão de determinar a validação de maneira diferente do seu lado.
{% endhint %}

## Alteração e eliminação de validações

Caso pretenda alterar uma [validação](../../glossario/glossario-aplicacao.md#validacao) que já se encontre completa, poderá carregar no botão “✗", voltando esta ao estado _Incompleto_.

Caso pretenda eliminar uma [validação](../../glossario/glossario-aplicacao.md#validacao), poderá sempre carregar no botão “🗑️". Note que apenas poderá apagar validações com estado _Incompleto_. Caso pretenda apagar uma validação completa, terá de a cancelar primeiro \(ver passo anterior\). 

## Filtros

Nesta página, são-lhe ainda disponibilizados filtros que permitem mostrar as [validações](../../glossario/glossario-aplicacao.md#validacao) quanto ao seu estado ou origem. Por pré-definição, quando abre a página são mostradas todas as validações _incompletas._ 

![Filtros de valida&#xE7;&#xF5;es](../../.gitbook/assets/image%20%281%29.png)

Caso utilize os filtros para incluir as [validações](../../glossario/glossario-aplicacao.md#validacao) _Completas_, poderá ainda visualizar o seu resultado através de ícones:

* Avatar azul: significa que foi encontrada uma correspondência com uma [pessoa identificável](../../glossario/glossario-aplicacao.md#pessoa-identificavel) da base de dados da PEPData. Pode carregar neste ícone para abrir o perfil da mesma.
* Avatar translúcido: significa que não foi encontrada correspondência.
* Globo azul: significa que o país inserido na validação se encontra sancionado.
* Globo translúcido: significa que o país inserido na validação não se encontra sancionado.

![Exemplo de valida&#xE7;&#xF5;es completas](../../.gitbook/assets/image%20%284%29.png)

