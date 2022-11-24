# Importación de validaciones

En la [página de validaciones](../configuracoes/#validacoes), puede importar validaciones automáticamente utilizando el botón "Importar validaciones", que le da acceso a un explorador que le permite elegir el archivo que contiene las [validaciones](../../glossario/glossario-aplicacao.md#validacion) para agregar. Para que el archivo sea interpretado correctamente por la aplicación, debe seguir una serie de especificaciones, descritas a continuación.

Una vez finalizada la carga de archivos, todos las nuevas[ validaciones](../../glossario/glossario-aplicacao.md#validacion) aparecerán  en la [página de validaciones](./).

{% hint style="info" %}
### ¿Cuáles son las especificaciones del archivo de carga?

* Sólo se permiten las extensiones .csv o .txt.
* Una [validación](../../glossario/glossario-aplicacao.md#validacion) por línea.
* Una[ validación](../../glossario/glossario-aplicacao.md#validacion) debe seguir el formato: Nombre, Fecha de nacimiento, País.&#x20;
* Cualquiera de los siguientes ejemplos representa una validación en el formato correcto: \
  André Pinheiro, 31-12-1980, Portugal \
  Ricardo Sousa Vieira Armando Rui Pinto, , Rusia\
  Armando Tavares Rocha\
  Tenga en cuenta que, en el segundo ejemplo, se agregó una coma adicional porque no hay fecha de nacimiento.
* La fecha de nacimiento debe seguir el formato dd-mm-yyyy ou dd/mm/yyyy.
* Limitado a 700.000 líneas/[validaciones](../../glossario/glossario-aplicacao.md#validacion) por archivo.
* La codificación del archivo debe ser utf-8 o ANSI.
{% endhint %}

{% hint style="info" %}
### ¿Qué debo saber antes de introducir la información?

#### Nombre

* Como mínimo, sólo se permiten 2 nombres: con nombre y primer apellido. Pero le sugerimos que ingrese al menos 2 nombres y la fecha de nacimiento, o nombre y primer y segundo apellido para que los resultados sean más correctos. Estos requisitos mínimos existen para garantizar que el sistema tenga la capacidad de sugerir resultados relevantes cuando quiera analizar si la persona es [identificable](../../glossario/glossario-aplicacao.md#pessoa-identificavel).&#x20;
* Todos los [caracteres latinos](https://en.wikipedia.org/wiki/ISO/IEC\_8859-1), la acentuación y las mayúsculas **son** compatibles y no cambian los resultados mostrados en el proceso de análisis. Por lo tanto, puede introducir el nombre en el formato que más le convenga. \
  Por ejemplo: "Ines Marçal Romão" equivaldrá a introducir "ines marcal romao".
* Aparte de los mencionados, sólo se aceptan espacios (" "), guiones ("-") o apóstrofes (" ' ").
* Las [partículas](https://www.irn.mj.pt/IRN/sections/irn/a\_registral/registo-civil/docs-do-civil/dar-o-nome/) que existen en el nombre, (como "de", "da", "y", etc.) no cambian los resultados presentados en el proceso de análisis. Por ejemplo: "Rui Miguel do Rio" equivaldrá a introducir "Rui Miguel Rio".
* Las abreviaturas son compatibles. Sin embargo, éstas no pueden ir precedidas de un punto. Por ejemplo: "Rui M Rio" podría resultar en el nombre "Rui Miguel Rio".
* Todos los puntos anteriores se han aplicado para que el proceso sea lo más sólido posible. No obstante, le recomendamos que intente introducir nombres lo más parecidos al original.

#### País

* Este campo se analiza de forma independiente, y sólo se comprueba si el país introducido está [sancionado](../../glossario/glossario-aplicacao.md#pais-sancionado). Así, este campo puede tener diferentes significados, como: origen de los fondos del cliente, lugar de residencia fiscal o cualquier otro que considere relevante
* Hay varias formas distintas de escribir el nombre de cada país. La aplicación PEPData admite cualquier valor [ISO 3166](https://en.wikipedia.org/wiki/ISO\_3166), nombre común o nombre oficial de cada país.\
  Nota: si el país asociado a una [validación](../../glossario/glossario-aplicacao.md#validacao) es sancionado, la [validación](../../glossario/glossario-aplicacao.md#validacao) heredará esta clasificación, independientemente de que corresponda a una [persona identificable](../../glossario/glossario-aplicacao.md#pessoa-identificavel). Una [validación](../../glossario/glossario-aplicacao.md#validacao) puede tener varias [clasificaciones](../../glossario/glossario-aplicacao.md#classificacao) distintas.&#x20;
{% endhint %}

{% hint style="info" %}
### No puedo cargar el archivo, ¿qué puedo hacer?

* Asegúrese que el nombre, la fecha de nacimiento y el país no están delimitados por "o". Estos valores no deben ser delimitados.
* Comprueba que al abrir el archivo no aparecen caracteres como "" en lugar de caracteres acentuados o "ç". Si esto sucede, hay un problema de codificación que puede intentar resolver siguiendo lo que se describe [aquí](upload-de-validacoes.md#codificacao-incorreta-do-ficheiro).
* Si los puntos anteriores no se aplican y sigue recibiendo un mensaje de error cada vez que intenta cargar, puede haber un problema de codificación que puede intentar resolver siguiendo los pasos descritos [aquí](upload-de-validacoes.md#codificacao-incorreta-do-ficheiro).
* Si no se aplica ninguna de las anteriores, comuníquese con PEPData
{% endhint %}

## Asistente de corrección

Si se produce un problema con los datos a introducir, aparecerá un asistente de corrección que identificará los errores encontrados en el fichero. El asistente de corrección sigue la siguiente lógica secuencial:

1. Validación de los datos introducidos: nombre, fecha y país
2. Comprobación de duplicados: si ya ha agregado una validación en el pasado, los datos que se introduzcan se considerarán duplicados. El usuario puede entonces elegir ignorar este tipo de error.

{% hint style="info" %}
Nota: Debido a las limitaciones de espacio, si hay un gran número de errores o duplicados, es posible que no se muestren todos en el asistente de corrección. Tendrá que corregirlos y volver a cargarlos para ver los errores restantes.
{% endhint %}

## Soluciones a posibles problemas

### Codificación incorrecta del archivo

Un[ archivo de texto](https://es.wikipedia.org/wiki/Archivo\_de\_texto) contiene información que sólo puede interpretarse correctamente si se conoce su código. Sólo así un ordenador puede "entender" lo que se escribe en él y ser capaz de distinguir cada carácter.&#x20;

Lamentablemente, no existe una codificación universal utilizada en todos los ordenadores, lo que puede provocar dificultades para interpretar algunos archivos de texto, especialmente los caracteres con acentos. Si un ordenador utiliza una codificación que no se corresponde con la utilizada en el archivo, puede interpretar el carácter "es" como "", por ejemplo, y no ser capaz de entender su significado.

Aunque el sistema PEPData intenta determinar la codificación del archivo cargado, este proceso no siempre es infalible y podría producirse el problema descrito. Si esto ocurre, recibirá un mensaje de error informándole de que el sistema sólo reconoce un determinado número de caracteres cada vez que intente cargar el mismo archivo.

En este caso, sugerimos las siguientes soluciones:

**Bloc de notas/Notepad do Windows**&#x20;

1. Abrir el archivo en cuestión
2. Haga clic en Archivo/File -> Guardar como... /Save As...
3. Cambiar Codificación/Encoding de UTF-8 a ANSI o de ANSI a UTF-8. Esta opción se encuentra a la izquierda del botón Guardar/Save.
4. Guardar.
5. Vuelva a cargar el archivo en la plataforma PEPData.

****[**Notepad++**](https://notepad-plus-plus.org/)****

1. Abrir el archivo en cuestión.&#x20;
2. Codificación/Encoding ->Cambiar a ANSI ou UTF-8, dependiendo de la codificación actual.
3. Guardar.
4. Vuelva a cargar el archivo en la plataforma PEPData.

