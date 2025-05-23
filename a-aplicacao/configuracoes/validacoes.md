# Validações

Nesta secção é possível ativar ou desativar opções auxiliares aos processos de validação, bem como ocultar ou mostrar janelas de informação.

## Palavras-chave de Adverse Media

Nesta secção pode adicionar, editar ou eliminar palavras-chave que pretenda utilizar nas pesquisas adverse media. Por defeito, a palavra-chave atribuída é "crime".

Para saber como funciona a monitorização de adverse media nas validações, consulte a página de [monitorização](../validacoes/monitorizacao.md).

## Pesquisa e Regras

Nesta secção é possível ativar ou desativar as [regras de validação](../validacoes/aplicacao-de-regras.md#regras-de-validacao) e definir o [threshold de validação](validacoes.md#threshold-de-validacao).

### Threshold de validação

O threshold de validação é o valor acima do qual se considera um [grau de semelhança](../../glossario/glossario-aplicacao.md#grau-de-semelhanca) como elevado. Este permite-lhe identificar automaticamente todos os nomes com apenas uma correspondência e com [grau de semelhança](../../glossario/glossario-aplicacao.md#grau-de-semelhanca) superior ao valor definido.

O valor pré-definido para o threshold de validação é de 95, podendo o seu valor ser ajustado entre 90 e 100. Este valor é partilhado por todos os membros da sua organização.

{% hint style="info" %}
Ajuste o valor do threshold de validação consoante as suas preferências.\
Utilizar um valor mais elevado permite-lhe ter maior certeza na identificação mas deixará mais [validações](../../glossario/glossario-aplicacao.md#validacao) por completar. O inverso acontecerá para valores mais baixos.
{% endhint %}

### Threshold de não correspondência

O threshold de não correspondência é o valor usado para filtrar a lista de correspondências. Todos os nomes que possuam [grau de semelhança](../../glossario/glossario-aplicacao.md#grau-de-semelhanca) inferior ao threshold de não correspondência serão ignorados no processo de identificação automática das validações.&#x20;

## Monitorização

Nesta secção é possível ativar a monitorização de adverse media ou de processos judiciais nas suas validações. Pode ainda determinar o intervalo de monitorização (em dias) para que a plataforma vá buscar novas informações com o intervalo definido.

Se pretender saber mais sobre a monitorização de adverse media ou de processos judiciais nas validações, consulte a página [monitorização](../validacoes/monitorizacao.md).
