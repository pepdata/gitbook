# Importación de validaciones

En la [página de validaciones](../configuracoes/#validacoes), puede importar validaciones automáticamente utilizando el botón "Importar validaciones", que le da acceso a un explorador que le permite elegir el archivo que contiene las [validaciones](../../glossario/glossario-aplicacao.md#validacion) para agregar.

Antes de elegir el archivo de importación, deverá elegir el tipo de validaciones a importar seleccionando el icono correspondiente:

<figure><img src="../../.gitbook/assets/Untitled-1.jpg" alt=""><figcaption><p>Selección del tipo de validaciones a importar</p></figcaption></figure>

La aplicación selecciona automáticamente el tipo "Personas". Para importar validaciones de organizaciones, debe seleccionar el icono en forma de edificio.

Una vez finalizada la carga de archivos, todos las nuevas[ validaciones](../../glossario/glossario-aplicacao.md#validacion) aparecerán  en la [página de validaciones](./).

Para que el archivo sea interpretado correctamente por la aplicación, debe seguir una serie de especificaciones, descritas a continuación.

## Detalles de los archivos a importar

### Detalhes Gerais

* La primera línea debe contener el nombre de las columnas que representan la información a importar&#x20;
* Extensión .txt o .csv&#x20;
* Limitado a 500 000 filas por importación

### Fichero de personas

* Debe contener una persona por línea&#x20;
* Propiedades aceptadas (obligatorio en negrita):

| Campos               | Notas                                                                                                                                                                               |
| -------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| vat\_number          | Los números de identificación fiscal internacionales deben tener el código de país correspondiente al principio: Ej: FR12345678901 para un número de identificación fiscal francés. |
| **name**             | [Aquí](upload-de-validacoes.md#regras-a-cumplir), puedes ver las reglas a seguir en cuanto a los nombres.                                                                           |
| birth\_date          | La fecha de nacimiento debe seguir el formato dd-mm-yyyy ou dd/mm/yyyy.                                                                                                             |
| country\_nationality | [Aquí](upload-de-validacoes.md#regras-a-cumplir), puedes ver las reglas a seguir en cuanto a los países.                                                                            |
| country\_address     | [Aquí](upload-de-validacoes.md#regras-a-cumplir), puedes ver las reglas a seguir en cuanto a los países.                                                                            |
| id\_custom           | Identificador de cliente utilizado por su organización. Tiene que ser único.                                                                                                        |
| unidentifiable       | 1 o 0, si no es identificable.                                                                                                                                                      |

#### Archivo de muestra

{% file src="../../.gitbook/assets/validación individual.txt" %}

### Archivo de organización

* Debe contener una organización por línea&#x20;
* Propiedades aceptadas (obligatorio en negrita):

| Campos         | Notas                                                                                                                                                                               |
| -------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| vat\_number    | Los números de identificación fiscal internacionales deben tener el código de país correspondiente al principio: Ej: FR12345678901 para un número de identificación fiscal francés. |
| **name**       | [Aquí](upload-de-validacoes.md#regras-a-cumplir), puedes ver las reglas a seguir en cuanto a los nombres.                                                                           |
| country        | [Aquí](upload-de-validacoes.md#regras-a-cumplir), puedes ver las reglas a seguir en cuanto a los países.                                                                            |
| id\_custom     | Identificador de cliente utilizado por su organización. Tiene que ser único.                                                                                                        |
| unidentifiable | 1 o 0, si no es identificable.                                                                                                                                                      |

#### Archivo de muestra

{% file src="../../.gitbook/assets/validación de la organización.txt" %}

### Archivo de relación

* Debe contener una organización por línea&#x20;
* Propiedades aceptadas (obligatorio en negrita):

| Campos                         | Notas                                                                                                  |
| ------------------------------ | ------------------------------------------------------------------------------------------------------ |
| **organization\_vat\_number**  | CIF de la organización para entrar en las relaciones. Esta organización ya debe existir en el sistema. |
| **vat\_number**                | NIF de la relación a insertar. Este individuo ya debe existir en el sistema.                           |
| **position\_in\_organization** | Puede ser: representative, manager, owner o beneficial\_owner.                                         |

#### Archivo de muestra

{% file src="../../.gitbook/assets/relaciones de validationes.txt" %}

### Regras a cumplir

{% hint style="info" %}
### ¿Cuáles son las especificaciones del archivo de carga?

* Una [validación](../../glossario/glossario-aplicacao.md#validacion) por línea.
* Una validación debe seguir el orden de los campos definidos en el encabezado.
* La codificación del archivo debe ser utf-8 o ANSI.
{% endhint %}

{% hint style="info" %}
### ¿Qué debo saber antes de introducir la información?

#### Nombre

* En el caso de validaciones relativas a personas, sólo se permiten un mínimo de 2 nombres: con nombre y primer apellido. Pero le sugerimos que ingrese al menos 2 nombres y la fecha de nacimiento, o nombre y primer y segundo apellido para que los resultados sean más correctos. Estos requisitos mínimos existen para garantizar que el sistema tenga la capacidad de sugerir resultados relevantes cuando quiera analizar si la persona es [identificable](../../glossario/glossario-aplicacao.md#pessoa-identificavel).&#x20;
* Todos los [caracteres latinos](https://en.wikipedia.org/wiki/ISO/IEC\_8859-1), la acentuación y las mayúsculas **son** compatibles y no cambian los resultados mostrados en el proceso de análisis. Por lo tanto, puede introducir el nombre en el formato que más le convenga. \
  Por ejemplo: "Ines Marçal Romão" equivaldrá a introducir "ines marcal romao".
* Aparte de los mencionados, sólo se aceptan espacios (" "), guiones ("-") o apóstrofes (" ' ").
* Las [partículas](https://www.irn.mj.pt/IRN/sections/irn/a\_registral/registo-civil/docs-do-civil/dar-o-nome/) que existen en el nombre de personas, (como "de", "da", "y", etc.) no cambian los resultados presentados en el proceso de análisis. Por ejemplo: "Rui Miguel do Rio" equivaldrá a introducir "Rui Miguel Rio".
* Validaciones de personas admiten nombres con abreviaturas . Sin embargo, éstas no pueden ir precedidas de un punto. Por ejemplo: "Rui M Rio" podría resultar en el nombre "Rui Miguel Rio".
* Todos los puntos anteriores se han aplicado para que el proceso sea lo más sólido posible. No obstante, le recomendamos que intente introducir nombres lo más parecidos al original.

#### País

* Este campo se analiza de forma independiente, y sólo se comprueba si el país introducido (país de nacionalidad, en el caso de personas, o país, en el caso de organizaciones) está [sancionado](../../glossario/glossario-aplicacao.md#pais-sancionado). Así, este campo puede tener diferentes significados, como: origen de los fondos del cliente, lugar de residencia fiscal o cualquier otro que considere relevante
* Hay varias formas distintas de escribir el nombre de cada país. La aplicación PEPData admite cualquier valor [ISO 3166](https://en.wikipedia.org/wiki/ISO\_3166), nombre común o nombre oficial de cada país.\
  Nota: si el país asociado a una [validación](../../glossario/glossario-aplicacao.md#validacao) es sancionado, la [validación](../../glossario/glossario-aplicacao.md#validacao) heredará esta clasificación, independientemente de que corresponda a una [persona identificable](../../glossario/glossario-aplicacao.md#pessoa-identificavel). Una [validación](../../glossario/glossario-aplicacao.md#validacao) puede tener varias [clasificaciones](../../glossario/glossario-aplicacao.md#classificacao) distintas.&#x20;
{% endhint %}

{% hint style="info" %}
### No puedo cargar el archivo, ¿qué puedo hacer?

* Asegúrese que el nombre, la fecha de nacimiento y campos relacionados con países no están delimitados por "o". Estos valores no deben ser delimitados.
* Comprueba que al abrir el archivo no aparecen caracteres como "" en lugar de caracteres acentuados o "ç". Si esto sucede, hay un problema de codificación que puede intentar resolver siguiendo lo que se describe [aquí](upload-de-validacoes.md#codificacao-incorreta-do-ficheiro).
* Si los puntos anteriores no se aplican y sigue recibiendo un mensaje de error cada vez que intenta cargar, puede haber un problema de codificación que puede intentar resolver siguiendo los pasos descritos [aquí](upload-de-validacoes.md#codificacao-incorreta-do-ficheiro).
* Si no se aplica ninguna de las anteriores, comuníquese con PEPData
{% endhint %}

## Asistente de corrección

Si se produce un problema con los datos a introducir, aparecerá un asistente de corrección que identificará los errores encontrados en el fichero. El asistente de corrección sigue la siguiente lógica secuencial:

1. Validación de fila de encabezado;
2. Validación de los datos introducidos:
   * name;
   * birth\_date (en el caso de validaciones de personas);
   * country\_nationality (en el caso de validaciones de personas);
   * country\_address (en el caso de validaciones de personas);
   * country (en el caso de validaciones de organizaciones);
   * vat\_number
3. Comprobación de duplicados: si ya ha agregado una validación en el pasado, los datos que se introduzcan se considerarán duplicados. El usuario puede entonces elegir ignorar este tipo de error.

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

[**Notepad++**](https://notepad-plus-plus.org/)

1. Abrir el archivo en cuestión.&#x20;
2. Codificación/Encoding ->Cambiar a ANSI ou UTF-8, dependiendo de la codificación actual.
3. Guardar.
4. Vuelva a cargar el archivo en la plataforma PEPData.

