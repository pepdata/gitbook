# Visión general

La API PEPData puede utilizarse para buscar y realizar operaciones relacionadas con las [validaciones](../a-aplicacao/validacoes/).&#x20;

Su documentación es técnica y está orientada a los programadores. Si sólo quiere leer sobre la aplicación, puede hacerlo en la [sección correspondiente](../a-aplicacao/validacoes/).

## Autenticación

La autenticación a través de la PEPData API v0.1 sólo puede realizarse a través de la clave de autenticación.

Cada usuario solo puede ver y cambiar su clave en su perfil. Se puede cambiar una clave, pero la nueva clave invalidará la anterior. Por lo tanto, sólo hay una clave activa en todo momento.

La clave activa debe utilizarse en la sección `Headers` de HTTP request. Por ejemplo:

```bash
curl -H "Authorization: key [API_KEY]" https://www.pepdata.com/api/[endpoint_url]
```

{% hint style="info" %}
Su clave de autenticación tiene los mismos privilegios que su usuario. Por lo tanto, es esencial que la mantenga segura. No comparta su clave con terceros: tenga especial cuidado de no enviarla por correo electrónico o ponerla en un depósito de código.
{% endhint %}

## Estructura

Toda la comunicación con la API debe realizarse a través de objetos JSON, con las respuestas siempre codificadas en UTF-8.

En caso de éxito, la API seguirá la siguiente estructura de respuesta:

```bash
{
    "data": {...},
    "version": "versão da API",
    "timestamp": X
}
```

### Leyenda

* fecha: objeto que contiene la información solicitada.
* versión: versión actual de la API.
* timestamp: la fecha en la que se produjo la respuesta del servidor, como el número de milisegundos desde el 1 de enero de 1970 00:00:00 UTC.

## Fechas

Todas las fechas utilizadas, a excepción  del campo _timestamp_ mencionado anteriormente, siguen las siguientes normas:

* Las fechas con el sufijo "\_at" representan unix millisecond timestamps (milisegundos desde el 1 de enero de 1970 00:00:00 UTC)
* Las fechas con el sufijo "\_date" representan calendar dates en formato [ISO 8601](https://en.wikipedia.org/wiki/ISO\_8601) YYYY-MM-DD.

## Paginación

Algunos endpoints devuelven resultados en forma paginada. En este caso, el formato de objeto de parámetro _data (datos)_ irá será el siguiente:

```bash
{
    "items": [
        ...
    ],
    "page": X,
    "max_results_per_page": Y,
    "total": Z
}
```

### Leyenda

* elementos: los elementos correspondientes a la información solicitada.
* page: número de la página a la que pertenecen los elementos.
* max\_results\_per\_page: número máximo de resultados por página.
* total: el número de resultados existentes.

## Errores

PEPData utiliza códigos de respuesta HTTP convencionales para indicar el éxito o el fallo de cada solicitud de la API.

Como regla general:

* Los códigos en el intervalo 2xx indican éxito.
* Los códigos del intervalo 4xx indican un uso incorrecto o incompleto de los parámetros (ejemplos: se ha omitido un parámetro obligatorio, el endpoint no existe, el token de autenticación no es válido).
* Los códigos en el intervalo 5xx indican un error en los servidores de PEPData.

PEPData devuelve el mensaje de error con el siguiente formato:

```bash
{
    "message": "Mensagem de erro",
    "version": "versão da API",
    "timestamp": X 
}
```

{% hint style="info" %}
Excepciones: Los errores 401, 403, 404 y 500 deben ser procesados como tales y la respuesta debe ser ignorada.
{% endhint %}

## Configuración para Postman

Si desea realizar una prueba rápida de los endpoints de la API PEPData, hemos creado una configuración para [Postman](https://www.postman.com/downloads/) que contiene algunos ejemplos básicos.

{% file src="../.gitbook/assets/pepdata-public-api.postman_collection (1).json" %}
PEPData API Configuration
{% endfile %}

Una vez importada la configuración en Postman, deberá establecer la variable `API_KEY` en la pestaña Autorización.
