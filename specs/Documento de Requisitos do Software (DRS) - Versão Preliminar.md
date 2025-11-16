**Instituto Federal de Educação, Ciência e Tecnologia da Paraíba**  
  **Campus João Pessoa \- Unidade acadêmica de Informática**  
**Curso superior de tecnologia em Sistemas para Internet**   
**Disciplina: Análise e Projeto de Sistemas  \-  Professor: Maxwell Anderson**

`José Correia da Cruz Júnior`  
`Maria Luiza Silva de Lima`   
`Pedro Lucas Silva Batista`

# 

# **Requisitos de software: Sistema Gerenciador de TCC (SIGT)**

# **Sumário**

* Capa   
* Sumário  
* Introdução  
  * Propósito  
  * Escopo do produto  
  * Definições, acrônimos e abreviações  
* Requisitos funcionais  
  * Requisitos comuns  
  * Requisitos do orientando  
  * Requisitos do orientador  
  * Requisitos do coordenador  
  * Requisitos do Administrador  
* Requisitos não funcionais


# **Documento de Requisitos do Software (DRS) \- Versão Preliminar**

## **1\. Introdução**

### **1.1. Propósito**

O propósito deste documento é especificar os requisitos do **Sistema Gerenciador de TCC** do IFPB, detalhando as funcionalidades, os dados e as restrições necessárias para resolver os problemas de burocracia, desorganização (uso de Excel) e falta de rastreabilidade do processo atual.

### **1.2. Escopo do Produto**

O sistema será uma plataforma **Web** que automatizará e centralizará o fluxo de trabalho das defesas de TCC, desde a verificação de aptidão do aluno até a geração da ata final. 

O escopo abrange os seguintes usuários para o sistema: 

* Usuário do sistema   
  * Usuários comuns   
    * Orientando  
    * Orientador   
    * Coordenador de TCC   
  * Administrador do sistema  
    

**1.3. Definições, Acrônimos e Abreviações**

Esta subseção fornece as definições de todos os termos, acrônimos e abreviações necessárias à adequada interpretação do Documento de Requisitos. 

* Identificação dos requisitos: por convenção, a referência a requisitos é feita através do identificador de requisitos, de acordo como descrito abaixo:   
    
  \[IDENTIFICADOR DO TIPO DE REQUISITOSidentificador do requisito\]   
  O identificador do tipo de requisitos é conforme abaixo:   
  * RF – Requisito Funcional   
  * RNF – Requisito Não-Funcional   
  * NR – Não-Requisito 

  O identificador do requisito será uma sequência numérica. Esse número sequencial será único para todo o conjunto de tipos de requisitos. 

Exemplo: RF001, RF134, RNF134, NR212

| Termo | Definição |
| :---- | :---- |
| **IHC** | Interação Humano-Computador |
| **DRS** | Documento de Requisitos do Software |
| **TCC** | Trabalho de Conclusão de Curso |
| **SUAP** | Sistema Unificado de Administração Pública |
| **Pré-Banca** | Avaliação preliminar do trabalho antes da defesa final. |

## **2\. Requisitos Funcionais**

Os requisitos são agrupados por ator e refletem as funcionalidades essenciais para que o sistema atenda à visão do produto.

### **2.1. Requisitos Comuns**

| ID | Requisito |
| :---- | :---- |
| RF001 | O sistema deve permitir que o usuário (todos os perfis) se logue no sistema para acessar as funcionalidades. |
| RF002 | O sistema deve ser integrado ao SUAP para que seja possível realizar verificações e validações. |

**2.2. Requisitos do Orientando** 

| ID | Requisito |
| :---- | :---- |
| RF101 | O sistema deve fornecer mecanismos de verificação para garantir que o orientando esteja apto a realizar a defesa. |
| RF102 | O sistema deve permitir que o orientando adicione seus dados pessoais e as informações relacionadas ao seu TCC para cadastro. |
| RF103 | O sistema deve permitir que o orientando acompanhe o trâmite da sua defesa (status: cadastrada, pré-banca, marcada, cancelado, finalizado). |
| RF104 | O sistema deve permitir que o orientando agende uma pré-banca. |
| RF105 | O sistema deve permitir o armazenamento do documento de defesa final do trabalho. |
| RF106 | O sistema deve permitir que o orientando edite suas informações do TCC antes que o orientador aprove o cadastro definitivo |
| RF107 | O sistema deve permitir que o orientando visualize o histórico completo do seu TCC. |
| RF108 | O sistema deve notificar o orientando sobre mudanças no status do trâmite. |

**2.3**. **Requisitos do Orientador** 

| ID | Requisito |
| :---- | :---- |
| RF201 | O sistema deve permitir ao orientador agendar uma defesa e definir se a defesa será presencialmente ou remotamente. |
| RF202 | O sistema deve permitir ao orientador registrar os membros da banca avaliadora. |
| RF203 | O sistema deve permitir ao orientador reagendar ou redefinir a banca avaliadora para resolver imprevistos. |
| RF204 | O sistema deve notificar automaticamente por email (ao orientador, membros da banca e orientando) sobre as informações da defesa agendada. |
| RF205 | O sistema deve permitir ao orientador registrar notas e adicionar comentários finais para comprovar a aprovação ou reprovação. |

**2.4. Requisitos do Coordenador** 

| ID | Requisito |
| :---- | :---- |
| RF301 | O sistema deve gerar automaticamente a ata da defesa do TCC. |
| RF302 | O sistema deve permitir ao coordenador deferir ou indeferir o registro de cada orientando. |
| RF303 | O sistema deve restringir o tempo limite para registro e defesa conforme o calendário acadêmico. |
| RF304 | O sistema deve permitir ao coordenador cancelar uma defesa previamente marcada. |
| RF305 | O sistema deve permitir ao coordenador verificar o histórico de defesas de trabalho de conclusão. |

**2.5 Requisitos do Administrador**

| ID | Requisito |
| :---- | :---- |
| RF401 | O sistema deve permitir ao administrador gerenciar os usuários do sistema (criar, editar, desativar). |
| RF402 | O sistema deve permitir ao administrador realizar backup dos dados do sistema. |
| RF403 | O sistema deve permitir ao administrador atualizar o sistema e suas configurações. |
| RF404 | O sistema deve permitir ao administrador visualizar logs de acesso e atividades do sistema. |
| RF405 | O sistema deve permitir ao administrador gerenciar as permissões de acesso dos usuários. |
| RF406 | O sistema deve permitir ao administrador restaurar o sistema a partir de backup em caso de falhas. |

**3\. Requisitos Não-Funcionais**

| ID | Requisito |
| :---- | :---- |
| RNF001 | O sistema deve preservar a integridade das informações necessárias para a formalização da defesa. |
| RNF002 | O sistema deve garantir a autenticação do usuário comum por meio da integração com o SUAP. |
| RNF003 | O sistema deve garantir que as notificações por email sejam enviadas imediatamente após o agendamento da defesa. |
| RNF004 | O sistema deve fornecer uma interface clara que instrua o orientando sobre as macro informações e o processo burocrático. |
| RNF005 | O sistema deve ser familiar (semelhante ao SUAP) para o orientando durante o cadastro inicial. |
| RNF006 | O sistema deve ser projetado para ser facilmente atualizável e adaptável a novas regras do colegiado. |

[image1]: <data:image/png;base64,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>
