# Capa

---

<h1>Requisitos de Software</h1>

<h2>Sistema Gerenciador de TCC (SiGT)</h2>

<small>Versão 1.1</small>

**Instituto Federal de Educação, Ciência e Tecnologia da Paraíba**

**Campus João Pessoa - Unidade acadêmica de Informática**

**Curso superior de tecnologia em Sistemas para Internet**

**Disciplina: Análise e Projeto de Sistemas - Professor: Maxwell Anderson**

**Autores:**
- José Correia da Cruz Júnior
- Maria Luiza Silva de Lima
- Pedro Lucas Silva Batista

---

## Histórico de revisões

| Data       | Versão | Descrição                           | Autor                     |
| :--------: | :----: | :---------------------------------- | :-----------------------: |
| 09/11/2025 |  1.0   | Criação do documento                | Equipe de Desenvolvimento |
| 15/01/2026 |  1.1   | Adição de novas informações         | Equipe de Desenvolvimento |

---

## Sumário

- [Capa](#capa)
  - [Histórico de revisões](#histórico-de-revisões)
  - [Sumário](#sumário)
- [Introdução](#introdução)
  - [Propósito](#propósito)
  - [Escopo do Produto](#escopo-do-produto)
  - [Definições, Acrônimos e Abreviações](#definições-acrônimos-e-abreviações)
- [Usuários identificados](#usuários-identificados)
- [Requisitos funcionais](#requisitos-funcionais)
- [Requisitos não-funcionais](#requisitos-não-funcionais)

---

# Introdução

## Propósito

O propósito deste documento é especificar os requisitos do **Sistema Gerenciador de TCC (SiGT)** do IFPB, detalhando as funcionalidades, os dados e as restrições necessárias para resolver os problemas de burocracia, desorganização (uso de Excel) e falta de rastreabilidade do processo atual.

## Escopo do Produto

O SiGT será uma plataforma **Web** que automatizará e centralizará o fluxo de trabalho das defesas de TCC, desde a verificação de aptidão do aluno até a geração da ata final.

O sistema abrange os seguintes usuários (atores):

- Usuário do sistema
  - Usuários comuns
    - Orientando
    - Orientador
    - Coordenador de TCC
  - Administrador do sistema

## Definições, Acrônimos e Abreviações

Esta subseção fornece as definições de todos os termos, acrônimos e abreviações necessárias à adequada interpretação do Documento de Requisitos.

### Identificação dos Requisitos

Por convenção, a referência a requisitos é feita através do identificador de requisitos, de acordo como descrito abaixo:

- Funcionais: `[RF-CÓDIGO MÓDULO-sequencial]`
- Não-Funcionais: `[RNF-sequencial]`

O identificador do tipo de requisitos é conforme abaixo:

- **RF** – Requisito Funcional  
- **RNF** – Requisito Não-Funcional  
- **NR** – Não-Requisito  

O identificador do requisito será uma sequência numérica. Esse número sequencial será único para todo o conjunto de tipos de requisitos.

**Exemplo**: RF0001, RF0234, RNF0001, RNF0234, NR0001

### Módulos identificados

- AUT: Autenticação e Acesso  
- GES: Gestão de Usuários e Perfis  
- TCC: Fluxo e Trâmite do Trabalho  
- BNC: Gestão de Bancas e Defesas  
- REL: Documentação, Atas e Relatórios  
- ADM: Administração e Infraestrutura  

### Atributos dos Requisitos

Os atributos de requisitos estabelecidos são:

- **Requisitos vinculados**: fornece uma lista dos requisitos que mantêm rastreabilidade.  
- **Prioridade**: Essencial, Importante, Desejável  
- **Complexidade**: Complexa, Alta, Média ou Baixa  
- **Risco**: Alto, Médio, Baixo  

### Termos e Siglas

| Termo | Definição |
| :---: | :-------- |
| **DRS** | Documento de Requisitos do Software |
| **TCC** | Trabalho de Conclusão de Curso |
| **SUAP** | Sistema Unificado de Administração Pública |
| **Pré-Banca** | Avaliação preliminar do trabalho antes da defesa final |
| **Ata de Defesa** | Documento oficial registrando resultado da defesa |
| **Fator de Correção** | Prazo estabelecido para aluno corrigir conforme sugestões da banca |

---

# Usuários identificados

Os seguintes usuários foram identificados para o sistema:

- **Usuário do sistema**
  - **Usuários comuns**
    - **Orientando**
    - **Orientador**
    - **Coordenador de TCC**
  - **Administrador do sistema**

---

# Requisitos funcionais

Os requisitos funcionais são descritos a seguir, organizados por módulo.

## Módulo AUT – Autenticação e Acesso

- **[RF-AUT-001]** – Como usuário, gostaria de me autenticar utilizando o SUAP, para acessar as funcionalidades específicas de acordo com o meu perfil (orientando, orientador, coordenador ou administrador).

- **[RF-AUT-002]** – Como usuário, gostaria de encerrar minha sessão (logout), para garantir que meus dados não sejam acessados por terceiros em computadores públicos.

## Módulo GES – Gestão de Usuários e Perfis

- **[RF-GES-001]** – Como orientando, gostaria de cadastrar e atualizar meus dados pessoais e as informações do meu TCC, para manter meu registro acadêmico organizado no sistema.

- **[RF-GES-002]** – Como administrador, gostaria de gerenciar os usuários do sistema (criar, editar e desativar contas), para controlar o acesso ao SiGT.

- **[RF-GES-003]** – Como administrador, gostaria de gerenciar as permissões de acesso dos usuários, para definir quais funcionalidades cada perfil pode utilizar.

## Módulo TCC – Fluxo e Trâmite do Trabalho

- **[RF-TCC-001]** – Como orientando, gostaria de verificar automaticamente minha aptidão para defesa com base nos dados do SUAP, para saber se posso iniciar o processo.

- **[RF-TCC-002]** – Como orientando, gostaria de acompanhar o status do meu TCC (cadastrada, pré‑banca, marcada, finalizada), para monitorar o progresso burocrático.

- **[RF-TCC-003]** – Como orientando, gostaria de editar as informações do meu TCC enquanto o cadastro ainda não estiver definitivamente aprovado, para corrigir possíveis erros.

- **[RF-TCC-004]** – Como orientando, gostaria de visualizar o histórico completo do meu TCC, incluindo alterações, agendamentos e resultados, para consultar o que já foi realizado.

- **[RF-TCC-005]** – Como orientando, gostaria de receber notificações sempre que houver mudança no status do meu TCC, para ser informado sobre agendamentos, cancelamentos ou conclusões de defesa.

- **[RF-TCC-006]** – Como coordenador de TCC, gostaria de que o sistema controle os prazos com base no calendário acadêmico, restringindo o limite para cadastro e realização das defesas.

## Módulo BNC – Gestão de Bancas e Defesas

- **[RF-BNC-001]** – Como orientando, gostaria de agendar uma pré‑banca com meu orientador, para que meu trabalho seja avaliado antes da defesa final.

- **[RF-BNC-002]** – Como orientando, gostaria de enviar os arquivos do meu trabalho em formato digital (versão de pré‑banca e versão final), para que a banca tenha acesso ao conteúdo atualizado.

- **[RF-BNC-003]** – Como orientador, gostaria de agendar a defesa do TCC, definindo data, horário e modalidade (presencial ou remota), para formalizar o evento de avaliação.

- **[RF-BNC-004]** – Como orientador, gostaria de registrar os membros da banca examinadora, incluindo participantes internos e externos, para compor oficialmente a avaliação do trabalho.

- **[RF-BNC-005]** – Como orientador, gostaria de reagendar a defesa ou redefinir a banca examinadora, para lidar com imprevistos de disponibilidade de participantes.

- **[RF-BNC-006]** – Como orientador, gostaria de que o sistema envie automaticamente e‑mails com os detalhes da defesa para o orientando e para os membros da banca, para garantir que todos recebam as informações do agendamento.

- **[RF-BNC-007]** – Como coordenador de TCC, gostaria de cancelar uma defesa previamente marcada, para tratar casos excepcionais que exijam remarcação.

## Módulo REL – Documentação, Atas e Relatórios

- **[RF-REL-001]** – Como coordenador de TCC, gostaria de registrar o fator de correção pós‑defesa, definindo um prazo para o aluno realizar as alterações sugeridas pela banca.

- **[RF-REL-002]** – Como coordenador de TCC, gostaria de que o sistema gere automaticamente a ata da defesa, para formalizar o resultado em documento padrão do curso.

- **[RF-REL-003]** – Como coordenador de TCC, gostaria de consultar o histórico de defesas realizadas, para apoiar auditorias, estatísticas e o planejamento do curso.

## Módulo ADM – Administração e Infraestrutura

- **[RF-ADM-001]** – Como administrador, gostaria de realizar backups periódicos dos dados, para possibilitar a recuperação em caso de falhas.

- **[RF-ADM-002]** – Como administrador, gostaria de atualizar o sistema e suas configurações, para adequar o SiGT a novas regras e melhorias institucionais.

- **[RF-ADM-003]** – Como administrador, gostaria de visualizar logs de acesso e atividades, para monitorar o uso do sistema e identificar ações suspeitas.

- **[RF-ADM-004]** – Como administrador, gostaria de restaurar o sistema a partir de backups, para restabelecer o ambiente em caso de perda de dados.

---

# Requisitos não-funcionais

Os requisitos não-funcionais são descritos a seguir, organizados por categorias.

## Segurança

- **[RNF0001]** – O sistema deve garantir a integridade das informações necessárias para a formalização da defesa, especialmente dados de notas e datas de defesa.

- **[RNF0002]** – O sistema deve seguir as diretrizes da LGPD, garantindo que dados sensíveis de alunos e professores externos sejam protegidos e que haja consentimento para coleta.

- **[RNF0003]** – O sistema deve garantir a autenticação do usuário através da integração segura com o SUAP, impedindo acesso não autorizado.

- **[RNF0004]** – O sistema deve garantir que a integridade de atas assinadas não possa ser alterada, gerando um código de autenticidade verificável.

## Disponibilidade

- **[RNF0005]** – O sistema deve estar disponível 24 horas por dia, 7 dias por semana, com redundância de servidores para evitar quedas durante períodos de pico de defesas.

## Usabilidade

- **[RNF0006]** – O sistema deve ser desenvolvido de forma que seja fácil de usar e de fácil aprendizado, fornecendo uma interface clara que instrua o orientando sobre o processo burocrático e seja familiar ao SUAP para reduzir a curva de aprendizado.

- **[RNF0007]** – O sistema deve ser responsivo e funcionar em navegadores modernos (Chrome, Firefox, Edge, Safari) e dispositivos móveis (tablets e smartphones) com sistema operacional Android ou iOS.

## Desempenho

- **[RNF0008]** – O sistema deve garantir que as notificações por email sejam enviadas imediatamente (máximo 30 segundos) após o agendamento ou alteração da defesa.

- **[RNF0009]** – O tempo de geração da Ata de Defesa em PDF não deve ultrapassar 5 segundos, mesmo para sistemas com alta carga.

- **[RNF0010]** – O sistema deve suportar o upload e armazenamento de arquivos PDF de até 50MB por trabalho de conclusão sem prejudicar o desempenho.

## Interoperabilidade

- **[RNF0011]** – O sistema deve consumir a API do SUAP para validação de matrícula, vínculo de professores e extração de dados acadêmicos necessários ao fluxo de TCC.

## Manutenibilidade e Testabilidade

- **[RNF0012]** – O código deve ser versionado em Git, com testes unitários para os módulos de cálculo de notas, validação de prazos e geração de atas, mantendo cobertura mínima de 80%.

- **[RNF0013]** – O sistema deve possuir cobertura de testes de integração para o módulo de geração de atas, garantindo que os dados do aluno nunca venham trocados.

- **[RNF0014]** – O sistema deve ser projetado para ser facilmente atualizável e adaptável a novas regras do colegiado, sem necessidade de recompilação completa do código.

## Localização e Contexto

- **[RNF0015]** – Todas as datas e horários devem seguir o fuso horário de Brasília (GMT-3), considerando o horário de verão se aplicável.
