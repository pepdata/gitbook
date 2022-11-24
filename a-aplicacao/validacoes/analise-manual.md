# Análisis manual

En la [ página de validaciones](./), puede completar una validación a través del botón correspondiente “👁”, que le da acceso a una ventana de análisis.

Esta ventana puede sugerir nombres de[ personas identificables](../../glossario/glossario-aplicacao.md#persona-identificable) relevantes, con su [grado de similitud ](../../glossario/glossario-aplicacao.md#grado-de-similitud)en relación con el nombre de[ validación](../../glossario/glossario-aplicacao.md#validacion).&#x20;

![Ventana de análisis manual](../../.gitbook/assets/validar.jpg)

En la línea de cada[ persona identificable](../../glossario/glossario-aplicacao.md#persona-identificable), puede ver su perfil a través del botón “👁” o establecer una coincidencia mediante el botón “✓”. \
Si no hay ninguna coincidencia, o ninguna de las sugerencias de la aplicación es correcta, puede validar el nombre como no identificable mediante el botón "✗ No identificable"

Una[ validación ](../../glossario/glossario-aplicacao.md#validacion)está completa una vez que se ha establecido una coincidencia entre ella y una persona identificable en la base de datos PEPData.

{% hint style="info" %}
### ¿Cómo se encuentran los resultados sugeridos?

#### Por nombre

Todos los nombres que forman el nombre de validación deben estar en la [persona identificable](../../glossario/glossario-aplicacao.md#persona-identificable) que aparece como resultado, a excepción de las partículas (como "de", "da", "y", etc.). Por ejemplo:

1. "Juan Ignacio González" puede tener como resultado el nombre "João Pedro Soares da Silva".
2. "Juan Ignacio González" **no** puede tener como resultado el nombre "Juan Ignacio de Miguel García", ya que no tiene el nombre "González".
3. "Juan Ignacio de González" puede tener como resultado el nombre "Juan Ignacio González" ya que se ignora la partícula "de".

Se consideran las abreviaturas, si las hay. Por ejemplo:

1. "Juan I González" puede tener como resultado el nombre "Juan Ignacio González García".

#### Por fecha de nacimiento

La fecha de nacimiento de la validación, si la hay, se utiliza para filtrar los resultados. Por ejemplo:

1. Si ha introducido la fecha de nacimiento "01/01/1990" en la validación, sólo aparecerán las [personas identificables](../../glossario/glossario-aplicacao.md#persona-identificable) con la misma fecha de nacimiento o sin información sobre la fecha de nacimiento.

#### Por límite de resultados

Como máximo, se le muestran los 20 resultados con mayor grado de similitud.

#### Por opciones auxiliares

Las siguientes opciones auxiliares pueden activarse o desactivarse en la[ página de configuración: ](../configuracoes/#validacoes)

* Los nombres introducidos siempre contienen el primer nombre en la primera posición.
* Los nombres introducidos siempre contienen el último apellido en la última posición.

Cuando estas opciones están activas, permiten que el sistema considere que el nombre y los apellidos introducidos se corresponden siempre con el nombre y los apellidos de la persona, lo que permite obtener mejores resultados en estas situaciones.

Estas opciones deben estar en consonancia con la calidad de los datos que recoge de sus clientes.&#x20;
{% endhint %}

## Otras funcionalidades

### Búsqueda Manual

La búsqueda manual se utiliza para realizar una búsqueda rápida del nombre en la[ validación](../../glossario/glossario-aplicacao.md#validacion), sin aplicar ningún filtro. Esta funcionalidad se eliminará pronto.

### Agregar Persona

Si está seguro de que una determinada[ validación](../../glossario/glossario-aplicacao.md#validacion) debe considerarse como una persona identificable y no está en las sugerencias, puede añadirla a la base de datos PEPData. Después de la adición, será posible considerar la[ validación](../../glossario/glossario-aplicacao.md#validacion) como identificable.

{% hint style="info" %}
La persona agregada por usted sólo será visible para su organización. PEPData revisará su perfil en el futuro. Si esta persona es[ identificable](../../glossario/glossario-aplicacao.md#persona-identificable), según la ley actual, PEPData levantará la restricción y la pondrá a disposición de todos los clientes.
{% endhint %}

&#x20;
