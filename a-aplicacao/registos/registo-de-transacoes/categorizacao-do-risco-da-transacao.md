# Categorização do risco da transação

## Metodologia

O modelo de risco criado pela PEPData foi desenvolvido de forma a ser flexível, mantendo um grau de simplicidade que o permite ser facilmente compreendido.\
Este é composto por 3 categorias distintas de risco com os seguintes limites (em pontos):&#x20;

* Baixo: \[0 - 1\[
* Médio: \[1 - 2\[
* Alto: 2+

Cada transação é enquadrada nas várias categorias de risco tendo em consideração os seguintes critérios:

* Existência de suspeição:
  * Caso suspeite da documentação apresentada ou da transação em si.
    * Aumenta o risco em 2 pontos.
* Método de pagamento
  * Transferência bancária:
    * Caso o pagamento tenha sido realizado através de um banco não residente em Portugal
      * Aumenta o risco em 2 pontos.
  * Moeda virtual:
    * Caso o pagamento tenha sido realizado num ativo virtual não regulamentado
      * Aumenta o risco em 1 ponto.
    * Caso o pagamento tenha sido realizado através de uma entidade que não esteja registada para o exercício de atividades com ativos virtuais
      * Aumenta o risco em 2 pontos.
* Combinação entre Método de pagamento e Montante:
  * Pagamentos em numerário:
    * Caso o somatório dos pagamentos em euros (€) feitos por entidades individuais seja igual ou superior a 3.000€
      * Aumenta o risco em 2 pontos.
    * Caso o somatório dos pagamentos em moeda estrangeira feitos por entidades individuais seja igual ou superior a 10.000€, após feita a respetiva conversão
      * Aumenta o risco em 2 pontos.
    * Caso o somatório dos pagamentos feitos por entidades coletivas seja igual ou superior a 1.000€
      * Aumenta o risco em 2 pontos.
* Intervenientes da transação:
  * Caso existam intervenientes com risco medio
    * Aumenta o risco em 1 ponto.
  * Caso existam intervenientes com risco alto
    * Aumenta o risco em 2 pontos.

{% hint style="info" %}
* Ativos virtuais regulamentados:
  * Bitcoin (BTH);
  * Ethereum (ETH)
* Pode consultar [aqui ](https://www.bportugal.pt/sites/default/files/lista\_entidades\_ativos\_virtuais\_pt.pdf)a lista de entidades portuguesas registadas para o exercício de atividades com ativos virtuais.
{% endhint %}



Nota: o nosso algoritmo de cálculo de risco está em constante desenvolvimento. Caso tenha alguma proposta de melhoria ou especificidade da sua área profissional não hesite em [contactar-nos](../../../outros/contactos.md).
