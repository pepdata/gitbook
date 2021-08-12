# Categorização do risco de pessoas singulares/coletivas

## Metodologia

O modelo de risco criado pela PEPData foi desenvolvido de forma a ser flexível, mantendo um grau de simplicidade que o permite ser facilmente compreendido.   
Este é composto por 3 categorias distintas de risco: baixo, médio e alto. Cada pessoa singular ou coletiva é enquadrada nas várias categorias de risco tendo em consideração os seguintes critérios:

### Pessoas singulares

* Existência de suspeição 
  * Caso suspeite da documentação apresentada ou da pessoa singular em si 
* Países sancionados 
  * Caso a pessoa singular tenha naturalidade, nacionalidade ou residência em países sancionados internacionalmente
* Paraísos fiscais
  * Caso a pessoa singular tenha residência num país considerado como tendo um "regime de tributação privilegiada" pela lei portuguesa
* Classificação enquanto [pessoa identificável](../../glossario/glossario-aplicacao.md#pessoa-identificavel)
* Classificação enquanto [pessoa sancionada](../../glossario/glossario-aplicacao.md#sancionado)

### Pessoas coletivas

* Existência de suspeição 
  * Caso suspeite da documentação apresentada ou da pessoa coletiva em si 
* Países sancionados 
  * Caso o país de constituição ou país onde realiza a maioria das operações seja sancionado
* Paraísos fiscais
  * Caso o país de constituição ou país onde realiza a maioria das operações seja considerado como tendo um "regime de tributação privilegiada" pela lei portuguesa
* Outros critérios geográficos
  * Caso não tenha sede em território nacional
* Classificação da atividade económica
  * Caso algum dos CAEs da pessoa coletiva seja considerado como risco elevado
* Classificação enquanto [pessoa sancionada](../../glossario/glossario-aplicacao.md#sancionado)

Nota: o nosso algoritmo de cálculo de risco está em constante desenvolvimento. Caso tenha alguma proposta de melhoria ou especificidade da sua área profissional não hesite em [contactar-nos](../../outros/contactos.md).

