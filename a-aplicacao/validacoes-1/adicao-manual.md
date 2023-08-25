# Adição manual

Na [página de validações](../validacoes/), pode adicionar manualmente uma validação através do botão “+ Adicionar validação”, que lhe dá acesso a uma janela para o fazer.

Nesta janela, terá inicialmente de selecionar o tipo de validação a adicionar, escolhendo o ícone correspondente. Por pré-definição, aparece selecionado o tipo "Pessoa". Para adicionar uma validação de organização, terá de escolher o ícone em forma de edifício.

Após a seleção do tipo de validação, terá à disposição um conjunto de campos onde poderá preencher informação relativa à validação e que dependerão do tipo selecionado:

#### Validação de pessoa:

| Campos                | Notas                                                                                                                                                       |
| --------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Nome                  | Poderá ver [aqui](adicao-manual.md#regras-a-cumprir) as regras a cumprir relativamente aos nomes.                                                           |
| NIF                   | Os números de contribuinte internacionais devem conter o código do país correspondente no início. Ex: FR12345678901 para um número de contribuinte francês. |
| Data de Nascimento    | A data de nascimento deve seguir o formato definido na [página de configurações](../configuracoes/).                                                        |
| País de Nacionalidade | Poderá ver aqui as regras a cumprir relativamente aos [países](adicao-manual.md#regras-a-cumprir).                                                          |
| País de Morada        | Poderá ver aqui as regras a cumprir relativamente aos [países](adicao-manual.md#regras-a-cumprir).                                                          |
| ID                    | Este ID é opcional e pode ter qualquer valor, não podendo, no entanto, ser repetido com outro que já tenha sido introduzido.                                |

#### Validação de organização:

| Campos | Notas                                                                                                                                                       |
| ------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Nome   | Poderá ver [aqui](adicao-manual.md#regras-a-cumprir) as regras a cumprir relativamente aos nomes.                                                           |
| NIF    | Os números de contribuinte internacionais devem conter o código do país correspondente no início. Ex: FR12345678901 para um número de contribuinte francês. |
| País   | Poderá ver aqui as regras a cumprir relativamente aos [países](adicao-manual.md#regras-a-cumprir).                                                          |
| ID     | Este ID é opcional e pode ter qualquer valor, não podendo, no entanto, ser repetido com outro que já tenha sido introduzido.                                |

### Regras a cumprir

{% hint style="info" %}
#### O que devo saber antes de introduzir informação?

**Nome**

* Em caso de validações respeitantes a pessoas, apenas são permitidos, no mínimo, nomes próprios com 2 nomes. No entanto, recomendamos que, no mínimo, sejam introduzidos 2 nomes e a data de nascimento.\
  Esta recomendação existe para que o sistema tenha a capacidade de sugerir resultados relevantes quando pretenda analisar se a pessoa é identificável.
* Todos os [caracteres latinos](https://en.wikipedia.org/wiki/ISO/IEC\_8859-1), sua acentuação e capitalização **são** suportados, não alterando os resultados apresentados no processo de análise. Pode, por isso, introduzir o nome no formato que lhe seja mais conveniente.\
  Exemplificando: "Inês Marçal Romão" será equivalente a introduzir "ines marcal romao".
* Para além dos acima mencionados, apenas são aceites espaços (" "), hífenes ("-") ou apóstrofes (" ' ").
* As [partículas](https://www.irn.mj.pt/IRN/sections/irn/a\_registral/registo-civil/docs-do-civil/dar-o-nome/) existentes no nome de pessoas (como "de", "da", "e", etc.) não alteram os resultados apresentados no processo de análise.\
  Exemplificando: "Rui Miguel do Rio" será equivalente a introduzir "Rui Miguel Rio".
* As validações de pessoas suportam abreviaturas no seu nome. No entanto, estas não poderão ser procedidas com um ponto.\
  Exemplificando: "Rui M Rio" poderá ter como resultado o nome "Rui Miguel Rio".
* Todos os pontos anteriores foram implementados de forma a tornar o processo o mais robusto possível. No entanto, recomendamos que tente introduzir nomes o mais próximo do original quanto possível.

**País**

* Este campo é analisado de forma independente, sendo apenas verificado se o país introduzido (país de nacionalidade, no caso de pessoas, ou país, no caso de organizações) se encontra [sancionado](../../glossario/glossario-aplicacao.md#pais-sancionado). Deste modo, este campo poderá ter significados distintos como: origem dos fundos do cliente, local de residência fiscal ou qualquer outro que considere relevante.\
  Nota: caso o país associado a uma [validação](../../glossario/glossario-aplicacao.md#validacao) se encontre [sancionado](../../glossario/glossario-aplicacao.md#pais-sancionado), a [validação](../../glossario/glossario-aplicacao.md#validacao) irá herdar esta [classificação](../../glossario/glossario-aplicacao.md#classificacao), independentemente de corresponder a uma [pessoa identificável](../../glossario/glossario-aplicacao.md#pessoa-identificavel). Uma [validação](../../glossario/glossario-aplicacao.md#validacao) pode ter múltiplas classificações distintas.
{% endhint %}

Após preenchimento da informação, existem duas opções, que são acedidas clicando nos botões com o mesmo nome:

#### Adicionar e analisar

Adiciona a [validação](../../glossario/glossario-aplicacao.md#sancionado) ao sistema e abre imediatamente a sua janela de análise manual.

#### Adicionar

Adiciona a [validação](../../glossario/glossario-aplicacao.md#validacao) ao sistema e atualiza a grelha principal.
