# Análisis manual

En la [ página de validaciones](./), puede completar una validación a través del botón de la lupa, que le da acceso a una ventana de análisis.

Esta ventana puede sugerir nombres de[ personas identificables](../../glossario/glossario-aplicacao.md#persona-identificable) (en el caso de la validación de una persona) u [organizaciones identificables](../../glossario/glossario-aplicacao.md#organizacion-identificable) (en el caso de la validación de una organización) relevantes, con su [grado de similitud ](../../glossario/glossario-aplicacao.md#grado-de-similitud)en relación con el nombre de[ validación](../../glossario/glossario-aplicacao.md#validacion).

<figure><img src="../../.gitbook/assets/analisar validação ES.jpg" alt=""><figcaption><p>Ventana de análisis manual</p></figcaption></figure>

En la línea de cada[ persona identificable](../../glossario/glossario-aplicacao.md#persona-identificable), puede ver su perfil a través del botón “👁”, establecer una coincidencia mediante el botón “✓” o agregar/eliminar personas de la lista de non correspondencia usando los íconos de persona.

Si se trata de una validación de organización, en cada línea de [organización identificable](../../glossario/glossario-aplicacao.md#organizacion-identificable), podrá definir una correspondencia mediante el botón “✓” o agregar/eliminar organizaciones de la lista de non correspondencia usando los íconos de edificio.

\
Si no hay ninguna coincidencia, o ninguna de las sugerencias de la aplicación es correcta, puede validar el nombre como no identificable mediante el botón "✗ No identificable"

Una[ validación ](../../glossario/glossario-aplicacao.md#validacion)está completa una vez que se ha establecido una coincidencia entre ella y una persona identificable en la base de datos PEPData.

{% hint style="info" %}
### ¿Cómo se encuentran los resultados sugeridos?

#### Por nombre

En validaciones de personas, todos los nombres que forman el nombre de validación deben estar en la [persona identificable](../../glossario/glossario-aplicacao.md#persona-identificable) que aparece como resultado, a excepción de las partículas (como "de", "da", "y", etc.). Por ejemplo:

1. "Juan Ignacio González" puede tener como resultado el nombre "João Pedro Soares da Silva".
2. "Juan Ignacio González" **no** puede tener como resultado el nombre "Juan Ignacio de Miguel García", ya que no tiene el nombre "González".
3. "Juan Ignacio de González" puede tener como resultado el nombre "Juan Ignacio González" ya que se ignora la partícula "de".

En validaciones de personas, las abreviaturas, si las hay, se consideran. Por ejemplo:

1. "Juan I González" puede tener como resultado el nombre "Juan Ignacio González García".

En validaciones de organizaciones, la búsqueda intentará encontrar un resultado donde el nombre coincida exactamente con el nombre de la validación.

#### Por fecha de nacimiento (válido solo para validaciones de personas)

La fecha de nacimiento de la validación, si la hay, se utiliza para filtrar los resultados. Por ejemplo:

1. Si ha introducido la fecha de nacimiento "01/01/1990" en la validación, sólo aparecerán las [personas identificables](../../glossario/glossario-aplicacao.md#persona-identificable) con la misma fecha de nacimiento o sin información sobre la fecha de nacimiento.

#### Por límite de resultados

En validaciones de personas, como máximo, se le muestran los 20 resultados con mayor grado de similitud.

En validaciones de organizaciones, se le presenta, si lo hay, un resultado cuyo nombre corresponde exactamente al nombre de la validación.

#### Por opciones auxiliares (válido solo para validaciones de personas)

Las siguientes opciones auxiliares pueden activarse o desactivarse en la[ página de configuración: ](../configuracoes/#validacoes)

* Los nombres introducidos siempre contienen el primer nombre en la primera posición.
* Los nombres introducidos siempre contienen el último apellido en la última posición.

Cuando estas opciones están activas, permiten que el sistema considere que el nombre y los apellidos introducidos se corresponden siempre con el nombre y los apellidos de la persona, lo que permite obtener mejores resultados en estas situaciones.

Estas opciones deben estar en consonancia con la calidad de los datos que recoge de sus clientes.&#x20;
{% endhint %}

## Otras funcionalidades

### Agregar Persona (disponible en validaciones de personas)

Si está seguro de que una determinada[ validación](../../glossario/glossario-aplicacao.md#validacion) debe considerarse como una persona identificable y no está en las sugerencias, puede añadirla a la base de datos PEPData. Después de la adición, será posible considerar la[ validación](../../glossario/glossario-aplicacao.md#validacion) como identificable.

{% hint style="info" %}
La persona agregada por usted sólo será visible para su organización. PEPData revisará su perfil en el futuro. Si esta persona es[ identificable](../../glossario/glossario-aplicacao.md#persona-identificable), según la ley actual, PEPData levantará la restricción y la pondrá a disposición de todos los clientes.
{% endhint %}

&#x20;
