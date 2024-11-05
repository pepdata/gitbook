# Risco

As configurações de risco são uma ferramenta poderosa que lhe permite personalizar o cálculo do risco dos seus [clientes ](broken-reference)de acordo com as especificidades da sua organização e da área de negócio em que se insere.

Estas configurações centram-se em três componentes essenciais:

* As [fórmulas de risco](risco.md#formulas-de-risco)
* As [categorias de risco](risco.md#categorias-de-risco)
* Os [níveis de risco](risco.md#categorias-de-risco-1)

Apenas após a configuração destes três componentes é possível ativar a personalização do cálculo de risco para a sua organização.

<figure><img src="../../.gitbook/assets/risco.png" alt=""><figcaption></figcaption></figure>

### Fórmulas de risco

As fórmulas de risco são o centro da configuração de risco, permitindo-lhe especificar os ponderadores de risco a aplicar a cada um dos [fatores de risco](risco.md#fatores-de-risco) disponíveis e a aplicar um vasto conjunto de funções à computação do risco.

Existem dois tipos de fórmulas de risco:

* Para pessoas singulares: incluindo beneficiários efetivos e representantes
* Para pessoas coletivas

#### Fatores de risco

Para incorporar um fator de risco na sua fórmula basta arrastá-lo para a área de introdução da fórmula. Os fatores de risco encontram-se identificados em caixas a cinzento que se encontram sob área de introdução.

Existem fatores de risco simples, cujo valor se apura tendo em conta apenas um valor e compostos, cujo valor se apura tendo em conta a aplicação de uma função a múltiplos valores.

Estão disponíveis os seguintes fatores de risco na aplicação:

* Fórmula de risco para pessoas singulares
  * **Classificação da pessoa singular**: no caso de existência de várias classificações, os seus níveis de risco são somados ou é considerado apenas o nível mais elevado, consoante se definida no separador "Pessoas Identificáveis" a função Soma ou Máximo, respetivamente.
  * **Nacionalidades**: no caso de existência de várias, é considerado apenas o nível de risco mais elevado.
  * **Local de nascimento**
  * **País de residência**
  * **Existência de notícias adversas**
* Fórmula de risco para pessoas coletivas
  * **Setores de atividade**: no caso de existência de vários, é considerado apenas o nível de risco mais elevado.
  * **Países de operações**: no caso de existência de vários, é considerado apenas o nível de risco mais elevado.
  * **Classificação da pessoa coletiva**: no caso de existência de várias classificações, os seus níveis de risco são somados ou é considerado apenas o nível mais elevado, consoante se definida no separador "Pessoas Identificáveis" a função Soma ou Máximo, respetivamente.
  * **Representantes da pessoa coletiva**: no caso de existência de vários, é considerado apenas o nível de risco mais elevado.
  * **Titulares de Órgãos de Administração/Gestão:** no caso de existência de vários, é considerado apenas o nível de risco mais elevado.
  * **Titulares de Ações/Direitos de voto:** no caso de existência de vários, é considerado apenas o nível de risco mais elevado.
  * **Beneficiários efetivos**: no caso de existência de vários, é considerado apenas o nível de risco mais elevado.
  * **País de constituição**
  * **País da sede**
  * **Data de fundação**
  * **Existência de notícias adversas**

#### Sintaxe da fórmula

* As fórmulas utilizadas têm a mesma base que as fórmulas de Excel. Como tal, devem começar com o símbolo "=".
* Estão disponíveis todas as funções que existem no Excel, devendo estas ser escritas em maiúsculas. Ex: SUM(), MAX().
* A separação de valores deve ser feita utilizando a vírgula.\
  Ex: MAX(1, 2).
* As casas decimais devem ser especificadas com um ponto final.\
  Ex: 1.2.

### Categorias de risco

A computação do valor do risco não possui significado próprio, sendo necessário enquadrá-lo nos intervalos das categorias de risco, que podem também ser definidos por utilizador.

A definição destes intervalos pode ser efetuada no separador "Categorias".

Para além dos intervalos, é ainda possível definir um estado de aprovação automático que aprova ou rejeita o cliente consoante a categoria de risco no momento da submissão.

### Níveis de risco

Os níveis de risco são os componentes mais elementares do cálculo do risco.

Estes podem ser definidos para cada um dos [fatores de risco](risco.md#fatores-de-risco) nos respetivos separadores.

{% hint style="success" %}
A modelação do risco é uma área técnica e complexa, sendo importante o envolvimento de especialistas que o poderão ajudar em todas as etapas do processo. Caso tenha alguma questão, não hesite em [contactar-nos](../../outros/contactos.md).
{% endhint %}
