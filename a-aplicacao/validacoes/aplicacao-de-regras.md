# Aplicación de reglas

En la  [página de validaciones](./), puede realizar un análisis automático de cada validación que tenga un estado incompleto, a través del botón "Aplicar reglas". 

{% hint style="warning" %}
Por defecto, las reglas a aplicar están desactivadas y deben ser activadas por usted a través del [página de configuración](../configuracoes.md). Sin embargo, antes de hacerlo, se recomienda encarecidamente la lectura de la siguiente información, ya que la aplicación de las reglas de validación, sin su correcta comprensión, puede provocar cambios no deseados y complicados o imposibles de revertir.
{% endhint %}

### Reglas  de validación

Hay dos reglas de validación, que se pueden activar o desactivar en la [página de configuración](../configuracoes.md): 

1. Considera como no identificables los nombres que no tienen correspondencia. 
2. Considera como identificables todos los nombres con una solo correspondencia posible y un alto [grado de similitud](../../glossario/glossario-aplicacao.md#grau-de-semelhanca).

Como máximo, las reglas se aplicarán a 80.000 [validaciones](../../glossario/glossario-aplicacao.md#validacao) a la vez. 

{% hint style="info" %}
### Como funciona la aplicación de las reglas?

En este ejemplo, considere que ambas reglas de validación están activas. Así pues, al hacer clic en "Aplicar reglas", el sistema procederá de la siguiente manera, para cada [validación](../../glossario/glossario-aplicacao.md#validacao) incompleta:

1. Busca en la base de datos PEPData todas las personas identificables con un nombre similar al de la [validación](../../glossario/glossario-aplicacao.md#validacao).
2. Mediante el paso anterior, se obtiene una lista de resultados sugeridos, como se describe en la siguiente nota:
   1. Si no hay coincidencias sugeridas, porque la regla 1 está activa, la [validación](../../glossario/glossario-aplicacao.md#validacao) se establecerá como no identificable.
   2. Si sólo hay un resultado y su [grado de similitud](../../glossario/glossario-aplicacao.md#grau-de-semelhanca) es mayor que el [threshold de validación](../configuracoes.md#threshold-de-validacao), porque la regla 2 está activa, la [validación](../../glossario/glossario-aplicacao.md#validacao) se establecerá como identificable. 
   3. Si sólo hay un resultado y el [grado de similitud](../../glossario/glossario-aplicacao.md#grau-de-semelhanca) es inferior o igual al [threshold de validación](../configuracoes.md#threshold-de-validacao), la validación quedará incompleta y habrá que realizar un [análisis manual](analise-manual.md).
   4. Si existen varios resultados, la [validación](../../glossario/glossario-aplicacao.md#validacao) quedará incompleta y será necesario un [análisis manual](analise-manual.md).
{% endhint %}

{% hint style="info" %}
### ¿Cómo se encuentran los resultados sugeridos?

#### Por nombre

Todos los nombres que forman o nombre de [validación](../../glossario/glossario-aplicacao.md#validacao) deben que estar en el nombre de la persona identificable que aparece como resultado, a excepción de las partículas \(como "de", "y", etc.\). Ejemplificando:

1. "João Pedro Silva" puede dar lugar al nombre "João Pedro Soares da Silva".
2. "João Pedro Pereira" **no** puede dar lugar al nombre "João Pedro Soares da Silva", ya que no tiene el nombre "Pereira".
3. "João Pedro da Silva" puede resultar en el nombre "João Pedro Silva" ya que la partícula "da" se ignora.

Se consideran las abreviaturas, si las hay. Por ejemplo:

1. "João P Silva" puede dar lugar al nombre "João Pedro Soares da Silva".

#### Por fecha de nacimiento

La fecha de nacimiento de la [validación](../../glossario/glossario-aplicacao.md#validacao), si la hay, se utiliza para filtrar los resultados. Por ejemplo:

Si ha introducido la fecha de nacimiento "01/01/1990" en la [validación](../../glossario/glossario-aplicacao.md#validacao), sólo aparecerán personas identificables con la misma fecha de nacimiento o sin información sobre la fecha de nacimiento.

#### Por límite de resultados

Como máximo, se le muestran los 20 resultados con mayor [grado de similitud](../../glossario/glossario-aplicacao.md#grau-de-semelhanca). 

#### Por opciones auxiliares

Las siguientes opciones auxiliares pueden activarse o desactivarse en la [página de configuración](../configuracoes.md): 

* Los nombres introducidos siempre contienen el primer nombre en la primera posición.
* Los nombres introducidos siempre contienen el último apellido en la última posición.

Cuando estas opciones están activas, permiten que el sistema considere que el nombre y los apellidos introducidos se corresponden siempre con el nombre y los apellidos de la persona, lo que permite obtener mejores resultados en estas situaciones.

Estas opciones deben estar en consonancia con la calidad de los datos que recoge de sus clientes.
{% endhint %}

## 

