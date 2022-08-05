# Ejemplos de utilización

{% hint style="warning" %}
La API PEPData está actualmente en versión beta. Si desea ser uno de nuestros probadores, envíe un correo electrónico a [geral@pepdata.pt](mailto:geral@pepdata.pt).
{% endhint %}

Hay dos maneras diferentes de utilizar la API PEPData. Esta página tratará de describir ambas formas y presentar sus ventajas e inconvenientes para que pueda tomar una decisión acertada sobre cuál se adapta mejor a sus necesidades.

## Búsqueda

Corresponde al ejemplo de uso más básico. Para seguir esta ruta, sólo tiene que utilizar el endpoint de [búsqueda de persona identificable](pesquisa.md#pesquisa-de-pessoa-identificavel).&#x20;

Este endpoint final acepta un nombre y una fecha de nacimiento como entradas y devuelve los resultados de la búsqueda que más se parecen a los términos de búsqueda. Para obtener los mejores resultados, se recomienda leer la documentación del área de [búsqueda](../a-aplicacao/pesquisa.md).

Tras recibir los resultados, puede procesarlos internamente para decidir si la persona buscada se corresponde con una [persona identificable](../glossario/glossario-aplicacao.md#pessoa-identificavel) en la base de datos.

#### Ventajas

* Solución muy fácil y sencilla de aplicar.
* Adecuado en caso de que necesite validar a las personas en tiempo real.

#### Desventajas

* No le permite crear una "cartera de clientes" en la aplicación PEPData, que le posibilita recibir futuras alertas en caso de cambio de estatus como [persona identificable](../glossario/glossario-aplicacao.md#pessoa-identificavel). &#x20;
* Le obliga a crear criterios internos para la validación de las personas encuestadas y su decisión no se almacena en la aplicación PEPData.
* Sólo se puede buscar a una persona a la vez.
* No permite validar a los [países sancionados](../glossario/glossario-aplicacao.md#pais-sancionado).

## Validaciones

Corresponde al ejemplo de uso más avanzado. Para seguir este camino, es necesario utilizar varios [endpoints de validación](validacoes.md).Como ejemplo, se propone el siguiente flujo de trabajo:

1. Agregue cada persona que deba ser validada utilizando el endpoint `/add_validation.` Esto acepta el nombre de la persona, la fecha de nacimiento y el país, creando así una [validación](../glossario/glossario-aplicacao.md#validacao).&#x20;
2. Cuando sea necesario, aplique las [reglas de validación](../a-aplicacao/validacoes/aplicacao-de-regras.md#regras-de-validacao) pretendidas através del endpoint `/apply_rules`.Esto le permitirá [determinar](../a-aplicacao/validacoes/#adicao-e-determinacao-de-validacoes) todas las [validaciones](../glossario/glossario-aplicacao.md#validacao) que se ajustan las reglas que ha definido.
3. Las validaciones que quedaron incompletas son más difíciles de determinar y probablemente requieren atención humana. Por ello, se recomienda determinarlas manualmente en la aplicación PEPData. Sin embargo, puede hacerlo a través de la API utilizando el endpoint `/determine_validation`.

Para obtener los mejores resultados, le recomendamos que lea la documentación relativa al área de [validaciones](../a-aplicacao/validacoes/).

#### Ventajas

* Permite crear una "cartera de clientes" en la aplicación PEPData, que le permite recibir futuras alertas en caso de cambio de estatus como persona identificable.
* Todas tus decisiones se registran en la aplicación PEPData y pueden exportarse para su uso futuro.
* Puede determinar cientos de miles de validaciones a la vez.
* Permite validar los [países sancionados](../glossario/glossario-aplicacao.md#pais-sancionado).

Desventajas

* Solución más compleja de aplicar.
* No es adecuado en caso de que necesite buscar personas en tiempo real.
