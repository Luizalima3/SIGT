# Especificação – Verificar Aptidão para Defesa de TCC

---

## 1. Informações Gerais

- **Caso de Uso:** Verificar aptidão para defesa de TCC  
- **Código Relacionado:** RF-TCC-001  
- **Versão:** 1.1 (Verificação Automática via Pop-up)  
- **Atores Principais:** Orientando  
- **Atores Secundários:**  
  - SUAP (fonte de dados acadêmicos)  
  - Coordenador de TCC (definição de regras)

---

## 2. Descrição

Este caso de uso descreve o processo automatizado do SiGT para validar se o orientando cumpre os requisitos necessários para a defesa do TCC.  

A verificação ocorre de forma proativa imediatamente após o login. Se o sistema identificar que o aluno não cumpre as regras pré-estabelecidas, um **pop-up (modal) impeditivo** é exibido detalhando as pendências acadêmicas.

---

## 3. Pré-condições

- O orientando deve possuir vínculo ativo com o curso no SUAP.  
- A integração (API) entre o SiGT e o SUAP deve estar operacional.  
- As regras de aptidão (ex: disciplinas obrigatórias, carga horária mínima) devem estar configuradas pela coordenação no sistema.

---

## 4. Pós-condições

- **Se Apto:**  
  - O sistema libera o fluxo normal para solicitação de banca e demais funcionalidades de defesa.  

- **Se Não Apto:**  
  - O sistema exibe um pop-up de alerta.  
  - Lista as pendências.  
  - Mantém bloqueado o agendamento de banca.  

- O histórico da verificação (status, data e hora) é registrado para auditoria.

---

## 5. Fluxo Principal (Gatilho: Pós-Login)

1. O orientando realiza o login no SiGT via SUAP.  
2. O sistema inicia automaticamente a rotina de verificação.  
3. O sistema consulta os dados acadêmicos no SUAP (situação de matrícula, disciplinas e carga horária).  
4. O sistema processa os dados com base nas regras cadastradas pela coordenação.  
5. O sistema determina o status de aptidão.  

### 5.1 Caminhos

- **Se o aluno estiver APTO:**  
  - O sistema redireciona o usuário para o Dashboard principal sem interrupções.

- **Se o aluno estiver NÃO APTO:**  
  - O sistema exibe um pop-up (modal) na tela inicial informando a inaptidão.  
  - O sistema apresenta a lista detalhada dos requisitos não cumpridos  
    - Ex: *"Falta concluir a disciplina Metodologia Científica"*.  
  - O sistema bloqueia o acesso aos formulários de solicitação de defesa.

---

## 6. Fluxos Alternativos e de Exceção

### 6.1 Falha na consulta ao SUAP

- Ao tentar consultar o SUAP após o login, ocorre erro de comunicação (timeout ou indisponibilidade).  
- O sistema exibe uma mensagem informando que a verificação automática falhou por instabilidade no serviço externo.  
- As funcionalidades de agendamento permanecem bloqueadas até que uma consulta bem-sucedida seja realizada.

---

### 6.2 Regras de aptidão não configuradas

- O sistema identifica que a coordenação ainda não parametrizou os requisitos de aptidão para o curso.  
- O sistema informa ao aluno que a verificação automática está indisponível e orienta contato com a coordenação.

---

## 7. Regras de Negócio

| ID   | Regra               | Descrição |
|------|---------------------|-----------|
| RN01 | Gatilho Automático  | A verificação de aptidão deve ocorrer sempre no momento do acesso (login) do aluno. |
| RN02 | Bloqueio de Função  | Alunos com status **"Não Apto"** não podem acessar a funcionalidade de **"Solicitar Banca"**. |
| RN03 | Soberania do SUAP   | A decisão de aptidão baseia-se exclusivamente em dados oficiais, sem entrada manual de notas ou horas pelo aluno. |
| RN04 | Transparência      | O pop-up de inaptidão deve listar objetivamente quais requisitos o aluno ainda não cumpriu. |

---

## 8. Restrições

- O tempo de carregamento da primeira tela após o login depende da performance da API do SUAP.  
- O pop-up deve ser fechável para permitir uso de outras partes do sistema (ex: download de documentos), porém o bloqueio das funções de defesa deve persistir.

---

## 9. Requisitos Relacionados

- **RF-TCC-001:** Verificar aptidão automaticamente via SUAP.  
- **RF-AUT-001:** Login via SUAP.  
- **RF-COORD-005:** Parametrizar regras de aptidão por curso.

---
