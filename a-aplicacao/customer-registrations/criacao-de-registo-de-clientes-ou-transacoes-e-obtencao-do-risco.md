# Criação de registo de clientes ou transações e obtenção do risco

## 1 - Criar um registo de clientes ou transações

Existem diferentes formas de criar registos de clientes ou transações:

* **Manual** - Através da plataforma, no menu de **Registo de Clientes** ou **Registo Transações**.
* **API Pública** - Através da função [`add_questionnaire`](../../api/registrations.md#adicao-de-um-registo)``
* **Importação de Registos ou Transações** - Através da plataforma, no menu de **Registo de Clientes** ou **Registo Transações**, clicar em _"Importar Registos"._

## 2 - Obter o risco do registo de clientes ou transações criado

Existem diferentes formas de obter o risco do registo criado:

* Manual - Abertura do registo, escolhendo-o da lista presente no menu de **Registo de Clientes** ou **Registo Transações**.
* **API Pública** - Através da função [`get_questionnaires`](../../api/registrations.md#obter-registos) especificando o id do registo que quer consular.
