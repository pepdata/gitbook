# Exportação de validações

## Exportação de múltiplas validações 

Na [página de validações](./), pode exportar validações para diferentes formatos, através do botão “Exportar”, que lhe dá acesso a uma janela de exportação.

![Janela de download de valida&#xE7;&#xF5;es](../../.gitbook/assets/image%20%2812%29.png)

{% hint style="info" %}
### Sugestões

* Pode exportar as validações _Incompletas_, após a [aplicação de regras](aplicacao-de-regras.md) e uma primeira tentativa de [verificação manual](analise-manual.md), de forma a saber os casos em que precisa de obter mais informação.
* Pode exportar as validações _Completas - Identificadas_, para utilizar em processos internos de aceitação de clientes.
{% endhint %}

### Estrutura do ficheiro exportado

O ficheiro exportado possui as seguintes colunas:

* **Id**: identificador único relativo à [validação](../../glossario/glossario-aplicacao.md#validacao). 
* **Source**: Origem da validação. Pode ter os valores “Manual” ou “Automatic”, dependendo se a [validação](../../glossario/glossario-aplicacao.md#validacao) foi adicionada [manualmente](analise-manual.md) ou através da [importação de validações](importacao-de-validacoes.md), respetivamente. 
* **Name**: Nome introduzido, pelo utilizador, na [validação](../../glossario/glossario-aplicacao.md#validacao). 
* **Birth\_Date**: Data de nascimento introduzida, pelo utilizador, na [validação](../../glossario/glossario-aplicacao.md#validacao): formato dd-mm-yyyy.
* **Country**: País introduzido, pelo utilizador, na [validação](../../glossario/glossario-aplicacao.md#validacao). 
* **Identifiable\_Person**: 1 ou 0, caso a pessoa tenha sido [classificada](../../glossario/glossario-aplicacao.md#classificacao) como [pessoa identificável](../../glossario/glossario-aplicacao.md#pessoa-identificavel), ou não, respetivamente. 
* **Id\_IPerson**: Identificador único relativo à pessoa identificada, caso a decisão tenha sido 1. 
* **IPerson\_Classification**: Tipos de [classificação](../../glossario/glossario-aplicacao.md#classificacao) da pessoa identificada, separados por “;” no caso de vários. Estes podem ser: “PEP”, “Family Member”, “Associate” ou “Sanctioned X” em que X é a lista que identifica a pessoa como sancionada. 
* **IPerson**: Informação acerca da pessoa identificada. Este campo possui a informação separada por “;”, seguindo o seguinte formato: nome; data de nascimento: formato dd-mm-yyyy; [ocupações](../../glossario/glossario-aplicacao.md#ocupacao) relevantes: formato cargo, [órgão](../../glossario/glossario-aplicacao.md#orgao), [organização](../../glossario/glossario-aplicacao.md#organizacao); países relevantes: formato país, relação com país.
* **Identifiable\_Country**: 1 ou 0, caso a país da validação seja [sancionado](../../glossario/glossario-aplicacao.md#pais-sancionado), ou não, respetivamente. 
* **Country\_Classification**: Listas onde o país se encontra sancionado, separadas por “;” no caso de várias. Formato: “Sanctioned X” em que X é a entidade que identifica a país como sancionado.
* **Added\_At**: Data a que a [validação](../../glossario/glossario-aplicacao.md#validacao) foi adicionada: formato dd-mm-yyyy HH:MM:SS. 
* **Added\_By**: Utilizador que adicionou a [validação](../../glossario/glossario-aplicacao.md#validacao): formato Nome \(email\).
* **Determined\_At**: Data a que a [validação](../../glossario/glossario-aplicacao.md#validacao) foi determinada: formato dd-mm-yyyy HH:MM:SS.
* **Determined\_By**: Utilizador que determinou a [validação](../../glossario/glossario-aplicacao.md#validacao): formato Nome \(email\).

