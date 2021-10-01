# Búsqueda

Esta página le permite buscar por nombre, listando todas las [personas identificables](../glossario/glossario-aplicacao.md#pessoa-identificavel) con nombres similares al introducido

La lista de resultados mostrará los nombres y las fechas de nacimiento de las personas encontradas, y podrá ver su perfil haciendo clic en el botón “👁”.

![P&#xE1;gina de pesquisa](../.gitbook/assets/search.gif)

{% hint style="info" %}
### ¿Cómo se encuentran los resultados sugeridos?

#### Por nombre

Todos los nombres que forman el nombre de [validación](../glossario/glossario-aplicacao.md#validacao) deben estar a nombre de la [persona identificable ](../glossario/glossario-aplicacao.md#pessoa-identificavel)que aparece como resultado. Ejemplificando:
{% endhint %}

{% hint style="info" %}
1. "João Pedro Silva" puede dar lugar al nombre "João Pedro Soares da Silva".
2. "João Pedro Pereira" **no** puede dar lugar al nombre "João Pedro Soares da Silva", ya que no tiene el nombre "Pereira".

Se consideran las abreviaturas, si las hay. Ejemplificando:

1. "João P Silva" puede dar lugar al nombre "João Pedro Soares da Silva".

#### Por límite de resultados

Como máximo, se le muestran los 25 resultados con mayor [grado de similitud](../glossario/glossario-aplicacao.md#grau-de-semelhanca). 
{% endhint %}

