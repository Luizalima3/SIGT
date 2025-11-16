**Instituto Federal de Educação, Ciência e Tecnologia da Paraíba**  
  **Campus João Pessoa \- Unidade acadêmica de Informática**  
**Curso superior de tecnologia em Sistemas para Internet**   
**Disciplina: Análise e Projeto de Sistemas  \-  Professor: Maxwell Anderson**

`José Correia da Cruz Júnior`  
`Maria Luiza Silva de Lima`   
`Pedro Lucas Silva Batista`

# 

# **Protótipo do tipo Wireframe: \- Versão Preliminar**

### **Introdução**

A visão de casos de uso exibe as funcionalidades do sistema e como elas são percebidas pelos usuários enquanto atores que interagem com o sistema. O Sistema Gerenciador de TCC (SIGT) é um sistema que auxiliará o gerenciamento do processo de TCC no IFPB. O propósito deste documento (DVP) é coletar, analisar e definir as características e necessidades de alto nível do SIGT, focando-se nos recursos necessários e nas razões para essas necessidades.

#### **Quem usa estas informações?**

As informações contidas nos documentos de visão de casos de uso são tipicamente utilizadas por:

* Clientes  
* Designers  
* Desenvolvedores  
* Testadores  
* Gerentes de projeto

#### **Referências**

* Visão de Produto (Documento de Visão do Produto \- DVP)  
* Requisitos de Software (Documento de Requisitos do Software \- DRS)

### **Visão geral**

O SIGT é uma plataforma Web que automatizará e centralizará o fluxo de trabalho das defesas de TCC, abrangendo desde a verificação de aptidão do aluno até a geração da ata final. O objetivo do sistema é resolver problemas como burocracia, desorganização (uso de excel) e falta de rastreabilidade do processo atual.

#### **Atores**

O escopo do produto abrange os seguintes usuários (atores) para o sistema:

* Orientando: aluno que realiza o TCC e utiliza o sistema para cadastro e acompanhamento.  
* Orientador: professor responsável pela orientação do TCC.  
* Coordenador de TCC: professor que supervisiona todo o processo de TCC no curso.  
* Administrador do sistema: profissional responsável por gerenciar e manter o sistema.

#### **Produtos**

O produto SIGT será um sistema integrado de gerenciamento de TCC. Ele possibilita que os usuários cadastrem TCCs, acompanhem o status do trâmite, agendem defesas, gerem documentos oficiais (como a ata de defesa) e recebam notificações automáticas.

#### **Sistema**

O sistema será uma aplicação web acessível por meio de navegadores (Google Chrome, Mozilla Firefox,Microsoft Edge ou Safari) em computadores, laptops, tablets e smartphones. O acesso requer login e senha institucionais do SUAP. A implantação do sistema incluirá a configuração da integração com o SUAP, realizada por meio de APIs para autenticação e validação de dados. Uma restrição de usabilidade exige que a interface seja desenhada para ser familiar (semelhante ao SUAP) para o orientando durante o cadastro inicial.

#### **Monetização**

Embora o SIGT seja disponibilizado como um sistema institucional do IFPB, ele apresenta oportunidades de geração de valor:

1. Licenciamento institucional: O SIGT pode ser disponibilizado para outros *campi* do IFPB ou instituições mediante acordo formal.  
2. Serviços de suporte e manutenção: A equipe pode oferecer contratos de suporte técnico, atualização e treinamento.  
3. Redução de custos administrativos: A automação do gerenciamento do processo de TCC reduz a necessidade de intervenções manuais, gerando economia operacional.

### **Casos de uso**

Os casos de uso representam as funcionalidades essenciais, mapeadas a partir dos requisitos funcionais (RFs) e das telas principais (Protótipos Wireframe) especificadas no DRS.

| Caso de uso | Título | Wireframes |
| ----- | ----- | ----- |
|![Tela de Login](imagens/tela-de-login.png) |  |  |
| UCS001 | Autenticação e Acesso ao Sistema |  |
|![Cadastro Examinador](imagens/Cadastro-examinador.png) |  |  |
| UCS002 | Cadastro do Examinador |  |  |
| ![Alerta de Requisitos](imagens/alerta-de-requisitos.png) |  |  |
| UCS003 | Popup (Alerta de Inaptidão) |  |
