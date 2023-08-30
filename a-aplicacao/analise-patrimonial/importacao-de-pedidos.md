# Importação de pedidos

Na página de [análise patrimonial](./), pode fazer a importação automática de pedidos através do botão “Importar pedidos”.

Após o upload do ficheiro ter sido concluído, todos os novos pedidos irão aparecer na [página](./).

De forma a que o ficheiro possa ser interpretado corretamente pela aplicação, este deverá seguir um conjunto de especificações, descritas abaixo.

## Detalhes dos ficheiros a importar

### Detalhes Gerais

* A primeira linha deve conter o nome das colunas que representam a informação a importar
* Extensão .txt ou .csv
* Limitado a 500.000 linhas por cada importação
* Deve conter uma entidade por linha
* Cada propriedade deve ser separada por ponto e vírgula
* Propriedades aceites (obrigatórias a negrito):

| Campos          | Notas                                                                                                                                                                                                      |
| --------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **name**        | Poderá ver [aqui](importacao-de-pedidos.md#regras-a-cumprir) as regras a cumprir relativamente aos nomes.                                                                                                  |
| **vat\_number** | Apenas são aceites números de contribuinte portugueses.                                                                                                                                                    |
| notes           | <p>Campo de texto livre onde pode inserir informações extra necessárias.<br><strong>Nota:</strong> não introduza ponto e vírgula nas suas notas de forma a não interferir com a importação do ficheiro</p> |

#### Ficheiro exemplo

{% file src="../../.gitbook/assets/importação pedidos (1).txt" %}

### Regras a cumprir

{% hint style="info" %}
#### Quais as especificações do ficheiro de upload?

* Um pedido por linha.
* Um pedido deve seguir a ordem dos campos definidos no cabeçalho.
* Os campos devem ser separados por ponto e vírgula.
* A codificação do ficheiro deve ser utf-8 ou ANSI.
{% endhint %}

{% hint style="info" %}
#### Não estou a conseguir fazer o upload do ficheiro, o que posso fazer?

* Verifique se os campos não estão delimitados por ' ou ". Estes valores não devem estar delimitados.
* Verifique se, abrindo o ficheiro, não vê nenhum caracter como "" em vez de caracteres com acentos ou "ç". Caso tal aconteça, existe um problema de codificação que pode tentar resolver seguindo o [aqui ](importacao-de-pedidos.md#codificacao-incorreta-do-ficheiro)descrito.
* Caso os pontos anteriores não se verifiquem e continue a receber uma mensagem de erro cada vez que tenta realizar um upload, pode existir um problema de codificação que pode tentar resolver seguindo o processo [aqui ](importacao-de-pedidos.md#codificacao-incorreta-do-ficheiro)descrito.
* Caso nenhum dos exemplos anteriores se verifique, por favor contacte a PEPData.
{% endhint %}

## Assistente de correção

Caso ocorra um problema com os dados a introduzir, irá aparecer um assistente de correção que irá identificar os erros encontrados no ficheiro. O assistente de correção segue a seguinte lógica sequencial:

1. Validação da linha de cabeçalho;
2. Validação dos dados introduzidos:
   * name;
   * vat\_number;
   * notes.

{% hint style="info" %}
Nota: Por limitação de espaço, caso exista uma elevada quantidade de erros, estes podem não ser todos mostrados no assistente de correção. Terá de efetuar a sua correção e refazer o upload para ver os erros restantes.
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
