# Visão geral

A API da PEPData pode ser utilizada para fazer [pesquisas](../a-aplicacao/pesquisa.md) e realizar operações relativas às [validações](../a-aplicacao/validacoes/). 

A sua documentação é técnica e orientada para programadores. Caso apenas pretenda ler sobre a aplicação poderá fazê-lo na [secção correspondente](../a-aplicacao/validacoes/).

## Autenticação

A autenticação através da PEPData API v0.1 apenas pode ser realizada via chave de autenticação. 

Cada utilizador pode ver e alterar a sua chave no seu perfil. Uma chave pode ser alterada mas a nova irá invalidar a anterior. Só existe, por isso, uma chave ativa a cada momento.

O chave ativa deve ser utilizado na secção `Headers` do HTTP request. Exemplificando:

```bash
curl -H "Authorization: key [API_KEY]" https://www.pepdata.com/api/[endpoint_url]
```

{% hint style="info" %}
A sua chave de autenticação possui os mesmos privilégios que o seu utilizador. É por isso essencial que a mantenha segura. Não partilhe a sua chave com terceiros: tenha especial atenção para não a enviar por email nem a colocar num repositório de código.
{% endhint %}

## Estrutura

Toda a comunicação realizada com a API deve ser realizada através de objetos JSON, estando as respostas sempre codificadas em UTF-8.

No caso de sucesso, API irá seguir a seguinte estrutura de resposta:

```bash
{
    "data": {...},
    "version": "versão da API",
    "timestamp": X
}
```

### Legenda

* data: objeto que contém a informação requisitada.
* version: versão atual da API.
* timestamp: data a que a resposta do servidor foi efetuada, sob a forma de número de milisegundos desde 1 de Janeiro de 1970 00:00:00 UTC.

## Datas

Todas as datas utilizadas, com exceção do campo _timestamp_ referido anteriormente, seguem os seguintes padrões:

* Datas com o sufixo "\_at" representam unix millisecond timestamps \(milissegundos desde 1 de Janeiro de 1970 00:00:00 UTC\)
* Datas com o sufixo "\_date" representam calendar dates no formato [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601) YYYY-MM-DD.

## Paginação

Alguns endpoints devolvem resultados de forma paginada. Neste caso, a formatação do objeto do parâmetro _data_ irá ser a seguinte:

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

### Legenda

* items: os items correspondentes à informação solicitada.
* page: número da página à qual os items pertencem.
* max\_results\_per\_page: número máximo de resultados por página.
* total: o número de resultados existentes.

## Erros

A PEPData utiliza os códigos de resposta HTTP convencionais para indicar o sucesso ou a falha de cada API request.

Como regra geral:

* Códigos no intervalo `2xx` indicam sucesso.
* Códigos no intervalo `4xx` indicam uma utilização incorreta ou incompleta dos parâmetros.\(exemplos: um parâmetro obrigatório foi omitido, o endpoint não existe, o token de autenticação não é válido\).
* Códigos no intervalo `5xx` indicam um erro nos servidores da PEPData.

A PEPData devolve a mensagem de erro com o seguinte formato:

```bash
{
    "message": "Mensagem de erro",
    "version": "versão da API",
    "timestamp": X 
}
```

{% hint style="info" %}
Exceções: Erros 401, 403, 404 e 500 devem ser processados como tal, devendo a resposta ser ignorada.
{% endhint %}

## Configuração para o Postman

Caso deseje efetuar um teste rápido aos endpoints da API da PEPData, criámos uma configuração para o [Postman](https://www.postman.com/downloads/) que contém alguns exemplos básicos.

{% file src="../.gitbook/assets/pepdata-public-api.postman\_collection \(1\).json" caption="PEPData API Configuration" %}

Uma vez importada a configuração no Postman, irá precisar de definir a variável `API_KEY` no separador de Autorização.

