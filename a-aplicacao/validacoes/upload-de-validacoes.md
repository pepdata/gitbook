# Importación de validaciones

En la [página de valida](./)ciones, puede importar validaciones automáticamente utilizando el botón "Importar validaciones", que le da acceso a un explorador que le permite elegir el archivo que contiene las [valida](../../glossario/glossario-aplicacao.md#validacao)ciones para agregar. Para que el archivo sea interpretado correctamente por la aplicación, debe seguir una serie de especificaciones, descritas a continuación.

Una vez finalizada la carga de archivos, todos las nuevas [valida](../../glossario/glossario-aplicacao.md#validacao)ciones aparecerán  en la [página de valida](./)ciones.

{% hint style="info" %}
### ¿Cuáles son las especificaciones del archivo de carga?

* Sólo se permiten las extensões .csv ou .txt.
* Una [valida](../../glossario/glossario-aplicacao.md#validacao)ción por línea.
* Una [valida](../../glossario/glossario-aplicacao.md#validacao)ción deve seguir o formato: Nome, Data de nascimento, País. debe seguir el formato: Nombre, Fecha de nacimiento, País. Cualquiera de los siguientes ejemplos representa una validación en el formato correcto:  André Pinheiro, 31-12-1980, Portugal  Ricardo Sousa Vieira Armando Rui Pinto, , Rusia Armando Tavares Rocha Tenga en cuenta que, en el segundo ejemplo, se agregó una coma adicional porque no hay fecha de nacimiento.
* La fecha de nacimiento debe seguir el formato dd-mm-yyyy ou dd/mm/yyyy. 
* Limitado a 700.000 líneas/[valida](../../glossario/glossario-aplicacao.md#validacao)ciones por archivo.  
* A codificación del archivo debe ser utf-8 ou ANSI 
{% endhint %}

{% hint style="info" %}
### No puedo cargar el archivo, ¿qué puedo hacer?

* Asegúrese que el nombre, la fecha de nacimiento y el país no están delimitados por "o". Estos valores no deben ser delimitados.
* Comprueba que al abrir el archivo no aparecen caracteres como "" en lugar de caracteres acentuados o "ç". Si esto sucede, hay un problema de codificación que puede intentar resolver siguiendo lo que se describe [aqu](upload-de-validacoes.md#codificacao-incorreta-do-ficheiro)í.
* Si los puntos anteriores no se aplican y sigue recibiendo un mensaje de error cada vez que intenta cargar, puede haber un problema de codificación que puede intentar resolver siguiendo los pasos descritos [aquí](upload-de-validacoes.md#codificacao-incorreta-do-ficheiro).
* Si no se aplica ninguna de las anteriores, comuníquese con PEPData
{% endhint %}

{% hint style="info" %}
### ¿Qué debo saber antes de introducir la información?

#### Nombre

* Como mínimo, sólo se permiten los nombres propios con 2 nombres y la fecha de nacimiento. Si no tiene información sobre la fecha de nacimiento, tiene que introducir al menos 3 nombres.  Estos requisitos mínimos existen para garantizar que el sistema tenga la capacidad de sugerir resultados relevantes cuando quiera analizar si la persona es [identific](../../glossario/glossario-aplicacao.md#pessoa-identificavel)able. 
* Todos los [caracteres latinos](https://en.wikipedia.org/wiki/ISO/IEC_8859-1), a acentuación y las mayúsculas **son** compatibles y no cambian los resultados mostrados en el proceso de análisis. Por lo tanto, puede introducir el nombre en el formato que más le convenga.  Por ejemplo: "Ines Marçal Romão" equivaldrá a introducir "ines marcal romao".
* Aparte de los mencionados, sólo se aceptan espacios \(" "\), guiones \("-"\) o apóstrofes \(" ' "\).
* Las [partículas](https://www.irn.mj.pt/IRN/sections/irn/a_registral/registo-civil/docs-do-civil/dar-o-nome/) que existen en el nombre, \(como "de", "da", "y", etc.\) no cambian los resultados presentados en el proceso de análisis. Por ejemplo: "Rui Miguel do Rio" equivaldrá a introducir "Rui Miguel Rio".
* Las abreviaturas son compatibles. Sin embargo, éstas no pueden ir precedidas de un punto.Por ejemplo: "Rui M Rio" podría resultar en el nombre "Rui Miguel Rio".
* Todos los puntos anteriores se han aplicado para que el proceso sea lo más sólido posible. No obstante, le recomendamos que intente introducir nombres lo más parecidos al original.
{% endhint %}

{% hint style="info" %}
#### País

* Este campo se analiza de forma independiente, y sólo se comprueba si el país introducido está [sancionado](../../glossario/glossario-aplicacao.md#pais-sancionado). Así, este campo puede tener diferentes significados, como: origen de los fondos del cliente, lugar de residencia fiscal o cualquier otro que considere relevante
* Hay varias formas distintas de escribir el nombre de cada país. La aplicación PEPData admite cualquier valor [ISO 3166](https://en.wikipedia.org/wiki/ISO_3166), nombre común o nombre oficial de cada país. Nota: si el país asociado a una [valida](../../glossario/glossario-aplicacao.md#validacao)ción es sancionado, la [valida](../../glossario/glossario-aplicacao.md#validacao)ción heredará esta clasificación, independientemente de que corresponda a una [persona identific](../../glossario/glossario-aplicacao.md#pessoa-identificavel)able. Una [valida](../../glossario/glossario-aplicacao.md#validacao)ción puede tener varias [clasifica](../../glossario/glossario-aplicacao.md#classificacao)ciones distintas. 
{% endhint %}

## Asistente de correción

Caso ocorra um problema com os dados a introduzir, irá aparecer um assistente de correção que irá identificar os erros encontrados no ficheiro. O assistente de correção segue a seguinte lógica sequencial:

1. Validação dos dados introduzidos: nome, data e país
2. Verificação da existência de duplicados: caso já tenha adicionado uma determinada validação no passado, os dados a introduzir serão considerados como duplicados. O utilizador poderá depois optar por ignorar este tipo de erro.

{% hint style="info" %}
Nota: Por limitação de espaço, caso exista uma elevada quantidade de erros ou de duplicados, estes podem não ser todos mostrados no assistente de correção. Terá de efetuar a sua correção e refazer o upload para ver os erros restantes.
{% endhint %}

## Soluções para possíveis problemas 

### Codificação incorreta do ficheiro

Um [ficheiro de texto](https://pt.wikipedia.org/wiki/Arquivo_de_texto) contém informação que apenas consegue ser corretamente interpretada caso se saiba a sua codificação. Apenas deste modo um computador consegue "compreender" o que nele se encontra escrito, podendo distinguir cada um dos caracteres.

Infelizmente, não existe uma codificação universal que seja utilizada em todos os computadores, o que poderá levar a dificuldades na interpretação de alguns ficheiros de texto, com especial relevância nos caracteres com acentos. Caso um computador utilize uma codificação que não corresponde à do ficheiro, poderá interpretar o caracter "é" como "", por exemplo, não conseguindo compreender o seu significado.

Embora o sistema da PEPData tente determinar a codificação do ficheiro carregado, nem sempre este processo é infalível, pelo que o problema descrito poderá ocorrer. Caso tal aconteça, irá receber uma mensagem de erro que o informa que apenas um determinado número de caracteres é reconhecido pelo sistema sempre que tente realizar o upload do mesmo ficheiro.

Neste caso, sugerimos as seguintes soluções:

**Bloco de Notas/Notepad do Windows** 

1. Abrir o ficheiro em questão. 
2. Clicar em Ficheiro/File -&gt; Guardar Como... /Save As... 
3. Alterar Codificação/Encoding de UTF-8 para ANSI ou de ANSI para UTF-8. Esta opção encontra-se à esquerda do botão Guardar/Save.
4. Guardar.
5. Voltar a fazer upload do ficheiro na plataforma da PEPData.

\*\*\*\*[**Notepad++**](https://notepad-plus-plus.org/)\*\*\*\*

1. Abrir o ficheiro em questão. 
2. Codificação/Encoding -&gt; Converter para ANSI ou UTF-8, dependendo da codificação atual.
3. Guardar.
4. Voltar a fazer upload do ficheiro na plataforma da PEPData.



