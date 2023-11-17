# Categorização do risco da transação

## Metodologia

O modelo de risco criado pela PEPData foi desenvolvido de forma a ser flexível, mantendo um grau de simplicidade que o permite ser facilmente compreendido.\
Este é composto por 3 categorias distintas de risco com os seguintes thresholds (em pontos): \
&#x20;\- Baixo: \[0, 1\[\
&#x20;\- Médio: \[1, 2\[\
&#x20;\- Alto: 2+

Cada transação é enquadrada nas várias categorias de risco tendo em consideração os seguintes critérios:

* Existência de suspeição:
  * Caso suspeite da documentação apresentada ou da transação em si.
    * Aumenta o risco em 2 pontos.
* Montante:
  * Caso o montante seja superior a 15.000€
    * Aumenta o risco em 1 ponto.
* Combinação entre Método de pagamento e Montante
  * Caso o método de pagamento seja numerário e o montante seja superior a 3000€
    * Aumenta o risco em 1 ponto.

Nota: o nosso algoritmo de cálculo de risco está em constante desenvolvimento. Caso tenha alguma proposta de melhoria ou especificidade da sua área profissional não hesite em [contactar-nos](../../outros/contactos.md).
