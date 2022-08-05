# Exportación de la validación

## Exportación de varias validaciones&#x20;

En la [página de validaciones](./), puede exportar las validaciones a diferentes formatos a través del botón "Exportar", que le da acceso a una ventana de exportación.

![Ventana de descarga de validaciones](<../../.gitbook/assets/exportar-validações (1).jpg>)

{% hint style="info" %}
### Sugerencias

* Puede exportar las validaciones incompletas, tras [aplicación de reglas](aplicacao-de-regras.md) y un primer intento de[ análisis manual,](analise-manual.md) para conocer los casos en los que necesita obtener más información.
* Puede exportar las validaciones _completas - identificadas_ para utilizarlas en los procesos internos de aceptación del cliente.
{% endhint %}

### Estructura del archivo exportado

El archivo exportado tiene las siguientes columnas:

* **Id**: identificador único para la [validación](../../glossario/glossario-aplicacao.md#validacao).&#x20;
* **Source**: Origen de la validación. Puede tener los valores “Manual” o “Automatic”, dependiendo si la [validación](../../glossario/glossario-aplicacao.md#validacao) fue agregada [manualmente](analise-manual.md) o a través de la [importación de validaciones](upload-de-validacoes.md), respetivamente.&#x20;
* **Name**: Nombre introducido por el usuario durante la [validación](../../glossario/glossario-aplicacao.md#validacao).&#x20;
* **Birth\_Date**: Fecha de nacimiento introducida por el usuario en la [validación](../../glossario/glossario-aplicacao.md#validacao): formato dd-mm-yyyy.
* **Country**: País introducido por el usuario durante la [validación](../../glossario/glossario-aplicacao.md#validacao).&#x20;
* **Identifiable\_Person**: 1 o 0, si la persona ha sido [clasificada](../../glossario/glossario-aplicacao.md#classificacao) como [persona identificable](../../glossario/glossario-aplicacao.md#pessoa-identificavel), o no, respectivamente.&#x20;
* **Id\_IPerson**: Identificador único relativo a la persona identificada cuando la decisión fue 1.
* **IPerson\_Classification**: Tipos de [clasificación](../../glossario/glossario-aplicacao.md#classificacao) de la persona identificable, separados por “;” en caso de varios. Pueden ser: “PEP”, “Family Member”, “Associate” o “Sanctioned X” donde X es la lista que identifica a la persona como sancionada.&#x20;
* **IPerson**: Información sobre la persona identificada. Este campo tiene la información separada por ";" siguiendo el formato: nombre; fecha de nacimiento: formato dd-mm-aaaa; [ocupaciones](../../glossario/glossario-aplicacao.md#ocupacao) relevantes: formato cargo, [órgano](../../glossario/glossario-aplicacao.md#orgao), [organización](../../glossario/glossario-aplicacao.md#organizacao); países relevantes: formato país, relación con el país.
* **Identifiable\_Country**: 1 o 0, si el país de validación está [sancionado](../../glossario/glossario-aplicacao.md#pais-sancionado), o no, respectivamente.&#x20;
* **Country\_Classification**: Listas de los países sancionados, separados por ';' cuando hay varios. Formato: “Sanctioned X” donde X es la entidad que identifica al país como sancionado.
* **Added\_At**: Fecha en que se agregó la [validación](../../glossario/glossario-aplicacao.md#validacao): formato dd-mm-yyyy HH:MM:SS.&#x20;
* **Added\_By**: Usuario que ha agregado la [validación](../../glossario/glossario-aplicacao.md#validacao): formato Nombre (correo electrónico).
* **Determined\_At**: Fecha en la que se determinó la [validación](../../glossario/glossario-aplicacao.md#validacao): formato dd-mm-yyyy HH:MM:SS.
* **Determined\_By**: Usuario que realizó la [validación](../../glossario/glossario-aplicacao.md#validacao): formato Nombre (correo electrónico).

