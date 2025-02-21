# Categorização do risco

## Metodologia

O modelo de risco criado pela PEPData foi desenvolvido de forma a ser flexível, mantendo um grau de simplicidade que o permite ser facilmente compreendido.\
Este é composto por 3 categorias distintas de risco com os seguintes limites (em pontos):

* Baixo: \[0 - 1\[
* Médio: \[1 - 2\[
* Alto: 2+

Cada pessoa ou organização é enquadrada nas várias categorias de risco tendo em consideração os seguintes critérios:

### Pessoas

* Existência de suspeição
  * Caso suspeite da documentação apresentada ou da pessoa em si
    * Aumenta o risco em 2 pontos.
* Países sancionados
  * Caso a pessoa tenha naturalidade, nacionalidade ou residência em países sancionados internacionalmente
    * Aumenta o risco em 2 pontos.
* Paraísos fiscais
  * Caso a pessoa tenha residência num país considerado como tendo um "regime de tributação privilegiada" pela lei portuguesa
    * Aumenta o risco em 1 ponto.
* Classificação enquanto [pessoa identificável](../../../glossario/glossario-aplicacao.md#pessoa-identificavel)
  * Aumenta o risco em 1 ponto.
* Classificação enquanto [pessoa sancionada](../../../glossario/glossario-aplicacao.md#sancionado)
  * Aumenta o risco em 2 pontos.

### Organizações

* Existência de suspeição
  * Caso suspeite da documentação apresentada ou da organização em si
    * Aumenta o risco em 2 pontos.
* Países sancionados
  * Caso o país de constituição, o país de morada da sede social ou o(s) país(es) de proveniência dos negócios seja(m) sancionado(s)
    * Aumenta o risco em 2 pontos.
* Paraísos fiscais
  * Caso o país de constituição, o país de morada da sede social ou o(s) país(es) de proveniência dos negócios seja(m) considerado(s) como tendo um "regime de tributação privilegiada" pela lei portuguesa
    * Aumenta o risco em 1 ponto.
* Outros critérios geográficos
  * Caso não tenha sede em território nacional
    * Aumenta o risco em 1 ponto.
* Classificação da atividade económica
  * Caso algum dos CAEs da organização seja considerado como risco elevado
    * Aumenta o risco em 1 ponto.
* Classificação enquanto [organização sancionada](../../../glossario/glossario-aplicacao.md#sancionado)
  * Aumenta o risco em 2 pontos.
* Representação da organização
  * Caso algum dos representantes esteja classificado com nível de risco médio ou alto
* Titulares de órgãos de Administração/Gestão ou equivalente
  * Caso algum dos titulares esteja classificado com nível de risco médio ou alto
* Titulares de participações no capital/direitos de voto
  * Caso algum dos titulares esteja classificado com nível de risco médio ou alto
* Beneficiários efetivos
  * Caso algum dos beneficiários efetivos esteja classificado com nível de risco médio ou alto

#### Ajuste do fator de risco mediante a percentagem de capital ou direitos de voto

A propagação do risco de um questionário relacionado é ajustada de acordo com a sua percentagem de capital/direitos de voto na organização. Por exemplo:

* Empresa A
  * Beneficiário efetivo A (20% percentagem de capital, 30% direitos de voto) - Risco 1
  * Beneficiário efetivo B (80% percentagem de capital, 70% direitos de voto) - Risco 3

Para obtenção da percentagem a usar para cada questionário relacionado é calculado o **máximo entre a percentagem de capital e a percentagem dos direitos de voto e caso essa percentagem seja superior a 50%, o risco do questionário será contado na totalidade.**

Para o exemplo acima apresentado o risco contabilizado final da secção será de 3, ou seja, o **máximo entre 0.3 (30% do risco do Beneficiário efetivo A) e 3 (risco total do Beneficiário efetivo B)**.

{% hint style="warning" %}
Poderão existir relações cíclicas entre organizações através dos Titulares de participações no capital/direitos de voto.

Os intervenientes em relações cíclicas estão identificados no questionário com o símbolo (![](<../../../.gitbook/assets/triangle-exclamation-solid (2).svg>)) e o valor do risco dos mesmos não influencia o risco da organização em análise.
{% endhint %}

Nota: o nosso algoritmo de cálculo de risco está em constante desenvolvimento. Caso tenha alguma proposta de melhoria ou especificidade da sua área profissional não hesite em [contactar-nos](../../../outros/contactos.md).
