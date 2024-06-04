# Importación de Clientes

La nueva importación de clientes le permite cargar fácil y rápidamente sus clientes en la plataforma PEPData, creando automáticamente un registro para cada cliente.

Para ello, divida la información a importar en 3 archivos distintos:

* Personas jurídicas
  * Archivo con sus clientes que son sociedades
* Personas físicas
  * Archivo de los miembros del consejo de administración y de los propietarios efectivos de las sociedades que son sus clientes.
* Relaciones entre personas físicas y personas jurídicas
  * Fichero que recoge las relaciones entre las sociedades y las personas físicas mencionadas anteriormente
  * Este debe ser el último archivo en ser importado, y sólo será aceptado si los otros dos ya han sido insertados

Una vez creados estos 3 archivos, puede importarlos mediante el botón "Importar registros" de la página "Registro de clientes".



## Datos de los archivos a importar

### Datos generales

* La primera línea debe contener el nombre de las columnas que representan la información a importar
* Extensión .txt o .csv
* Limitado a 700.000 líneas por cada importación

### Archivo de personas jurídicas

* Debe contener una sociedad por línea
* Campos aceptados (obligatorios en negrita):

| Campos                |                                                                                                                                                                                                                            |
| --------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| id\_custom            | Identificador del cliente que usa su empresa. Tiene que ser único.                                                                                                                                                         |
| **name**              |                                                                                                                                                                                                                            |
| **vat\_number**       |                                                                                                                                                                                                                            |
| responsible\_email    | Dirección de correo electrónico del usuario que se encargará del cuestionario del cliente. Debe ser un usuario de su empresa.                                                                                              |
| invited\_email        | Correo electrónico de la persona a la que hay que invitar a completar el cuestionario. Nota: la invitación tendrá que ser enviada manualmente, después de la inserción.                                                    |
| corporate\_object     |                                                                                                                                                                                                                            |
| foundation\_date      |                                                                                                                                                                                                                            |
| nace\_codes           | Códigos CNAE. Separados por punto y coma si hay varios.                                                                                                                                                                    |
| country\_constitution |                                                                                                                                                                                                                            |
| operations\_countries | Separados por punto y coma si hay varios.                                                                                                                                                                                  |
| is\_identified        | 0, si no hay identificación.                                                                                                                                                                                               |
| country\_address      |                                                                                                                                                                                                                            |
| address\_postal\_code |                                                                                                                                                                                                                            |
| address               |                                                                                                                                                                                                                            |
| address\_door         |                                                                                                                                                                                                                            |
| address\_district     |                                                                                                                                                                                                                            |
| address\_city         |                                                                                                                                                                                                                            |
| has\_branch\_offices  | 1 ó 0, si hay o no sucursales, respectivamente.                                                                                                                                                                            |
| adverse\_media        | Tipos de medios adversos, en el formato \[antiguo/nuevo] _\[grave/ligero]_\[alegaciones/acusaciones/convicciones]. Separados por punto y coma si hay varios. Ejemplo: antiguas\_denuncias\_graves; nuevas\_condenas\_leves |

{% hint style="warning" %}
! Asegúrese de que ninguno de los valores introducidos, incluido el nombre de la sociedad, tenga comas, ya que de lo contrario la importación no se ejecutará correctamente!
{% endhint %}

#### Ejemplo de archivo

{% file src="../../.gitbook/assets/organizations (2).csv" %}

### Archivo **de personas físicas**

* Debe contener una persona física por línea
* Campos aceptados (obligatorios en negrita):

| Campos                | Notas                                                                                                                                                                                                                      |
| --------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| id\_custom            | Identificador del cliente que usa su empresa. Tiene que ser único.                                                                                                                                                         |
| **name**              |                                                                                                                                                                                                                            |
| **vat\_number**       | Si no tiene el número de identificación fiscal de la persona, puede generar un identificador único, que debe tener una letra como primer carácter. Ej: ID659                                                               |
| responsible\_email    | Dirección de correo electrónico del usuario que se encargará del cuestionario del cliente. Debe ser un usuario de su organización.                                                                                         |
| invited\_email        | Correo electrónico de la persona a la que hay que invitar a completar el cuestionario. Nota: la invitación tendrá que ser enviada manualmente, después de la inserción.                                                    |
| email                 | Correo electrónico de la persona.                                                                                                                                                                                          |
| birth\_date           |                                                                                                                                                                                                                            |
| nationalities         | Separadas por punto y coma su hay varias.                                                                                                                                                                                  |
| country\_birth        |                                                                                                                                                                                                                            |
| address\_type         | Valores aceptados: residencia, residencia\_fiscal y sede.                                                                                                                                                                  |
| country\_address      |                                                                                                                                                                                                                            |
| is\_identified        | 0, si no hay identificación.                                                                                                                                                                                               |
| address\_postal\_code |                                                                                                                                                                                                                            |
| address               |                                                                                                                                                                                                                            |
| address\_door         |                                                                                                                                                                                                                            |
| address\_district     |                                                                                                                                                                                                                            |
| address\_city         |                                                                                                                                                                                                                            |
| adverse\_media        | Tipos de medios adversos, en el formato \[antiguo/nuevo] _\[grave/ligero]_\[alegaciones/acusaciones/convicciones]. Separados por punto y coma si hay varios. Ejemplo: antiguas\_denuncias\_graves; nuevas\_condenas\_leves |

#### Ejemplo de archivo

{% file src="../../.gitbook/assets/individuals (1).csv" %}

### **Archivo de relaciones entre personas físicas y jurídicas.**

* Debe contener una relación por línea
* Campos aceptados (obligatorios en negrita):

| Campos                         | Notas                                                                                                                                                                                                                                                                                                            |
| ------------------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **organization\_vat\_number**  | CIF de la sociedad para insertar las relaciones. La sociedad debe existir ya en el sistema.                                                                                                                                                                                                                      |
| **vat\_number**                | NIF/CIF de la relación a insertar. Esta persona/empresa debe existir ya en el sistema.                                                                                                                                                                                                                           |
| **position\_in\_organization** | Puede tener texto libre (por ejemplo: "Presidente", "Administrador", etc.), "", en el caso de que la relación sea como accionista o titular de derechos de voto, o " titular real " si es beneficiario. Si el vat\_number es de una organización, este campo debe tener obligatoriamente el valor "propietario". |
| capital\_percentage            | Sólo puede rellenarse si el valor del campo position\_in\_organization es "propietario" o "titular real". Nota: las separaciones decimales deben hacerse con ".", ej: 19.96                                                                                                                                      |
| voting\_rights\_percentage     | Sólo puede rellenarse si el valor del campo position\_in\_organization es "propietario" o "titular real". Nota: las separaciones decimales deben hacerse con ".", ej: 19.96                                                                                                                                      |

#### Ejemplo de archivo

{% file src="../../.gitbook/assets/relationships (1).csv" %}
