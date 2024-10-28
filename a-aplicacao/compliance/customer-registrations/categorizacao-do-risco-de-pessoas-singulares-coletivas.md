# Categorização do risco

## Metodologia

O modelo de risco criado pela PEPData foi desenvolvido de forma a ser flexível, mantendo um grau de simplicidade que o permite ser facilmente compreendido.\
Este é composto por 3 categorias distintas de risco: baixo, médio e alto. Cada pessoa ou organização é enquadrada nas várias categorias de risco tendo em consideração os seguintes critérios:

### Pessoas

* Existência de suspeição
  * Caso suspeite da documentação apresentada ou da pessoa em si
* Países sancionados
  * Caso a pessoa tenha naturalidade, nacionalidade ou residência em países sancionados internacionalmente
* Paraísos fiscais
  * Caso a pessoa tenha residência num país considerado como tendo um "regime de tributação privilegiada" pela lei portuguesa
* Classificação enquanto [pessoa identificável](../../../glossario/glossario-aplicacao.md#pessoa-identificavel)
* Classificação enquanto [pessoa sancionada](../../../glossario/glossario-aplicacao.md#sancionado)

### Organizações

* Existência de suspeição
  * Caso suspeite da documentação apresentada ou da organização em si
* Países sancionados
  * Caso o país de constituição, o país de morada da sede social ou o(s) país(es) de proveniência dos negócios seja(m) sancionado(s)
* Paraísos fiscais
  * Caso o país de constituição, o país de morada da sede social ou o(s) país(es) de proveniência dos negócios seja(m) considerado(s) como tendo um "regime de tributação privilegiada" pela lei portuguesa
* Outros critérios geográficos
  * Caso não tenha sede em território nacional
* Classificação da atividade económica
  * Caso algum dos CAEs da organização seja considerado como risco elevado
* Classificação enquanto [organização sancionada](../../../glossario/glossario-aplicacao.md#sancionado)
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

Para obtenção da percentagem a usar para cada relação é feito o **Máximo entre a percentagem de capital e a percentagem dos direitos de voto e caso essa percentagem seja superior a 50%, o risco do questionário será contado na totalidade.**

Para o exemplo acima apresentado o risco contabilizado será de 0.2 (20% do risco do Beneficiário efetivo A) + 3 (risco total do Beneficiário efetivo B)&#x20;

{% hint style="warning" %}
Poderão existir relações cíclicas entre organizações através dos Titulares de participações no capital/direitos de voto.

Os intervenientes em relações cíclicas estão identificados no questionário com o símbolo (![](<../../../.gitbook/assets/triangle-exclamation-solid (2).svg>)) e o valor do risco dos mesmos não influencia o risco da organização em análise.
{% endhint %}

Nota: o nosso algoritmo de cálculo de risco está em constante desenvolvimento. Caso tenha alguma proposta de melhoria ou especificidade da sua área profissional não hesite em [contactar-nos](../../../outros/contactos.md).
