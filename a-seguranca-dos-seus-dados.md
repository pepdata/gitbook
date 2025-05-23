# A segurança dos seus dados

A segurança e privacidade dos seus dados é prioridade máxima da PEPData.\
Não referimos isto de animo leve nem apenas para parecer bem: compreendemos a sensibilidade da informação que coloca na nossa plataforma e assumimos o nosso dever de protege-la.

É por essa razão que:

* Restringimos ao máximo o acesso aos seus dados
  * Apenas o próprio utilizador, os membros da sua organização e o DPO (encarregado da proteção de dados) da PEPData têm acesso aos dados que insere na plataforma.
  * O DPO da PEPData apenas pode aceder aos seus dados com a sua autorização, para fins de suporte.
  * Não partilhamos os seus dados com nenhuma organização terceira, independentemente do contrato ou protocolo em que a sua utilização da plataforma se insere.
  * Não partilhamos, sequer, os seus dados internamente na PEPData. Todo o desenvolvimento da aplicação é feita utilizando dados anonimizados.
  * Todos os acessos à sua conta são monitorizados e registados.
* Utilizamos as ferramentas ao nosso dispor para aumentar a segurança dos nossos sistemas
  * Todas as interações que tem com o site da PEPData são feitas através de [HTTPS](https://en.wikipedia.org/wiki/HTTPS) de forma a assegurar que a informação é transmitida de forma encriptada.
  * Todas as cópias de segurança são realizadas recorrendo a encriptação.
  * Todos os nossos servidores dispõe de _firewall_ para apenas permitir a entrada e saída do tráfego pretendido.
  * O acesso aos nossos servidores é altamente restrito e é apenas efetuado a partir de [SSH](https://pt.wikipedia.org/wiki/Secure_Shell).
  * Não guardamos a sua password, utilizamos um sistema de _hash_ e [_salt_](https://pt.wikipedia.org/wiki/Sal_\(criptografia\)).
  * Monitorizamos continuamente os nossos sistemas.
* Trabalhamos continuamente para aumentar a segurança dos nossos sistemas
  * Todos os nossos programadores têm formação contínua na área de segurança informática.
  * Todas as alterações à plataforma são revistas por, pelo menos, outra pessoa antes de serem colocadas em ambiente de produção.
  * Contratamos empresas terceiras que testam e auditam continuamente a segurança dos nossos sistemas e processos.
* Residência dos dados
  * Os dados inseridos na plataforma residem em países da União Europeia, garantindo a adequação com o Regulamento Geral sobre a Proteção de Dados (RGPD). Os servidores de produção residem em Dublin, no _datacenter_ da Amazon AWS e os servidores de backup residem em Amsterdão, no _datacenter_ da Backblaze. Ambos os fornecedores têm certificados SOC-2.

## FAQ

<details>

<summary> A PEPData consegue aceder ou tratar dados pessoais sem autorização?</summary>

Não. A PEPData atua em total conformidade com o Regulamento Geral sobre a Proteção de Dados (RGPD) e com a Lei n.º 83/2017 (Lei de Prevenção do Branqueamento de Capitais e Financiamento do Terrorismo - LPBC/FT).

</details>

<details>

<summary>Que dados utiliza a PEPData?</summary>

A nossa base de dados contém:

* Pessoas Politicamente Expostas (PEP)
* Cargos públicos
* Pessoas estreitamente associadas
* Entidades sancionadas

Todas estas informações são públicas e recolhidas de fontes oficiais (como o Diário da República e portais institucionais). Não há qualquer expetativa de confidencialidade nestes dados, pois referem-se a cargos e funções públicos, reconhecidos legalmente.

</details>

<details>

<summary>Quem pode aceder à plataforma?</summary>

O acesso é restrito a clientes contratualmente vinculados. Cada utilizador:

* Tem autenticação segura
* É registado em logs invioláveis
* Acede à plataforma em ambiente protegido

</details>

<details>

<summary>Em que base legal assenta o tratamento de dados?</summary>

A PEPData baseia-se no artigo 6.º, n.º 1, alínea f) do RGPD — interesse legítimo em fornecer aos clientes uma ferramenta essencial para cumprirem as suas obrigações legais (LPBC/FT). A PEPData não trata:

* Dados sensíveis (artigo 9.º do RGPD)
* Informações sobre condenações penais (artigo 10.º do RGPD)

</details>

<details>

<summary>Como funciona a consulta de listas públicas de processos judiciais?</summary>

A plataforma permite apenas a consulta ad hoc (sem recolha nem armazenamento) de listas públicas disponíveis em plataformas do Ministério da Justiça, como:

* Citius (tribunais judiciais comuns)
* SITAF (tribunais administrativos e fiscais)

Estes dados são de acesso público, e a consulta é meramente referencial — não constituindo tratamento de dados pessoais, nem requerendo consentimento.

</details>

<details>

<summary>A PEPData pode tratar dados errados ou sem consentimento?</summary>

Não. Em nenhum caso a PEPData pode ou consegue fazê-lo. A PEPData:

* Não tem registo ou vínculo com os titulares dos dados pesquisados
* Não trata nem divulga os seus dados
* Não pode confirmar os parâmetros da pesquisa feita pela entidade cliente
* Não é responsável pela confrontação dos resultados obtidos com os dados pessoais

</details>

<details>

<summary>Quem pode alterar ou remover dados dessas listas?</summary>

Os direitos de acesso, retificação ou eliminação de dados devem ser exercidos junto do Ministério da Justiça ou dos tribunais competentes (responsáveis pelas plataformas Citius e SITAF), pois a PEPData não é detentora, nem gestora desses dados.

</details>
