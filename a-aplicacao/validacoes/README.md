# Validações

Esta página ajuda-o a determinar se os seus clientes, potenciais clientes ou beneficiários são [pessoas identificáveis](../../glossario/glossario-aplicacao.md#pessoa-identificavel), servindo também como repositório de toda a informação relacionada com os mesmos. A PEPData denomina cada nome adicionado por si como sendo uma [validação](../../glossario/glossario-aplicacao.md#validacao).

![Tabela de validações](<../../.gitbook/assets/image (14).png>)

## Adição, determinação e estados de validações

As [validações](../../glossario/glossario-aplicacao.md#validacao) podem ser adicionadas [manualmente](adicao-manual.md), uma a uma, ou [automaticamente](importacao-de-validacoes.md), o que lhe possibilita adicionar centenas de milhares de [validações](../../glossario/glossario-aplicacao.md#validacao) de uma só vez.

Um vez adicionada, uma [validação](../../glossario/glossario-aplicacao.md#validacao) irá ter o seu estado como _Incompleto_, o que significa que ainda não foi determinado se esta corresponde a uma [pessoa identificável](../../glossario/glossario-aplicacao.md#pessoa-identificavel). Esta determinação, à semelhança da adição, pode também ser feita [manualmente](analise-manual.md), uma a uma, ou [automaticamente](aplicacao-de-regras.md), o que lhe possibilita a determinação de centenas de milhares de [validações](../../glossario/glossario-aplicacao.md#validacao) de uma só vez. Após esta operação, o estado da [validação](../../glossario/glossario-aplicacao.md#validacao) irá passar a _Completo_.&#x20;

Uma validação _Completa_ poderá ser:&#x20;

* Completa - Identificada: caso tenha existido correspondência com uma pessoa identificável da base de dados da PEPData ou o seu país seja sancionado.&#x20;
* Completa - Não Identificada: caso não tenha existido correspondência com uma pessoa identificável da base de dados da PEPData e o seu país não seja sancionado.

## Validações que necessitam de atenção

A base de dados de [pessoas identificáveis](../../glossario/glossario-aplicacao.md#pessoa-identificavel) da PEPData está constantemente a ser atualizada, fazendo com que existam diariamente novas pessoas a ser introduzidas. Estas podem também ser removidas da plataforma, caso deixe de existir motivo para continuarem a ser identificadas, ex: ter passado 12 meses desde a última vez que ocuparam um cargo relevante e não terem qualquer outra [classificação](../../glossario/glossario-aplicacao.md#classificacao).

Neste sentido, cada vez que existam atualizações que requeiram a sua atenção, exemplo: uma validação que identificou como PEP ter deixado de o ser, as validações afetadas irão passar a ser sinalizadas como "Precisam de atenção".

{% hint style="info" %}
Esta sinalização não altera de qualquer modo a decisão tomada anteriormente em relação à validação. \
Exemplo: caso uma validação esteja como _Completa – não identificada_ e tenha sido adicionada uma [pessoa identificável](../../glossario/glossario-aplicacao.md#pessoa-identificavel) com o mesmo nome, a validação irá ser sinalizada mas irá continuar como _Completa – não identificada_. \
A aplicação, neste ponto, procura apenas auxiliar o utilizador, ficando a decisão de determinar a validação de maneira diferente do seu lado.
{% endhint %}

## Alteração e eliminação de validações

Caso pretenda alterar uma [validação](../../glossario/glossario-aplicacao.md#validacao) que já se encontre completa, poderá carregar no botão “✗", voltando esta ao estado _Incompleto_.

Caso pretenda eliminar uma [validação](../../glossario/glossario-aplicacao.md#validacao), poderá sempre carregar no botão “🗑️". Note que apenas poderá apagar validações com estado _Incompleto_. Caso pretenda apagar uma validação completa, terá de a cancelar primeiro (ver passo anterior).&#x20;

## Filtros

Nesta página, são-lhe ainda disponibilizados filtros que permitem mostrar as [validações](../../glossario/glossario-aplicacao.md#validacao) quanto ao seu estado ou origem. Por pré-definição, quando abre a página são mostradas todas as validações _incompletas._&#x20;

![Filtros de validações](<../../.gitbook/assets/image (1).png>)

Caso utilize os filtros para incluir as [validações](../../glossario/glossario-aplicacao.md#validacao) _Completas_, poderá ainda visualizar o seu resultado através de ícones:

* Avatar azul: significa que foi encontrada uma correspondência com uma [pessoa identificável](../../glossario/glossario-aplicacao.md#pessoa-identificavel) da base de dados da PEPData. Pode carregar neste ícone para abrir o perfil da mesma.
* Avatar translúcido: significa que não foi encontrada correspondência.
* Globo azul: significa que o país inserido na validação se encontra sancionado.
* Globo translúcido: significa que o país inserido na validação não se encontra sancionado.

![Exemplo de validações completas](<../../.gitbook/assets/image (4).png>)

### FAQs

<details>

<summary>Todos os clientes têm acesso à funcionalidade de validações?</summary>

Não. Esta funcionalidade é paga, consequentemente é exclusiva para quem a adquiriu.

</details>

<details>

<summary>O estado do meu cliente sofreu alterações. Posso validá-lo novamente?</summary>

Sim. Quando receber a notificação de que um estado de cliente sofreu alterações, poe voltar ao menu de validações e ver os detalhes dessa pessoa.

</details>

<details>

<summary>Só é possível pesquisar por nome?</summary>

A pesquisa pode ser feita com dois nomes e/ou data de nascimento e país. Estes dados servem por forma a cumprir na íntegra com a lei do RGPD.

</details>

<details>

<summary>Não obtive resultados na minha pesquisa, porquê?</summary>

Se não obteve nenhum resultado, significa que nas listas da platagorma, não se encontra nenhum nome com algum grau de semelhança com o nome introduzido. Neste caso, poderá considerá-lo como pessoa "não identificável".

Se tiver a certeza que esta pessoa é identificável, peja a resposta à pergunta: [«Para que serve o botão "adicionar pessoa"?»](./#para-que-serve-o-botao-adicionar-pessoa)

</details>

<details>

<summary>Para que serve o botão "adicionar pessoa"?</summary>

O botão "adicionar pessoa", serve para colocar uma pessoa sob vigilância caso o reconheça como sendo PEP, Familiar ou Associado de PEP, mas que ainda não faça parte das listas da plataforma. Desta forma, poderá adicionar diretamente uma pessoa à sua base de dados e validá-la automaticamente.

</details>

<details>

<summary>Porque é que uma pessoa ainda não consta na lista PEP?</summary>

Quando o nome que procura ainda não se encontra disponível nas listas da PEPData é porque a fonte oficial ainda não se encontra disponível. Todas as fontes utilizadas pela PEPData são oficiais e verficadas com regularidades, atualizando permanentemente as nossas listas.

</details>

<details>

<summary>Apenas sei os apelidos abreviados (ex: P., T. M.), obtenho resultados?</summary>

Sim, pode obter resultados com abreviaturas. No entanto, é também importante definir bem as regras de validação pra não obter resultados enganadores. Para que os resultados sejam mais fidedignos, o nome deverá estar completo ou ter, pelo menos, dois nomes completos e data de nascimento.&#x20;

Quanto mais completos forem os dados introduzidos, menos falsos positivos terá.

</details>
