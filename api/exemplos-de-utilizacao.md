# Exemplos de utilização

Existem várias maneiras distintas de utilizar a API da PEPData. Esta página irá procurar descrever alguns exemplos e apresentar as suas vantagens e desvantagens para que possa decidir, de maneira informada, como adequar a utilização da API às suas necessidades.

## Pesquisa

Corresponde ao exemplo mais básico de utilização. Para seguir esta via, apenas necessita de utilizar o endpoint de [pesquisa de pessoa identificável](pesquisa.md#pesquisa-de-pessoa-identificavel).&#x20;

Este endpoint aceita um nome e uma data de nascimento como inputs e devolve os resultados de pesquisa que mais se assemelham aos termos pesquisados. De forma a obter melhores resultados, recomenda-se que leia a documentação referente à área de [pesquisa](../a-aplicacao/pesquisa.md).

Após receção dos resultados, poderá processá-los internamente de forma a decidir se a pessoa pesquisada corresponde a uma [pessoa identificável](../glossario/glossario-aplicacao.md#pessoa-identificavel) que conste na base de dados da PEPData.

#### Vantagens

* Solução bastante fácil e simples de implementar.
* Adequada no caso de precisar de validar pessoas em tempo real.

#### Desvantagens

* Não permite criar uma "carteira de clientes" na aplicação da PEPData, que lhe possibilita receber alertas futuros no caso de uma alteração de estado enquanto [pessoa identificável](../glossario/glossario-aplicacao.md#pessoa-identificavel). &#x20;
* Obriga-o a ter de criar critérios internos para a validação das pessoas pesquisadas, não ficando a sua decisão guardada na aplicação da PEPData.
* Apenas pode pesquisar uma pessoa de cada vez.
* Não permite validar [países sancionados](../glossario/glossario-aplicacao.md#pais-sancionado).

## Validações

Corresponde ao exemplo mais avançado de utilização. Para seguir esta via, necessita de utilizar vários [endpoints de validação](validacoes.md). A título de exemplo, propõe-se o seguinte fluxo de trabalho:

1. Adicione cada pessoa a validar através do endpoint `/add_validation`. Este aceita o nome, a data de nascimento e o país da pessoa, criando assim uma [validação](../glossario/glossario-aplicacao.md#validacao).&#x20;
2. Quando necessitar, aplique as [regras de validação](../a-aplicacao/validacoes/aplicacao-de-regras.md#regras-de-validacao) pretendidas através do endpoint `/apply_rules`. Estas irão permitir a [determinação](../a-aplicacao/validacoes/#adicao-e-determinacao-de-validacoes) de todas as [validações](../glossario/glossario-aplicacao.md#validacao) que se enquadrem nas regras que definiu.
3. As validações que permaneceram incompletas são mais difíceis de determinar e provavelmente necessitam de atenção humana. Recomenda-se, por isso, que sejam determinadas manualmente na aplicação da PEPData. No entanto, poderá fazê-lo através da API, recorrendo ao endpoint `/determine_validation`.

De forma a obter melhores resultados, recomenda-se que leia a documentação referente à área de [validações](../a-aplicacao/validacoes/).

#### Vantagens

* Permite criar uma "carteira de clientes" na aplicação da PEPData, que lhe possibilita receber alertas futuros no caso de uma alteração de estado enquanto pessoa identificável. &#x20;
* Todas as suas decisões ficam registadas na aplicação da PEPData, podendo ser exportadas para utilização futura.
* Pode determinar centenas de milhares de validações de cada vez.
* Permite validar [países sancionados](../glossario/glossario-aplicacao.md#pais-sancionado).

#### Desvantagens

* Solução mais complexa de implementar.
* Não adequada no caso de precisar de pesquisar pessoas em tempo real.

## Registos e obtenção do risco

O registo dos seus clientes e transações permite-lhe registar toda a a informação necessária para o cumprimento da lei, obtendo ainda um [score de risco](../a-aplicacao/customer-registrations/categorizacao-do-risco-de-pessoas-singulares-coletivas.md) associado a cada registo. Para o fazer, necessita de utilizar pelo menos dois [endpoints de registos](registrations.md). Exemplificando:

1. Adicione o cliente ou transação através do endpoint [`/add_questionnaire`](registrations.md#adicao-de-um-registo). Este endpoint aceita várias propriedades enviadas num objeto `questionnaire_data`, permitindo-lhe popular uma grande parte dos campos disponíveis logo no momento da criação do registo.\
   Esta função irá retornar o `id` do cliente ou transação criado(a).
2. Depois, poderá obter a informação sobre o registo através da função [`get_questionnaires`](registrations.md#obter-registos) iterando ao longo das páginas existentes ou especificando o `id` do registo que acabou de criar.\
   Esta função devolve [informação completa](registrations.md#legenda) sobre o cliente ou transação que está a consultar.
