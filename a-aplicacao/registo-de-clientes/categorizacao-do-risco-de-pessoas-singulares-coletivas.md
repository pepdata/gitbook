# Clasificación del riesgo de las personas físicas/colectivas

## Metodología

El modelo de riesgo creado por PEPData se ha desarrollado para ser flexible, pero manteniendo un grado de simplicidad que permita su fácil comprensión.

Se compone de 3 categorías de riesgo distintas: bajo, medio y alto. Cada persona física o jurídica se sitúa en las distintas categorías de riesgo, teniendo en cuenta los siguientes criterios:

### Personas físicas&#x20;

* Existencia de sospecha
  * Si sospecha de la documentación presentada o el propio individuo
* Países sancionados&#x20;
  * Si el país de constitución o en el que realiza la mayor parte de sus operaciones está sancionado
* Paraísos fiscales
  * Si la persona física es residente en un país considerado como de "régimen fiscal privilegiado" por la ley española
* Clasificación como [persona identificable](../../glossario/glossario-aplicacao.md#persona-identificable).
* Clasificación como [persona sancionada](../../glossario/glossario-aplicacao.md#sancionado)

### Personas jurídicas

* Existencia de sospecha
  * Si sospecha de la documentación presentada o de la propia persona jurídica
* Países sancionados&#x20;
  * Si el país de constitución, el país de dirección del sede central o el(los) país(es) de origen del negocio es(son) sancionado(s)
* Paraísos fiscales
  * Si el país de constitución, el país de dirección del sede central o el(los) país(es) de origen del negocio se considera(n) que tiene un "régimen fiscal privilegiado" por la legislación&#x20;
* Otros criterios geográficos
  * Si no tiene domicilio social en territorio nacional
* Clasificación de la actividad económica
  * Si alguno de los CNAE's de la persona jurídica se considere de alto riesgo
* Clasificación como [persona sancionada](../../glossario/glossario-aplicacao.md#sancionado)
* Representación del cliente
  * Si alguno de los representantes está clasificado como de nível de riesgo medio o alto
* Titulares de órganos de Gobierno/Gestión o equivalente
  * Si alguno de los titulares está clasificado como de nível de riesgo medio o alto
* Titulares de participaciones en el capital/derechos de voto
  * Si alguno de los titulares esté clasificado con un nivel de riesgo medio o alto
* Titulares reales
  * Si alguno de los titulares reales está clasificado como de nível de riesgo medio o alto

#### Ajuste del factor de riesgo según el porcentaje de capital o derechos de voto

La propagación del riesgo de un cuestionario relacionado se ajusta de acuerdo con su porcentaje de capital/derechos de voto en la organización. Por ejemplo:

* Empresa A
  * Beneficiario efectivo A (20% de participación en el capital, 30% de derechos de voto) - Riesgo 1
  * Beneficiario efectivo B (80% de participación en el capital, 70% de derechos de voto) - Riesgo 3

Para obtener el porcentaje a utilizar en cada cuestionario relacionado, se calcula el **máximo entre el porcentaje de capital y el porcentaje de derechos de voto, y si este porcentaje es superior al 50%, el riesgo del cuestionario se contará en su totalidad.**

En el ejemplo anterior, el riesgo final contabilizado en la sección será de 3, es decir, el **máximo entre 0.3 (30% del riesgo del Beneficiario efectivo A) y 3 (riesgo total del Beneficiario efectivo B).**

{% hint style="warning" %}
Podrán existir relaciones cíclicas entre organizaciones a través de los Titulares de participaciones en el capital/derechos de voto. Los participantes en relaciones cíclicas están identificados en el cuestionario con el símbolo (![](<../../.gitbook/assets/triangle-exclamation-solid (2).svg>)) y su valor de riesgo no influye en el riesgo de la organización en análisis.
{% endhint %}

Nota: nuestro algoritmo de cálculo del riesgo está en constante desarrollo. Si tiene alguna propuesta de mejora o específica para su área profesional, no dude en ponerse en contacto con [nosotros](../../outros/contactos.md).
