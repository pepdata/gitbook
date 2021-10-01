# Análisis manual

En la [ página de validaciones](./), puede completar una validación a través del botón correspondiente “👁”, que le da acceso a una ventana de análisis.

Esta ventana puede sugerir nombres de[ personas identificables](../../glossario/glossario-aplicacao.md#persona-identificable) relevantes, con su [grado de similitud ](../../glossario/glossario-aplicacao.md#grado-de-similitud)en relación con el nombre de[ validación](../../glossario/glossario-aplicacao.md#validacion). 

![Ventana de an&#xE1;lisis manual](../../.gitbook/assets/image%20%2810%29.png)

En la línea de cada[ persona identificable](../../glossario/glossario-aplicacao.md#persona-identificable), puede ver o su perfil a través del botón “👁” o establecer una coincidencia mediante el botón “✓”.   
Si no hay ninguna coincidencia, o ninguna de las sugerencias de la aplicación es correcta, puede validar el nombre como no identificable mediante el botón "✗ No identificable"

Una[ validación ](../../glossario/glossario-aplicacao.md#validacion)está completa una vez que se ha establecido una coincidencia entre ella y una persona identificable en la base de datos PEPData.

{% hint style="info" %}
### ¿Cómo se encuentran los resultados sugeridos?

#### Por nombre

Todos los nombres que forman el nombre de validación deben estar en la [persona identificable](../../glossario/glossario-aplicacao.md#persona-identificable) que aparece como resultado, a excepción de las [partículas](https://www.irn.mj.pt/IRN/sections/irn/a_registral/registo-civil/docs-do-civil/dar-o-nome/) \(como "de", "da", "y", etc.\). Por ejemplo:

1. "João Pedro Silva" puede resultar en el nombre "João Pedro Soares da Silva".
2. "João Pedro Pereira" **no** puede resultar en el nombre "João Pedro Soares da Silva", ya que no tiene el nombre "Pereira".
3. "João Pedro da Silva" puede resultar en el nombre "João Pedro Silva" ya que se ignora la [partícula ](https://www.irn.mj.pt/IRN/sections/irn/a_registral/registo-civil/docs-do-civil/dar-o-nome/)"da".

Se consideran las abreviaturas, si las hay. Por ejemplo:

1. "João P Silva" puede resultar en el nombre "João Pedro Soares da Silva".

#### Por fecha de nacimiento

La fecha de nacimiento de la validación, si la hay, se utiliza para filtrar los resultados. Por ejemplo:

1. Si ha introducido la fecha de nacimiento "01/01/1990" en la validación, sólo aparecerá lo siguiente [personas identificables](../../glossario/glossario-aplicacao.md#persona-identificable) con la misma fecha de nacimiento o sin información sobre la fecha de nacimiento.

#### Por límite de resultados

Como máximo, se le muestran los 20 resultados con mayor grado de similitud.

#### Por opciones auxiliares

Las siguientes opciones auxiliares pueden activarse o desactivarse en la[ página de configuración: ](../configuracoes.md#validacoes)

* Los nombres introducidos siempre contienen el primer nombre en la primera posición.
* Los nombres introducidos siempre contienen el último apellido en la última posición.

Cuando estas opciones están activas, permiten que el sistema considere que el nombre y los apellidos introducidos se corresponden siempre con el nombre y los apellidos de la persona, lo que permite obtener mejores resultados en estas situaciones.

Estas opciones deben estar en consonancia con la calidad de los datos que recoge de sus clientes. 
{% endhint %}

## Otras funcionalidades

### Búsqueda Manual

La búsqueda manual se utiliza para realizar una búsqueda rápida del nombre en la[ validación](../../glossario/glossario-aplicacao.md#validacion), sin aplicar ningún filtro. Esta funcionalidad se eliminará pronto.

### Agregar Persona

Si está seguro de que una determinada[ validación](../../glossario/glossario-aplicacao.md#validacion) debe considerarse como una persona identificable y no está en las sugerencias, puede añadirla a la base de datos PEPData. Después de la adición, será posible considerar la[ validación](../../glossario/glossario-aplicacao.md#validacion) como identificable.

{% hint style="info" %}
La persona agregada por usted sólo será visible para su organización. PEPData revisará su perfil en el futuro. Si esta persona es[ identificable](../../glossario/glossario-aplicacao.md#persona-identificable), según la ley actual, PEPData levantará la restricción y la pondrá a disposición de todos los clientes.
{% endhint %}

 

