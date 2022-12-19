# Relatório CMVM para Auditores

A Plataforma da PEPData pode apoiá-lo na preparação e geração do relatório para a CMVM, que é entregue até ao dia 28 de Fevereiro de cada ano, conforme o artigo 19 (Deveres de Reporte de Auditores) do [Regulamento 2/2020 da CMVM](https://dre.pt/home/-/dre/130325827/details/maximized).

De forma a reforçar o escrutínio e transparência, publicamos a metodologia utilizada na elaboração do relatório, em conjunto com as instruções que precisa de seguir para a sua correta geração.

{% hint style="warning" %}
O Relatório CMVM já se encontra disponível para aquisição. Consulte a página Relatório CMVM 2022.
{% endhint %}

## Glossário do relatório CMVM para auditores

* Pessoas Associadas
  * Beneficiários efetivos, sócios ou gestores de topo
* País de alto risco
  * País com as características descritas no n.º 3 do Anexo III da [Lei n.º 83/2017](https://dre.pt/home/-/dre/108021178/details/maximized)

## Instruções de preenchimento

1. Aceder à página "Questionário CMVM"
2. Preencher o questionário elaborado pela PEPData
3. Elaborar e efetuar o carregamento de 3 ficheiros, cada um com as seguintes propriedades:
   1. **Pessoas Associadas e Colaboradores da SROC (Pessoas singulares)**&#x20;
      1. Nome completo&#x20;
      2. Data de nascimento (opcional)
      3. Nacionalidade: País &#x20;
   2. **Clientes (Pessoas coletivas)**&#x20;
      1. Nome empresa (sem vírgulas)
      2. NIPC da empresa&#x20;
      3. Novo cliente: coloque **1** caso o cliente tenha sido angariado no ano de referência ou **0** caso contrário
      4. País da sede da empresa&#x20;
      5. CAE principal
   3. **Pessoas Associadas aos Clientes (Pessoas singulares)**&#x20;
      1. Nome completo&#x20;
      2. Data de nascimento (opcional)
      3. País de residência fiscal&#x20;
      4. NIPC da empresa Cliente: este NIPC deverá coincidir com os inseridos no ficheiro Clientes (Pessoas coletivas)

### Características gerais dos ficheiros a carregar

* Uma pessoa singular/coletiva por linha
* Extensão .csv ou .txt&#x20;
* Limitado a 700.000 linhas

### Ficheiros exemplificativos

{% file src="../.gitbook/assets/pessoas-associadas-e-colaboradores-da-sroc-pessoas-singulares-.csv" %}

{% file src="../.gitbook/assets/clientes-pessoas-coletivas-.csv" %}

{% file src="../.gitbook/assets/pessoas-associadas-aos-clientes-pessoas-singulares-.csv" %}

### Perguntas frequentes

{% hint style="info" %}
### Como gerar os ficheiros em formato .csv?

Caso utilize um ficheiro excel, poderá gerar o seu ficheiro .csv através da opção "Guardar como...", escolhendo .csv como o tipo de ficheiro.

**Atenção**: recomendamos que mantenha sempre uma cópia do ficheiro excel em separado, caso existam problemas na conversão para .csv
{% endhint %}

{% hint style="info" %}
### O que devo saber antes de introduzir informação?

#### Nome completo

* No mínimo, apenas são permitidos nomes de pessoas com pelo menos 2 nomes e data de nascimento. Caso não tenha informação relativa à data de nascimento, terá de introduzir, no mínimo, 3 nomes. \
  Estes requisitos mínimos existem de forma a garantir que o sistema tem a capacidade de gerar resultados relevantes quando pretenda analisar se a pessoa é identificável.&#x20;
* Todos os [caracteres latinos](https://en.wikipedia.org/wiki/ISO/IEC\_8859-1), sua acentuação e capitalização **são** suportados, não alterando os resultados apresentados no processo de análise. Pode, por isso, introduzir o nome no formato que lhe seja mais conveniente. \
  Exemplificando:  "Inês Marçal Romão" será equivalente a introduzir "ines marcal romao".
* Para além dos acima mencionados,  apenas são aceites espaços (" "), hífenes ("-") ou apóstrofes (" ' ").  &#x20;
* As [partículas](https://www.irn.mj.pt/IRN/sections/irn/a\_registral/registo-civil/docs-do-civil/dar-o-nome/) existentes no nome (como "de", "da", "e", etc.) não alteram os resultados apresentados no processo de análise. \
  Exemplificando:  "Rui Miguel do Rio" será equivalente a introduzir "Rui Miguel Rio".
* Abreviaturas são suportadas. No entanto, estas não poderão ser procedidas com um ponto.\
  Exemplificando:  "Rui M Rio" poderá ter como resultado o nome "Rui Miguel Rio".
* Todos os pontos anteriores foram implementados de forma a tornar o processo o mais robusto possível. No entanto, recomendamos que tente introduzir nomes o mais próximo do original quanto possível.

#### NIPC

* NIPCs portugueses devem ser colocados de forma numérica. Ex: 537592962.&#x20;
* NIPCs estrangeiros devem ser colocados com o prefixo de dois dígitos. Ex: FR12345678901.
{% endhint %}

## Metodologia

### Categorização de risco

O modelo de risco criado pela PEPData foi desenvolvido de forma a ser flexível, mantendo um grau de simplicidade que o permite ser facilmente compreendido. \
Este é composto por 3 categorias distintas de risco: baixo, médio baixo a médio alto e alto. Cada pessoa coletiva é enquadrada nas várias categorias de risco de acordo com os seguintes critérios:

* Risco alto:&#x20;
  * Cliente [sancionado](https://app.gitbook.com/@afbpinheiro/s/pepdata/\~/drafts/-MVHgRcUttIZiR7V2b0D/glossario/glossario-aplicacao#sancionado)
  * Existência de qualquer pessoa associada ao cliente que seja [sancionada](../glossario/glossario-aplicacao.md#sancionado)
  * Existência de sede localizada em país de alto risco
  * Existência de qualquer pessoa associada ao cliente com residência em país de alto risco
* Risco médio baixo a médio alto
  * Inexistência de pessoas associadas (no ficheiro de Representantes de Clientes)
  * Existência de pessoas associadas [identificáveis](../glossario/glossario-aplicacao.md#pessoa-identificavel)
  * Qualquer pessoa coletiva que não se enquadre nas restantes categorias
* Risco baixo
  * Inexistência de sede localizada em país de alto risco
  * Existência de pelo menos uma pessoa associada (no ficheiro de Representantes de Clientes)
  * Inexistência de pessoas associadas [identificáveis](../glossario/glossario-aplicacao.md#pessoa-identificavel) ou [sancionadas](../glossario/glossario-aplicacao.md#sancionado)

Caso a aplicação dos critérios enquadre a pessoa coletiva em múltiplas categorias, esta é classificada com a categoria de risco mais elevada entre as categorias enquadradas.

### Identificação de pessoas singulares

A identificação de pessoas singulares é efetuada com base num método de identificação que recorre à base de dados da PEPData, ao algoritmo de comparação de nomes de pessoas da PEPData e à utilização de um threshold de classificação.&#x20;

#### Base de dados

A base de dados é propriedade exclusiva da PEPData, sendo atualizada diariamente.\
Esta base de dados possui as seguintes características:

* \~130.000 [pessoas identificáveis](../glossario/glossario-aplicacao.md#pessoa-identificavel) portuguesas ([pessoas politicamente expostas](../glossario/glossario-legal-portugal.md#pessoa-politicamente-exposta), [membros próximos da família](../glossario/glossario-legal-portugal.md#membro-proximo-da-familia), [pessoas reconhecidas como estreitamente associadas](../glossario/glossario-legal-portugal.md#pessoa-reconhecida-como-estreitamente-associada) ou [titulares de outro cargo político ou público](../glossario/glossario-legal-portugal.md#titular-de-outros-cargos-politicos-ou-publicos))
* \~6.000 [pessoas politicamente expostas](../glossario/glossario-legal-portugal.md#pessoa-politicamente-exposta) internacionais

Estão agregadas à base de dados da PEPData as seguintes listas de sanções internacionais, que são sincronizadas com periodicidade diária:

* United Nations Security Council Consolidated List
* EU Financial Sanctions Database
* OFAC Specially Designated Nationals and Blocked Persons List
* HM Treasury Financial Sanctions Targets

#### Algoritmo de comparação de nomes de pessoas

O algoritmo utilizado na comparação de nomes é propriedade exclusiva da PEPData.\
Este permite comparar dois nomes, computando um [grau de semelhança](../glossario/glossario-aplicacao.md#grau-de-semelhanca) que é utilizado para aferir a semelhança entre os nomes inseridos pelo cliente e os nomes existentes na base de dados.

#### Threshold de classificação

O threshold de classificação é o valor acima do qual se considera um grau de semelhança como elevado.\
A PEPData definiu o valor de 90% como threshold de classificação, com o intuito de obrigar que exista um razoável grau de certeza de que os nomes comparados correspondem, de facto, à mesma pessoa.

#### Método de identificação&#x20;

Caso o nome inserido pelo cliente possua um grau de semelhança ≥ a 90% com um nome constante na base de dados da PEPData, este é considerado como tendo sido identificado. Para tal, as datas de nascimento de ambos têm também de ser compatíveis.&#x20;
