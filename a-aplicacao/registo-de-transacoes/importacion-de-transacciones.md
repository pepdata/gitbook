# Importación de Transacciones

La nueva importación de clientes le permite, de forma fácil y rápida, cargar su cartera de clientes en la plataforma PEPData, creando automáticamente un registro para cada cliente.

Para ello, divida la información a importar en 3 archivos distintos:

* Transacciones de bienes
* Transacciones de servicios
* Transacciones de suscripción de Fondos/Oportunidades

Después de crear uno o varios de estos archivos, podrá proceder a la importación mediante el icono "Importar registros", presente en la página "Registro de transacciones".

### Detalles de los archivos a importar

#### Detalles generales

* La primera línea debe contener el nombre de las columnas que representan la información a importar
* Extensión .txt o .csv
* Limitado a 700.000 líneas por importación

#### Fichero de transacciones de bienes

* Debe contener una organización por línea
* Propiedades aceptadas (obligatorias en negrita):

| Campos                         |                                                                                    |
| ------------------------------ | ---------------------------------------------------------------------------------- |
| **name**                       |                                                                                    |
| id\_custom                     | Identificador de la transacción utilizado por su organización. Tiene que ser único |
| description                    |                                                                                    |
| value\_in_\__euros             |                                                                                    |
| payment\_method                | Tipos de formato de medio de pago: efectivo/cuotas                                 |
| installment\_in\_euros         |                                                                                    |
| installments\_frequency        | Frecuencia del pago:mensual, anual, trimestral, semestral, quincenal, otro.        |
| installments\_frequency\_other |                                                                                    |
| seller\_entity                 | Entidad de pago: propio/externo                                                    |
| responsible\_email             |                                                                                    |
| acquisition\_purpose           |                                                                                    |
| observations                   |                                                                                    |

{% hint style="warning" %}
Asegúrese de que ninguno de los valores introducidos, incluido el nombre de la transacción, tenga comas, de lo contrario la importación no se realizará correctamente.
{% endhint %}

#### Archivo ejemplo

{% file src="../../.gitbook/assets/transactions goods.txt" %}

### Archivo de transacciones de servicio

* Debe contener una organización por línea
* Propiedades aceptadas (obligatorias en negrita):

| Campos                         | Notas                                                                                         |
| ------------------------------ | --------------------------------------------------------------------------------------------- |
| **name**                       |                                                                                               |
| id\_custom                     | id\_custom Identificador de la transacción utilizada por su organización. Debe de ser única.  |
| description                    |                                                                                               |
| occurrence                     | Tipos de servicio: puntual/recurrente                                                         |
| frequency                      | Frecuencia de pago: mensual, anual, trimestral, semestral, quincenal, otro                    |
| value\_in\_euros               |                                                                                               |
| provision\_start\_date         |                                                                                               |
| provision\_end\_date           |                                                                                               |
| provision\_date                |                                                                                               |
| payment\_method                | Formato del tipo de pago: al contado/cuotas                                                   |
| installment\_in\_euros         |                                                                                               |
| installments\_frequency        | Frecuencia de los pagos de las cuotas: mensual, anual, trimestral, semestral, quincenal, otro |
| installments\_frequency\_other |                                                                                               |
| seller\_entity                 | Entidad vendedora: propia/externa                                                             |
| responsible\_email             |                                                                                               |
| acquisition\_purpose           |                                                                                               |
| observations                   |                                                                                               |

{% hint style="warning" %}
Asegúrese de que ninguno de los valores introducidos, incluido el nombre de la transacción, tenga comas, de lo contrario la importación no se realizará correctamente.
{% endhint %}

#### Archivo ejemplo

{% file src="../../.gitbook/assets/transactions services.txt" %}

### ad

### Fichero de transacciones de fondos/oportunidades

* Debe contener una organización por línea
* Propiedades aceptadas (obligatorias en negrita):

| Campos                                       | Notas                                                                               |
| -------------------------------------------- | ----------------------------------------------------------------------------------- |
| **transaction\_name**                        |                                                                                     |
| id\_custom                                   | Identificador de la transacción utilizado por su organización. Tiene que ser único. |
| **fund\_name**                               |                                                                                     |
| value\_in\_euros                             |                                                                                     |
| iban                                         |                                                                                     |
| swift                                        |                                                                                     |
| number\_of\_subscribed\_participation\_units |                                                                                     |
| contact\_email                               |                                                                                     |

{% hint style="warning" %}
Asegúrese de que ninguno de los valores introducidos, incluido el nombre de la transacción, tenga comas, de lo contrario la importación no se realizará correctamente.
{% endhint %}

#### Archivo ejemplo

{% file src="../../.gitbook/assets/transactions funds.txt" %}