# Validaciones

Esta página le ayuda a determinar si sus clientes, prospectos o beneficiarios son [pe](../../glossario/glossario-aplicacao.md#pessoa-identificavel)rsonas indentificables, También sirve como depósito de toda la información relacionada con ellos. PEPData llama a cada nombre agregado por usted como [valida](../../glossario/glossario-aplicacao.md#validacao)ción.

![Tabla de validaciones](../../.gitbook/assets/image%20%2814%29.png)

Estados de adición, determinación y validación

las [valida](../../glossario/glossario-aplicacao.md#validacao)ciones se pueden agregar [manualmente](adicao-manual.md), una por una, o [automáticamente](upload-de-validacoes.md), lo que le permite agregar cientos de miles de [valida](../../glossario/glossario-aplicacao.md#validacao)ciones a la vez.

Una vez agregada, una [valida](../../glossario/glossario-aplicacao.md#validacao)ción tendrá su estado como _Incompleta_, lo que significa que aún no se ha determinado si corresponde a una [persona identific](../../glossario/glossario-aplicacao.md#pessoa-identificavel)able. Esta determinación, al igual que la adición, también puede hacerse [manualmente](analise-manual.md), una por una, o [automáticamente](aplicacao-de-regras.md), lo que permite determinar cientos de miles de [valida](../../glossario/glossario-aplicacao.md#validacao)ciones a la vez.Después de esta operación, el estado de [valida](../../glossario/glossario-aplicacao.md#validacao)ción cambiará _Completo_. 

Una validación _Completa_ podría ser: 

* Completa - Identificado: si ha habido correspondencia con una persona identificable de la base de datos de PEPData o su país está sancionado.
* Completa - No identificado: si no ha habido correspondencia con una persona identificable de la base de datos de PEPData y su país no está sancionado.

## Validaciones que necesitan atención

La base de datos de PEPData de [p](../../glossario/glossario-aplicacao.md#pessoa-identificavel)ersonas identificables se actualiza constantemente, por lo que cada día se agrega nuevas personas. También pueden ser retirados de la plataforma si ya no hay razón para seguir identificados, por ejemplo, si han pasado 12 meses desde que ocuparon un puesto relevante por última vez y no tienen otra [classifica](../../glossario/glossario-aplicacao.md#classificacao)ción.

En este sentido, cada vez que haya actualizaciones que requieran su atención, por ejemplo: una validación que usted identificó como PEP ya no es PEP, las validaciones afectadas se marcarán como "requieren atención".

{% hint style="info" %}
Esta señal no modifica en absoluto la decisión tomada anteriormente sobre la validación.   
Ejemplo: si una validación es _Completa_ - no identificada y una [pe](../../glossario/glossario-aplicacao.md#pessoa-identificavel)rsona identificable con el mismo nombre, la validación se marcará pero permanecerá como _Completada_ - _no identificada_.  
La aplicación, en este punto, sólo busca ayudar al usuario, dejando la decisión de determinar la validación de manera diferente de su parte.
{% endhint %}

Modificación y supresión de validaciones

Si desea cambiar una [valida](../../glossario/glossario-aplicacao.md#validacao)ción que ya está completa, puede pulsar el botón "✗", volverá a la _Incompleto._

Si desea eliminar una [valida](../../glossario/glossario-aplicacao.md#validacao)ción, siempre puede presionar el botón “🗑️".Tenga en cuenta que sólo puede eliminar las validaciones con estado _Incompleto_. Si desea eliminar una validación completa, debe cancelarla primero \(véase el paso anterior\).

## Filtros

En esta página, también hay filtros que permiten mostrar las [valida](../../glossario/glossario-aplicacao.md#validacao)ciones en cuanto a su estado u origen. Por defecto, todas las validaciones incompletas se muestran al abrir la página.

![Filtros de validaciones](../../.gitbook/assets/image%20%281%29.png)

Si usa los filtros para incluir  [valida](../../glossario/glossario-aplicacao.md#validacao)ciones _Completas_, aún puede ver su resultado a través de íconos:

* Avatar azul: significa que se encontró una [persona identific](../../glossario/glossario-aplicacao.md#pessoa-identificavel)able de la base de datos da PEPData. Puede pulsar este icono para abrir su perfil.
* Avatar translúcido: significa que no se ha encontrado ninguna coincidencia.
* Globo azul: significa que el país introducido en la validación está sancionado.
* Globo translúcido: significa que el país introducido en la validación no está sancionado

![Ejemplo de validaciones completas](../../.gitbook/assets/image%20%284%29.png)

