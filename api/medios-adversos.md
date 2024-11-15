# Medios Adversos

## Obtener Medios Adversos

<mark style="color:green;">`POST`</mark> `https://www.pepdata.com/api/get_adverse_media`

Endpoint para la obtención de medios adversos.

#### Headers

| Name                                            | Type   | Description     |
| ----------------------------------------------- | ------ | --------------- |
| Authorization<mark style="color:red;">\*</mark> | string | key \[API\_KEY] |

#### Request Body

| Name                                           | Type   | Description                           |
| ---------------------------------------------- | ------ | ------------------------------------- |
| search\_term<mark style="color:red;">\*</mark> | string | Nombre de la entidad/persona a buscar |

{% tabs %}
{% tab title="200: OK Información de los medios adversos obtenida con éxito." %}
```
{
    "version": 0.1,
    "timestamp": 1683734308978,
    "data": {
        "icij_adverse_media": {
            "items": [
                {
                    "entity": "Lisa Fidalgo Corte-Real",
                    "source": "Panama Papers"
                }
            ],
        },
        "google_adverse_media": {
            "items": [
                {
                    "title": "Lisa Fidalgo Corte-Real será juzgada por...",
                    "description": "Lisa Fidalgo Corte-Real será juzgada por corrupción...",
                    "source": "https://test-link.pt",
                    "date": "2023-04-14"
                }
            ],
        },
        "judicial_processes": {
            "items": [
                {
                    "entry_number": 12345678,
                    "entry_date": "2022-04-13",
                    "distribution_date": "2022-04-13",
                    "end_date": "2023-04-13",
                    "organ": "Juzgado de Ejecución de Madrid",
                    "process_code": "000/00.0A0AGD",
                    "process_value": "12460.27",
                    "observations": "Ejecución Ordinaria (Ejecución Ag.) Entrega Electrónica - Ref 12345678"
                }
            ],
        }
    }
}
```
{% endtab %}

{% tab title="400: Bad Request El campo 'search_term' es obligatorio" %}


```json
{
    "message": {
        "version": 0.1,
        "timestamp": 1696241312398,
        "message": "El campo 'search_term' es obligatorio."
    }
}
```
{% endtab %}
{% endtabs %}

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
