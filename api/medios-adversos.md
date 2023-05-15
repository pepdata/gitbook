# Medios Adversos

{% swagger method="post" path="" baseUrl="https://www.pepdata.com/api/get_adverse_media" summary="Obtener Medios Adversos" %}
{% swagger-description %}
Endpoint para la obtención de medios adversos.
{% endswagger-description %}

{% swagger-parameter in="header" name="Authentication" required="true" type="string" %}
key [API_KEY]
{% endswagger-parameter %}

{% swagger-parameter in="body" name="search_term" required="true" type="string" %}
Nombre de la entidad/persona a buscar
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Información de los medios adversos obtenida con éxito." %}

{% endswagger-response %}

{% swagger-response status="400: Bad Request" description="El campo 'search_term' es obligatorio" %}

{% endswagger-response %}
{% endswagger %}

{% hint style="info" %}
La consulta incluye: **búsquedas en motores de búsqueda** (asociadas con el tema PBCFT), **procesos judiciales y listas de filtraciones** (Pandora Papers, Paradise Papers, Bahamas Leaks, Panama Papers y Offshore Leaks).



Las leyendas se referirán a los campos disponibles en cada una de las diferentes fuentes.
{% endhint %}

### Leyenda ICIJ (Consorcio Internacional de Periodistas de Investigación)

* entity: nombre de la entidad
* source: lista donde se encontró la información de la entidad

### Leyenda de Motores de búsqueda (Goolge)&#x20;

* title: título de la noticia
* description: descripción de la noticia
* source: enlace a la fuente de noticias
* date: fecha de la noticia&#x20;

### Leyenda de procesos judiciales

* entry\_number: número de entrada del proceso
* entry\_date: fecha de entrada
* distribution\_date: fecha de distribución
* end\_date: fecha de finalización
* organ: unidad orgánica
* process\_value: código de proceso
* process\_value: valor del proceso (en euros)
* observations: especies y observaciones
