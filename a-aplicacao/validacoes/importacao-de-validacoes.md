# Importação de validações

Na [página de validações](./), pode fazer a importação automática de validações através do botão “Importar validações”, que lhe dá acesso a um explorador que permite escolher o ficheiro que contém as [validações](../../glossario/glossario-aplicacao.md#validacao) a adicionar.

Antes de escolher o ficheiro de importação, terá de escolher o tipo de validações a importar, selecionando o ícone correspondente:

<figure><img src="../../.gitbook/assets/Untitled-1.jpg" alt=""><figcaption><p>Seleção do tipo de validações a importar</p></figcaption></figure>

Por predefinição, aparece selecionado o tipo 'Pessoas'. Para importar validações de organizações, deverá selecionar o ícone em forma de edifício e para importar relações, deverá selecionar o ícone em forma de diagrama.

Após o upload do ficheiro ter sido concluído, todas as novas [validações](../../glossario/glossario-aplicacao.md#validacao) irão aparecer na [página de validações](./). Se tiver importado relações, todas elas serão automaticamente associadas às [validações](./) correspondentes.

De forma a que o ficheiro possa ser interpretado corretamente pela aplicação, este deverá seguir um conjunto de especificações, descritas abaixo.

## Detalhes dos ficheiros a importar

### Detalhes Gerais

* A primeira linha deve conter o nome das colunas que representam a informação a importar
* Extensão .txt ou .csv
* Limitado a 500.000 linhas por cada importação

### Ficheiro das pessoas

* Deve conter uma pessoa por linha
* Propriedades aceites (obrigatórias a negrito):

| Campos           | Notas                                                                                                                                                       |
| ---------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------- |
| vat\_number      | Os números de contribuinte internacionais devem conter o código do país correspondente no início. Ex: FR12345678901 para um número de contribuinte francês. |
| **name**         | Poderá ver [aqui](importacao-de-validacoes.md#regras-a-cumprir) as regras a cumprir relativamente aos nomes.                                                |
| birth\_date      | A data de nascimento deve seguir o formato dd-mm-yyyy, dd/mm/yyyy, yyyy-mm-dd ou yyyy/mm/dd.                                                                |
| country          | Poderá ver [aqui](importacao-de-validacoes.md#regras-a-cumprir) as regras a cumprir relativamente aos países.                                               |
| country\_address | Poderá ver [aqui](importacao-de-validacoes.md#regras-a-cumprir) as regras a cumprir relativamente aos países.                                               |
| id\_custom       | Identificador do cliente utilizado pela sua organização. Tem de ser único.                                                                                  |
| unidentifiable   | 1 ou 0, caso seja não identificável.                                                                                                                        |

#### Ficheiro exemplo

{% file src="../../.gitbook/assets/validação individual (2).txt" %}

### Ficheiro das organizações

* Deve conter uma organização por linha
* Propriedades aceites (obrigatórias a negrito):

| Campos         | Notas                                                                                                                                                       |
| -------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------- |
| vat\_number    | Os números de contribuinte internacionais devem conter o código do país correspondente no início. Ex: FR12345678901 para um número de contribuinte francês. |
| **name**       | Poderá ver [aqui](importacao-de-validacoes.md#regras-a-cumprir) a regras a cumprir relativamente aos nomes.                                                 |
| country        | Poderá ver [aqui](importacao-de-validacoes.md#regras-a-cumprir) as regras a cumprir relativamente aos países.                                               |
| id\_custom     | Identificador do cliente utilizado pela sua organização. Tem de ser único.                                                                                  |
| unidentifiable | 1 ou 0, caso seja não identificável.                                                                                                                        |

#### Ficheiro exemplo

{% file src="../../.gitbook/assets/validação organização.txt" %}

### Ficheiro das relações

* Deve conter uma relação por linha
* Propriedades aceites (obrigatórias a negrito):



| Campos                         | Notas                                                                                                                     |
| ------------------------------ | ------------------------------------------------------------------------------------------------------------------------- |
| **organization\_vat\_number**  | NIPC da validação de organização onde se vai inserir a relação. Esta validação de organização já deve existir no sistema. |
| **vat\_number**                | NIF da relação a ser inserida. Este indivíduo/organização já deve existir no sistema.                                     |
| **position\_in\_organization** | Tipo da relação a inserir. Pode ser: representative, manager, owner ou beneficial\_owner.                                 |

#### Ficheiro exemplo

{% file src="../../.gitbook/assets/relação validações.txt" %}

### Regras a cumprir

{% hint style="info" %}
#### Quais as especificações do ficheiro de upload?

* Uma [validação](../../glossario/glossario-aplicacao.md#validacao)/[relação](../../glossario/glossario-aplicacao.md#relacao) por cada linha.
* Uma [validação](../../glossario/glossario-aplicacao.md#validacao)/[relação](../../glossario/glossario-aplicacao.md#relacao) deve seguir a ordem dos campos definidos no cabeçalho.
* A codificação do ficheiro deve ser utf-8 ou ANSI.
{% endhint %}

{% hint style="info" %}
#### O que devo saber antes de introduzir informação?

**Nome**

* Em caso de validações respeitantes a pessoas, apenas são permitidos, no mínimo, nomes próprios com 2 nomes e data de nascimento. Caso não tenha informação relativa à data de nascimento, terá de introduzir, no mínimo, 3 nomes.\
  Estes requisitos mínimos existem de forma a garantir que o sistema tenha a capacidade de sugerir resultados relevantes quando pretenda analisar se a pessoa é [identificável](../../glossario/glossario-aplicacao.md#pessoa-identificavel).
* Todos os [caracteres latinos](https://en.wikipedia.org/wiki/ISO/IEC\_8859-1), sua acentuação e capitalização **são** suportados, não alterando os resultados apresentados no processo de análise. Pode, por isso, introduzir o nome no formato que lhe seja mais conveniente.\
  Exemplificando: "Inês Marçal Romão" será equivalente a introduzir "ines marcal romao".
* Para além dos acima mencionados, apenas são aceites espaços (" "), hífenes ("-") ou apóstrofes (" ' ").
* As [partículas](https://www.irn.mj.pt/IRN/sections/irn/a\_registral/registo-civil/docs-do-civil/dar-o-nome/) existentes no nome de pessoas, (como "de", "da", "e", etc.) não alteram os resultados apresentados no processo de análise.\
  Exemplificando: "Rui Miguel do Rio" será equivalente a introduzir "Rui Miguel Rio".
* As validações de pessoas suportam abreviaturas no seu nome. No entanto, estas não poderão ser procedidas com um ponto.\
  Exemplificando: "Rui M Rio" poderá ter como resultado o nome "Rui Miguel Rio".
* Todos os pontos anteriores foram implementados de forma a tornar o processo mais robusto possível. No entanto, recomendamos que tente introduzir nomes o mais próximo do original quanto possível.

**País**

* Este campo é analisado de forma independente, sendo apenas verificado se o país introduzido (país de nacionalidade, no caso de pessoas, ou país, no caso de organizações) se encontra [sancionado](../../glossario/glossario-aplicacao.md#pais-sancionado). Deste modo, este campo poderá ter significados distintos como: origem dos fundos do cliente, local de residência fiscal ou qualquer outro que considere relevante.
* Existem múltiplas formas distintas de se escrever o nome de cada país. A aplicação da PEPData suporta qualquer valor [ISO 3166](https://en.wikipedia.org/wiki/ISO\_3166), nome comum ou nome oficial de cada país.\
  Nota: caso o país associado a uma [validação](../../glossario/glossario-aplicacao.md#validacao) se encontre sancionado, a [validação](../../glossario/glossario-aplicacao.md#validacao) irá herdar esta classificação, independentemente de corresponder a uma [pessoa identificável](../../glossario/glossario-aplicacao.md#pessoa-identificavel). Uma [validação](../../glossario/glossario-aplicacao.md#validacao) pode ter múltiplas [classificações](../../glossario/glossario-aplicacao.md#classificacao) distintas.
{% endhint %}

{% hint style="info" %}
#### Não estou a conseguir fazer o upload do ficheiro, o que posso fazer?

* Verifique se o nome, data de nascimento e campos relativos a países não estão delimitados por ' ou ". Estes valores não devem estar delimitados.
* Verifique se, abrindo o ficheiro, não vê nenhum caracter como "" em vez de caracteres com acentos ou "ç". Caso tal aconteça, existe um problema de codificação que pode tentar resolver seguindo o [aqui ](importacao-de-validacoes.md#codificacao-incorreta-do-ficheiro)descrito.
* Caso os pontos anteriores não se verifiquem e continue a receber uma mensagem de erro cada vez que tenta realizar um upload, pode existir um problema de codificação que pode tentar resolver seguindo o [aqui ](importacao-de-validacoes.md#codificacao-incorreta-do-ficheiro)descrito.
* Caso nenhum dos exemplos anteriores se verifique, por favor contacte a PEPData.
{% endhint %}

## Assistente de correção

Caso ocorra um problema com os dados a introduzir, irá aparecer um assistente de correção que irá identificar os erros encontrados no ficheiro. O assistente de correção segue a seguinte lógica sequencial:

1. Validação da linha de cabeçalho;
2. Validação dos dados introduzidos:
   * name;
   * birth\_date (caso se trate de validações de pessoas);
   * country\_nationality (caso se trate de validações de pessoas);
   * country\_address (caso se trate de validações de pessoas);
   * country (caso se trate de validações de organizações);
   * vat\_number
3. Verificação da existência de duplicados: caso já tenha adicionado uma determinada validação ou relação no passado, os dados a introduzir serão considerados como duplicados. O utilizador poderá depois optar por ignorar este tipo de erro.

{% hint style="info" %}
Nota: Por limitação de espaço, caso exista uma elevada quantidade de erros ou de duplicados, estes podem não ser todos mostrados no assistente de correção. Terá de efetuar a sua correção e refazer o upload para ver os erros restantes.
{% endhint %}

## Soluções para possíveis problemas

### Codificação incorreta do ficheiro

Um [ficheiro de texto](https://pt.wikipedia.org/wiki/Arquivo\_de\_texto) contém informação que apenas consegue ser corretamente interpretada caso se saiba a sua codificação. Apenas deste modo um computador consegue "compreender" o que nele se encontra escrito, podendo distinguir cada um dos caracteres.

Infelizmente, não existe uma codificação universal que seja utilizada em todos os computadores, o que poderá levar a dificuldades na interpretação de alguns ficheiros de texto, com especial relevância nos caracteres com acentos. Caso um computador utilize uma codificação que não corresponde à do ficheiro, poderá interpretar o caracter "é" como "", por exemplo, não conseguindo compreender o seu significado.

Embora o sistema da PEPData tente determinar a codificação do ficheiro carregado, nem sempre este processo é infalível, pelo que o problema descrito poderá ocorrer. Caso tal aconteça, irá receber uma mensagem de erro que o informa que apenas um determinado número de caracteres é reconhecido pelo sistema sempre que tente realizar o upload do mesmo ficheiro.

Neste caso, sugerimos as seguintes soluções:

**Bloco de Notas/Notepad do Windows**

1. Abrir o ficheiro em questão.
2. Clicar em Ficheiro/File -> Guardar Como... /Save As...
3. Alterar Codificação/Encoding de UTF-8 para ANSI ou de ANSI para UTF-8. Esta opção encontra-se à esquerda do botão Guardar/Save.
4. Guardar.
5. Voltar a fazer upload do ficheiro na plataforma da PEPData.

[**Notepad++**](https://notepad-plus-plus.org/)

1. Abrir o ficheiro em questão.
2. Codificação/Encoding -> Converter para ANSI ou UTF-8, dependendo da codificação atual.
3. Guardar.
4. Voltar a fazer upload do ficheiro na plataforma da PEPData.
