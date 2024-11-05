# Configuración de Riesgo

La configuración del riesgo es una potente herramienta que le permite personalizar el cálculo del riesgo de sus [clientes ](../registo-de-clientes/)en función de las particularidades de su organización y del área de negocio en la que se encuentre.

Estos ajustes se centran en tres componentes esenciales:

* Las [fórmulas de riesgo](configuracion-de-riesgo.md#formulas-de-riesgo)
* Las [categorías de riesgo](configuracion-de-riesgo.md#categorias-de-riesgo)
* Los [niveles de riesgo](configuracion-de-riesgo.md#niveles-de-riesgo)

Sólo después de configurar estos tres componentes podrá activar la personalización del cálculo de riesgo para su organización.

### Fórmulas de riesgo

Las fórmulas de riesgo son el centro de la configuración del riesgo, ya que permiten especificar las ponderaciones de riesgo que se aplicarán a cada uno de los [factores de riesgo ](configuracion-de-riesgo.md#factores-de-riesgo)disponibles y aplicar una amplia gama de funciones al cálculo del riesgo.

Existen dos tipos de fórmulas de riesgo:

* Para personas físicas: incluidos los titulares reales y los representantes
* Para las personas jurídicas

#### Factores de riesgo

Para incorporar un factor de riesgo a su fórmula, sólo tiene que arrastrarlo al área de entrada de la fórmula. Los factores de riesgo se identifican en recuadros grises junto al área de entrada.

Existen factores de riesgo simples, en los que el valor se calcula teniendo en cuenta un solo valor, y factores de riesgo compuestos, en los que el valor se calcula teniendo en cuenta la aplicación de una función a múltiples valores.

En la aplicación están disponibles los siguientes factores de riesgo:

* Fórmula de riesgo para personas físicas
  * **Clasificación de la persona**: en caso de existir varias clasificaciones, se suman sus niveles de riesgo o se considera sólo el nivel más alto, dependiendo de si se define la función Suma o Máxima en la pestaña "Personas identificables", respectivamente.
  * **Nacionalidades**: si hay varias, sólo se tiene en cuenta el nivel de riesgo más alto.
  * **Lugar de nacimiento**
  * **País de residencia**
  * **Existencia de noticias adversas**
* Fórmula de riesgo para las personas jurídicas
  * **Sectores de actividad**: si hay varios, sólo se considera el nivel de riesgo más alto.
  * **Países donde opera**: si hay varios, sólo se considera el nivel de riesgo más alto.
  * **Clasificación de la persona jurídica**: En caso de que existan varias clasificaciones, se sumarán sus niveles de riesgo o sólo se considerará el nivel más alto, dependiendo de si se establece la función Suma o Máxima en la pestaña "Personas identificables", respectivamente.
  * **Representantes de la persona jurídica**: en caso de que haya varios, sólo se considera el nivel de riesgo más alto.
  * **Titulares de Órganos de Administración/Gestión:** si hay varios, sólo se considera el nivel de riesgo más alto.
  * **Titulares de Acciones/Derechos de voto:** si hay varios, sólo se considera el nivel de riesgo más alto.
  * **Titulares reales**: si hay varios, sólo se considera el nivel de riesgo más alto.
  * **País de constitución**
  * **País de sede social**
  * **Fecha de fundación**
  * **Existencia de noticias adversas**

#### Sintaxis de las fórmulas

* Las fórmulas utilizadas tienen la misma base que las de Excel. Por lo tanto, deben comenzar con el símbolo "=".
* Todas las funciones que existen en Excel están disponibles y deben escribirse en mayúsculas. Ej: SUM(), MAX().
* La separación de los valores debe hacerse utilizando la coma. Ej: MAX(1, 2).
* Los decimales deben especificarse con un punto. Ej: 1.2.

### Categorías de riesgo

El cálculo del valor del riesgo no tiene significado propio, siendo necesario encajarlo en los intervalos de las categorías de riesgo, que también pueden ser definidos por el usuario.

La definición de estos intervalos puede hacerse en la pestaña "Categorías".

Además de los intervalos, también es posible definir un estado de aprobación automático que apruebe o rechace al cliente según la categoría de riesgo en el momento de la presentación.

### Niveles de riesgo

Los niveles de riesgo son los componentes más elementales del cálculo del riesgo.

Se pueden definir para cada uno de los [factores de riesgo](configuracion-de-riesgo.md#factores-de-riesgo) en las fichas respectivas.

{% hint style="success" %}
La elaboración de modelos de riesgo es un área compleja y técnica, y es importante contar con expertos que puedan ayudarle en cada paso del camino. Si tiene alguna pregunta, no dude en ponerse en [contacto con nosotros](../../outros/contactos.md).
{% endhint %}
