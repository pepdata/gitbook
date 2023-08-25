# Adição manual

Na página de [análise patrimonial](./), pode adicionar manualmente um pedido através do botão “+ Adicionar pedido”, que lhe dá acesso a uma janela para o fazer.

Nesta janela terá à disposição um conjunto de campos onde poderá preencher a informação relativa ao pedido:

| Campos             | Notas                                                                                                                                                       |
| ------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Nome**           | Poderá ver [aqui](adicao-manual.md#regras-a-cumprir) as regras a cumprir relativamente aos nomes.                                                           |
| **NIF/NIPC**       | Os números de contribuinte internacionais devem conter o código do país correspondente no início. Ex: FR12345678901 para um número de contribuinte francês. |
| Data de Nascimento | A data de nascimento deve seguir o formato definido na [página de configurações](../configuracoes/).                                                        |
| País               | Poderá ver aqui as regras a cumprir relativamente aos [países](adicao-manual.md#regras-a-cumprir).                                                          |
| Notas              | Campo de texto livre onde pode inserir informações extra necessárias.                                                                                       |

### Regras a cumprir

{% hint style="info" %}
#### O que devo saber antes de introduzir informação?

**Nome**

* Todos os [caracteres latinos](https://en.wikipedia.org/wiki/ISO/IEC\_8859-1), sua acentuação e capitalização **são** suportados, não alterando os resultados apresentados no processo de análise. Pode, por isso, introduzir o nome no formato que lhe seja mais conveniente.\
  Exemplificando: "Inês Marçal Romão" será equivalente a introduzir "ines marcal romao".

**País**

* Este campo é analisado de forma independente, sendo apenas verificado se o país introduzido (país de nacionalidade, no caso de pessoas, ou país, no caso de organizações) se encontra [sancionado](../../glossario/glossario-aplicacao.md#pais-sancionado). Deste modo, este campo poderá ter significados distintos como: origem dos fundos do cliente, local de residência fiscal ou qualquer outro que considere relevante.\
  Nota: caso o país associado a uma [validação](../../glossario/glossario-aplicacao.md#validacao) se encontre [sancionado](../../glossario/glossario-aplicacao.md#pais-sancionado), a [validação](../../glossario/glossario-aplicacao.md#validacao) irá herdar esta [classificação](../../glossario/glossario-aplicacao.md#classificacao), independentemente de corresponder a uma [pessoa identificável](../../glossario/glossario-aplicacao.md#pessoa-identificavel). Uma [validação](../../glossario/glossario-aplicacao.md#validacao) pode ter múltiplas classificações distintas.
{% endhint %}

