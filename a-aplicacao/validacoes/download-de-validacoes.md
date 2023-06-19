# Exportação de validações

## Exportação de múltiplas validações&#x20;

Na [página de validações](./), pode exportar validações para diferentes formatos, através do botão “Exportar”, que lhe dá acesso a uma janela de exportação.

<figure><img src="../../.gitbook/assets/exportValidations (1).jpg" alt=""><figcaption><p>Janela para exportar validações</p></figcaption></figure>

{% hint style="info" %}
### Sugestões

* Pode exportar as validações _Incompletas_, após a [aplicação de regras](aplicacao-de-regras.md) e uma primeira tentativa de [verificação manual](analise-manual.md), de forma a saber os casos em que precisa de obter mais informação.
* Pode exportar as validações _Completas - Identificadas_, para utilizar em processos internos de aceitação de clientes.
{% endhint %}

### Estrutura do ficheiro exportado

O ficheiro exportado possui as seguintes colunas:

* **Type**: Tipo da validação. Pode ter os valores "Individual" ou "Organization" dependendo se a validação diz respeito a uma pessoa individual ou coletiva.
* **Id**: identificador único relativo à [validação](../../glossario/glossario-aplicacao.md#validacao).&#x20;
* **Id\_Custom**: Identificador personalizável inserido pelo utilizador.
* **Vatin**: Número de Identificação Fiscal associado à validação.
* **Source**: Origem da validação. Pode ter os valores “Manual” ou “Automatic”, dependendo se a [validação](../../glossario/glossario-aplicacao.md#validacao) foi adicionada [manualmente](analise-manual.md) ou através da [importação de validações](importacao-de-validacoes.md), respetivamente.&#x20;
* **Name**: Nome introduzido, pelo utilizador, na [validação](../../glossario/glossario-aplicacao.md#validacao).&#x20;
* **Birth\_Date**: Data de nascimento introduzida, pelo utilizador, na [validação](../../glossario/glossario-aplicacao.md#validacao): formato dd-mm-yyyy. Esta coluna é usada apenas para guardar informação de validações de pessoas individuais.
* **Country**: País introduzido, pelo utilizador, na [validação](../../glossario/glossario-aplicacao.md#validacao).
* **Country\_Address**: País de morada associado à validação. Esta coluna é usada apenas para guardar informação de validações de pessoas individuais.
* **Country\_Classifications**: Listas onde o país associado à validação se encontra sancionado, separadas por “;” no caso de várias. Formato: “Sanctioned X” em que X é a entidade que identifica a país como sancionado.
* **Id\_IPerson**: Identificador único relativo à pessoa identificada. Esta coluna é usada apenas para guardar informação de validações de pessoas individuais.&#x20;
* **IPerson\_Classifications**: Tipos de [classificação](../../glossario/glossario-aplicacao.md#classificacao) da pessoa identificada, separados por “;” no caso de vários. Estes podem ser: “PEP”, “Family Member”, “Associate” ou “Sanctioned X” em que X é a lista que identifica a pessoa como sancionada. Esta coluna é usada apenas para guardar informação de validações de pessoas individuais.&#x20;
* **IPerson\_Name**: Nome da pessoa identificada. Esta coluna é usada apenas para guardar informação de validações de pessoas individuais.
* **IPerson\_Birth\_Date**: Data de nascimento da pessoa identificada. Esta coluna é usada apenas para guardar informação de validações de pessoas individuais.
* **IPerson\_Occupations**: Ocupações associadas à pessoa identificada, separadas por “;” no caso de serem várias. Esta coluna é usada apenas para guardar informação de validações de pessoas individuais.
* **IPerson\_Family\_Relations**: Relações familiares entre a pessoa identificada e outras pessoas identificadas, separadas por “;” no caso de serem várias. Esta coluna é usada apenas para guardar informação de validações de pessoas individuais.
* **IPerson\_Associate\_Relations**: Relações onde a pessoa identificada surge como "Associada" de outras pessoas identificadas, separadas por “;” no caso de serem várias. Esta coluna é usada apenas para guardar informação de validações de pessoas individuais.
* **Id\_Iorganization**: Identificador único relativo à organização identificada. Esta coluna é usada apenas para guardar informação de validações de pessoas coletivas.
* **IOrganization\_Name**: Nome da organização identificada. Esta coluna é usada apenas para guardar informação de pessoas coletivas.
* **Added\_At**: Data a que a [validação](../../glossario/glossario-aplicacao.md#validacao) foi adicionada: formato dd-mm-yyyy HH:MM:SS.&#x20;
* **Added\_By**: Utilizador que adicionou a [validação](../../glossario/glossario-aplicacao.md#validacao): formato Nome (email).
* **Determined\_At**: Data a que a [validação](../../glossario/glossario-aplicacao.md#validacao) foi determinada: formato dd-mm-yyyy HH:MM:SS.
* **Determined\_By**: Utilizador que determinou a [validação](../../glossario/glossario-aplicacao.md#validacao): formato Nome (email).
