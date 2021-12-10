# Importação de clientes (v2)

A nova importação de clientes permite-lhe, com facilidade e rapidez, fazer o upload dos seus clientes para a plataforma da PEPData, criando automaticamente um registo para cada cliente.

Para tal, por favor divida a informação a importar em 3 ficheiros distintos:

* Organizações
  * Ficheiro com os seus clientes organizacionais
* Pessoas singulares
  * Ficheiro com os membros da administração e beneficiários efetivos dos seus clientes
* Relações entre pessoas singulares e organizações
  * Ficheiro que mapeia as relações entre as organizações e as pessoas singulares mencionadas anteriormente
  * Este deve ser o último ficheiro a ser importado, só sendo aceite caso os dois restantes já tenham sido inseridos

### Ficheiro das organizações

* Deve conter uma organização por linha
* Deve ser um ficheiro .csv
* Na primeira linha, deve conter a estrutura das suas propriedades
* Propriedades aceites (obrigatórias a negrito):
  * **name**
  * **vat\_number**
  * corporate\_object
  * nace\_codes
  * country\_constitution
  * countries\_operations
  * address\_country
  * address\_postal\_code
  * address
  * address\_door&#x20;
  * address\_district
  * &#x20;address\_city
* Os campos nace\_codes e countries\_operations podem conter múltiplos países, desde que separados por ponto e vírgula ";"

### Ficheiro das pessoas singulares

* Deve conter uma pessoa singular por linha
* Deve ser um ficheiro .csv
* Na primeira linha, deve conter a estrutura das suas propriedades
* Propriedades aceites (obrigatórias a negrito):
  * **name**
  * **vat\_number**
  * email
  * birth\_date
  * nationalities
  * place\_of\_birth
  * address\_type
  * address\_country
  * address\_postal\_code
  * address
  * address\_door&#x20;
  * address\_district
  * &#x20;address\_city
* O campo nationalities pode conter múltiplos países, desde que separados por ponto e vírgula ";"

### Ficheiro das relações entre pessoas singulares e organizações

* Deve conter uma relação por linha
* Deve ser um ficheiro .csv
* Na primeira linha, deve conter a estrutura das suas propriedades
* Propriedades aceites (obrigatórias a negrito):
  * **company\_vat\_number**
  * **individual\_vat\_number**
  * **position\_in\_company**
  * capital\_percentage
  * voting\_rights\_percentage
* O campo position\_in\_company __ pode ter texto livre ou beneficial\_owner, no caso da relação ser enquanto beneficiário efetivo
* Os campos capital\_percentage e voting\_rights\_percentage apenas devem possuir valores caso o campo position\_in\_company __ seja o de beneficial\_owner
* Todos os números de contribuinte, tanto de organizações como de indivíduos, devem já existir no sistema, sendo este o último ficheiro a carregar

