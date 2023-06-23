# Adición manual

En la[ página de validaciones](./), puede agregar manualmente una validación a través del botón "+ Agregar validación", que le da acceso a una ventana para hacerlo.

En esta ventana, deberá seleccionar inicialmente el tipo de validación a agregar, eligiendo el icono correspondiente. La aplicación selecciona automáticamente el tipo "Persona". Para agregar una validación de organización, deberá elegir el icono en forma de edificio.

Luego de selecionar el tipo de validación, tendrá a su disposición un conjunto de campos donde podrá llenar información referente a la validación y que dependerá del tipo selecionado:

#### Validación de persona física:

| Campos               | Notas                                                                                                                                                                               |
| -------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Nombre               | [Aquí](adicao-manual.md#reglas-para-seguir), puedes ver las reglas a seguir en cuanto a los nombres.                                                                                |
| CIF                  | Los números de identificación fiscal internacionales deben tener el código de país correspondiente al principio: Ej: FR12345678901 para un número de identificación fiscal francés. |
| Fecha de Nacimiento  | La fecha de nacimiento debe seguir el formato definido en la [página de configuración](../configuracoes/).                                                                          |
| País de Nacionalidad | [Aquí](adicao-manual.md#reglas-para-seguir), puedes ver las reglas a seguir en cuanto a los países.                                                                                 |
| País de Dirección    | [Aquí](adicao-manual.md#reglas-para-seguir), puedes ver las reglas a seguir en cuanto a los países.                                                                                 |
| ID                   | Identificador de cliente utilizado por su organización. Tiene que ser único.                                                                                                        |

#### Validación de organización:

| Campos | Notas                                                                                                                                                                               |
| ------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Nombre | [Aquí](adicao-manual.md#reglas-para-seguir), puedes ver las reglas a seguir en cuanto a los nombres.                                                                                |
| CIF    | Los números de identificación fiscal internacionales deben tener el código de país correspondiente al principio: Ej: FR12345678901 para un número de identificación fiscal francés. |
| País   | [Aquí](adicao-manual.md#reglas-para-seguir), puedes ver las reglas a seguir en cuanto a los países.                                                                                 |
| ID     | Identificador de cliente utilizado por su organización. Tiene que ser único.                                                                                                        |

#### Reglas para seguir

{% hint style="info" %}
### &#x20;¿Qué debo saber antes de introducir la información?

#### Nombre

* En el caso de validaciones relativas a personas, sólo se permiten un mínimo de 2 nombres: con nombre y primer apellido. Pero le sugerimos que ingrese al menos 2 nombres y la fecha de nacimiento, o nombre y primer y segundo apellido para que los resultados sean más correctos. Estos requisitos mínimos existen para garantizar que el sistema tenga la capacidad de sugerir resultados relevantes cuando quiera analizar si la persona es [identificable](../../glossario/glossario-aplicacao.md#pessoa-identificavel).
* **Se admiten** todos los [caracteres latinos](https://en.wikipedia.org/wiki/ISO/IEC\_8859-1), su acentuación y sus mayúsculas, sin alterar los resultados mostrados en el proceso de análisis. Por lo tanto, puede introducir el nombre en el formato que más le convenga.\
  Por ejemplo: "Ines Marçal Romão" equivaldrá a introducir "ines marcal romao".
* Aparte de los mencionados, sólo se aceptan espacios (" "), guiones ("-") o apóstrofes (" ' ").
* Las partículas existentes en el nombre de personas (como "de", "da", "y", etc.) no alteran los resultados presentados en el proceso de análisis.\
  Por ejemplo: "Rui Miguel do Rio" equivaldrá a introducir "Rui Miguel Rio".
* Validaciones de personas admiten nombres con abreviaturas. Sin embargo, no se puede proceder con un punto final.\
  Por ejemplo: "Rui M Rio" podría resultar en el nombre "Rui Miguel Rio".
* Todos los puntos anteriores se han aplicado para que el proceso sea lo más sólido posible. Sin embargo, le recomendamos que intente introducir nombres lo más parecidos al original.

#### País

* Este campo se analiza de forma independiente, y sólo se verifica si el país introducido (país de nacionalidad, en el caso de personas, o país, en el caso de organizaciones) está [sancionado](../../glossario/glossario-aplicacao.md#pais-sancionado). Así, este campo puede tener diferentes significados, como: origen de los fondos del cliente, lugar de residencia fiscal o cualquier otro que considere relevante.\
  Nota: Si el país asociado a una[ validación](../../glossario/glossario-aplicacao.md#validacion) está [sancionado](../../glossario/glossario-aplicacao.md#pais-sancionado), la [validación](../../glossario/glossario-aplicacao.md#validacion) heredará esta[ clasificación](../../glossario/glossario-aplicacao.md#validacion), independientemente de que corresponda a una[ persona identificable](../../glossario/glossario-aplicacao.md#persona-identificable). Una[ validación](../../glossario/glossario-aplicacao.md#validacion) puede tener varias clasificaciones distintas.&#x20;
{% endhint %}

Después de rellenar la información, hay dos opciones, a las que se accede pulsando los botones con el mismo nombre:

#### Agregar y revisar

Agrega la[ validación](../../glossario/glossario-aplicacao.md#validacion) al sistema y abre inmediatamente su ventana de análisis manual.

#### Agregar&#x20;

Agrega la [validación](../../glossario/glossario-aplicacao.md#validacion) al sistema y actualiza la grilla principal.

