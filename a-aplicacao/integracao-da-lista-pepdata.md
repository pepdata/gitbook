# Integração da lista PEPData

## Introdução

A PEPData dispõe de uma lista em formato XML onde é compilada toda a informação da sua lista de PEPs e respetivos familiares e associados.

Esta lista é destinada a Clientes que pretendam realizar a integração no seu sistema a lista da PEPData.

## Estrutura de Informação

Neste momento para cada PEP a lista devolve a seguinte informação:

* **Id -** UUID V4 da pessoa no sistema da PEPData.
* **IdNum -** ID númerico da pessoa no sistema da PEPData.
* **Type -** Tipo da pessoa, neste apenas possui um valor: 'Individual'.
* **PEP -** Flag que indica se a pessoa é PEP ou não, de momento apenas possui um valor: 1.
* **Country -** Nome comum do país a que a pessoa está relacionada.
* **BirthDate -**  Data de nascimento da pessoa no formato DD-MM-YYYY.
* **Info -** Informação acerca das ocupações e relações da pessoa, no seguinte formato:
  * \[Ocupação\_1]; ...; \[Ocupação\_N]; \[Relação\_1]; ...; \[Relação\_N]
    * **Formato da Ocupação:** \[Posição] | \[Orgão] | \[Organização]
    * **Formato das Notas da relação:** Texto livre
    * **Formato da Relação:** \[Tipo da relação] of: \[Nome da pessoa] (\[Ocupação\_1]; ...; \[Ocupação\_N] | \[Notas da relação])
* **Designation -** Classificações da pessoa.&#x20;
  * **Legenda das classificações:**
    * PEP - Pessoa Politicamente Exposta
    * OCP - Titular de Outros Cargos Políticos ou Públicos
    * FAM - Membro Próximo da Família
    * ASSO - Pessoa Reconhecida como Estreitamente Associada
  * Existem os seguintes valores, que representam as várias combinações possíveis de classificações:&#x20;
    * PEP
    * OCP&#x20;
    * FAM&#x20;
    * ASSO&#x20;
    * PEP\_OCP&#x20;
    * PEP\_FAM&#x20;
    * PEP\_ASSO&#x20;
    * OCP\_FAM&#x20;
    * OCP\_ASSO&#x20;
    * FAM\_ASSO&#x20;
    * PEP\_OCP\_FAM&#x20;
    * PEP\_OCP\_ASSO&#x20;
    * PEP\_FAM\_ASSO&#x20;
    * OCP\_FAM\_ASSO&#x20;
    * PEP\_OCP\_FAM\_ASSO
* Hyperlink - URL do perfil da pessoa na plataforma da PEPData

## Exemplos

#### Exemplo 1 -  PEP, OCP, FAM e ASSO

```xml
<profile>
	<Id>7b5910b5-e1ab-e56e-c025-97774b73851c</Id>
	<IdNum>12615</IdNum>
	<Name>José Miguel Carregosa</Name>
	<Type>Individual</Type>
	<PEP>1</PEP>
	<Country>Portugal</Country>
	<BirthDate>28-02-1959</BirthDate>
	<Info>Presidente | União de Freguesias | União das Freguesias de Verim, Friande e Ajude; Membro | Direção | E.P.A.V.E. - Escola Profissional do Alto Ave, E.M.; Sibling's Spouse of: Maria da Conceição Lourenço (JUIZ CONSELHEIRO | Secção de Contencioso Administrativo | S.T.A. - Supremo Tribunal Administrativo); Associate of: Idalina das Neves Nunes Lucas (Diretor | Direção | E.P.A.V.E. - Escola Profissional do Alto Ave, E.M.; Vereador | CÂMARA MUNICIPAL | Município de Guimarães | Beneficial Owner of company with VAT number: PT123456789)</Info>
	<Designation>PEP_OCP_FAM_ASSO</Designation>
	<HyperLink>https://www.pepdata.com/dashboard/iperson?id=7b5910b5-e1ab-e56e-c025-97774b73851c</HyperLink>
</profile>
```

#### Exemplo 2 - PEP, OCP e FAM

```xml
<profile>
	<Id>441f5e84-5bd6-a858-dc0a-cbfc0e573df5</Id>
	<IdNum>994</IdNum>
	<Name>Maria Luísa Duarte</Name>
	<Type>Individual</Type>
	<PEP>1</PEP>
	<Country>Portugal</Country>
	<BirthDate>21-12-1944</BirthDate>
	<Info>Presidente | Junta de Freguesia | Freguesia de Água de Pena; Membro | Comissão Regional | PS Madeira; Sibling of: António José Morgado Couchinho (Membro | Comissão Regional | PS Madeira)</Info>
	<Designation>PEP_OCP_FAM</Designation>
	<HyperLink>https://www.pepdata.com/dashboard/iperson?id=441f5e84-5bd6-a858-dc0a-cbfc0e573df5</HyperLink>
</profile>
```

#### Exemplo 3 - FAM

```xml
<profile>
	<Id>b84ec963-a3ca-ef81-c185-f62acd21fd79</Id>
	<IdNum>950</IdNum>
	<Name>Abel Rui Rocha Gondar Barroso</Name>
	<Type>Individual</Type>
	<PEP>1</PEP>
	<Country>Portugal</Country>
	<BirthDate/>
	<Info>; Father of: Maria Senos (Ministro | Ministério dos Negócios Estrangeiros | Governo da República Portuguesa)</Info>
	<Designation>FAM</Designation>
	<HyperLink>https://www.pepdata.com/dashboard/iperson?id=b84ec963-a3ca-ef81-c185-f62acd21fd79</HyperLink>
</profile>
```

#### Exemplo 4 - PEP

```xml
<profile>
	<Id>c812b75a-d693-fc53-9159-ca59599ada85</Id>
	<IdNum>990</IdNum>
	<Name>Maria Antónia Matalote de Viveiros</Name>
	<Type>Individual</Type>
	<PEP>1</PEP>
	<Country>Portugal</Country>
	<BirthDate>23-08-1968</BirthDate>
	<Info>Ministro | Ministério dos Negócios Estrangeiros | Governo da República Portuguesa</Info>
	<Designation>PEP</Designation>
	<HyperLink>https://www.pepdata.com/dashboard/iperson?id=c812b75a-d693-fc53-9159-ca59599ada85</HyperLink>
</profile>
```
