# Categorización del riesgo de transacción

## Metodología

El modelo de riesgo creado por PEPData ha sido desarrollado para ser flexible, pero manteniendo un grado de simplicidad que permite su fácil comprensión. \
Se compone de 3 categorías de riesgo distintas con los siguientes límites (en puntos):

* Bajo: \[0 - 1\[
* Medio: \[1 - 2\[
* Alto: 2+

Cada operación se clasifica en las distintas categorías de riesgo teniendo en cuenta los siguientes criterios:

* Existencia de sospecha:&#x20;
  * Si sospecha de la documentación presentada o de la propia transacción.
    * Aumenta el riesgo en 2 puntos.
* Método de pago:&#x20;
  * Transferencia bancaria:
    * Si el pago se realizó a través de un banco no residente en Portugal
      * Aumenta el riesgo en 2 puntos.
  * Activo virtual:
    * Si el pago se realizó en un activo virtual no regulado
      * Aumenta el riesgo en 1 punto.
    * Si el pago se realizó a través de una entidad que no está registrada para realizar actividades con activos virtuales
      * Aumenta el riesgo en 2 puntos.
* Combinación de Método de Pago e Importe
  * Pagos en efectivo
    * Si la suma de los pagos en euros (€) realizados por entidades individuales es igual o superior a 3.000€
      * Aumenta el riesgo en 2 puntos.
    * Si la suma de los pagos en moneda extranjera realizados por entidades individuales es igual o superior a 10.000€, una vez realizada la conversión respectiva
      * Aumenta el riesgo en 2 puntos.
    * Si la suma de los pagos realizados por entidades colectivas es igual o superior a 1.000€
      * Aumenta el riesgo en 2 puntos.

{% hint style="info" %}
* Activos virtuales regulados:
  * Bitcoin (BTH);
  * Ethereum (ETH)
* Puede consultar [aquí](https://www.bportugal.pt/sites/default/files/lista\_entidades\_ativos\_virtuais\_pt.pdf) la lista de entidades portuguesas registradas para realizar actividades con activos virtuales.
{% endhint %}

Nota: nuestro algoritmo de cálculo del riesgo está en constante desarrollo. Si tiene alguna propuesta de mejora o específica en su área profesional, no dude en [contactarnos](../../outros/contactos.md).
