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
* Importe:&#x20;
  * si el importe supera los 15.000€
    * Aumenta el riesgo en 1 punto.
* Combinación de Método de Pago e Importe
  * Si la forma de pago es en efectivo y el importe es superior a 3000€
    * Aumenta el riesgo en 1 punto.

Nota: nuestro algoritmo de cálculo del riesgo está en constante desarrollo. Si tiene alguna propuesta de mejora o específica en su área profesional, no dude en [contactarnos](../../outros/contactos.md).
