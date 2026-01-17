# Especificação – Manter usuário no SiGT

## 1. Informações gerais

- **Caso de uso:** Manter usuário no SiGT  
- **Código relacionado:** RF-GES-002  
- **Versão:** 1.0  
- **Atores principais:** Administrador do sistema  
- **Atores secundários:** Nenhum

## 2. Descrição

Este caso de uso descreve como o administrador do sistema cria, edita e desativa usuários no SiGT, de forma a controlar quem pode acessar o sistema e com quais perfis.

## 3. Pré-condições

- O administrador deve estar autenticado no SiGT.  
- O administrador deve possuir permissão para gerenciar usuários.  
- O módulo de gestão de usuários deve estar disponível.

## 4. Pós-condições

- Novos usuários podem ser cadastrados no SiGT.  
- Usuários existentes podem ter seus dados atualizados.  
- Usuários podem ser desativados, bloqueando o acesso ao SiGT sem excluir histórico.

## 5. Fluxo principal

### 5.1 Cadastrar usuário

1. O administrador acessa o menu de administração do SiGT.  
2. O administrador seleciona a opção **“Usuários”** ou equivalente.  
3. O sistema exibe a lista de usuários cadastrados e a opção **“Novo usuário”**.  
4. O administrador aciona a opção **“Novo usuário”**.  
5. O sistema apresenta um formulário de cadastro de usuário com campos como: nome, e-mail institucional, matrícula/identificador, tipo de perfil (orientando, orientador, coordenador, administrador) e situação (ativo/inativo).  
6. O administrador preenche os dados obrigatórios e escolhe o perfil do usuário.  
7. O administrador aciona a opção **“Salvar”**.  
8. O sistema valida os dados informados.  
9. Em caso de sucesso, o sistema grava o novo usuário e exibe mensagem de confirmação.  
10. O usuário passa a aparecer na lista de usuários.

### 5.2 Editar usuário

1. A partir da lista de usuários, o administrador localiza o usuário a ser alterado.  
2. O administrador seleciona a opção de **“Editar”** para o usuário desejado.  
3. O sistema exibe o formulário com os dados atuais do usuário.  
4. O administrador altera os campos necessários (por exemplo, perfil, e-mail, situação).  
5. O administrador aciona a opção **“Salvar”**.  
6. O sistema valida os dados.  
7. O sistema grava as alterações e apresenta mensagem de confirmação.

### 5.3 Desativar usuário

1. A partir da lista de usuários, o administrador localiza o usuário a ser desativado.  
2. O administrador seleciona a opção **“Desativar”** ou altera o campo de situação para “Inativo”.  
3. O sistema solicita confirmação da ação.  
4. O administrador confirma a desativação.  
5. O sistema registra o usuário como inativo e impede novos acessos ao SiGT com aquela conta.  
6. O usuário permanece na base para fins de histórico e rastreabilidade.

## 6. Fluxos alternativos e de exceção

### 6.1 Dados obrigatórios não informados

- Passos relacionados: 7–8 dos fluxos de cadastro/edição.

1. O administrador tenta salvar sem preencher todos os campos obrigatórios.  
2. O sistema exibe mensagens indicando quais campos precisam ser preenchidos.  
3. O administrador ajusta os dados e tenta novamente.

### 6.2 Formato de dados inválido

1. O administrador informa dados em formato inválido (por exemplo, e-mail mal formatado).  
2. O sistema identifica o erro e indica os campos inválidos.  
3. O administrador corrige e tenta salvar novamente.

### 6.3 Usuário já existente

1. Ao cadastrar um novo usuário, o administrador informa e-mail, matrícula ou identificador que já existe no sistema.  
2. O sistema impede a criação do novo cadastro e apresenta mensagem informando que já existe usuário com aquele identificador.  
3. O administrador pode optar por editar o usuário existente em vez de criar um novo.

## 7. Regras de negócio

- **RN01** – Cada usuário deve possuir um identificador único (por exemplo, matrícula ou e-mail institucional) que não pode ser duplicado.  
- **RN02** – Usuários desativados não podem acessar o sistema, mas seu histórico de ações deve ser mantido.  
- **RN03** – Alguns tipos de usuário (por exemplo, administrador) só podem ser atribuídos por outro administrador.  
- **RN04** – Alterações em perfil e situação (ativo/inativo) devem ser registradas em log para auditoria.

## 8. Restrições

- A gestão de usuários deve ser acessível apenas para contas com perfil de administrador.  
- A interface deve permitir filtros e busca na lista de usuários para facilitar a administração em bases grandes.  
- A sincronização com sistemas externos (como SUAP) pode limitar quais dados são editáveis localmente.

## 9. Requisitos relacionados

- **RF-GES-002** – Como administrador, gostaria de gerenciar os usuários do sistema (criar, editar e desativar contas), para controlar o acesso ao SiGT.  
- **RF-ADM-003** – Visualizar logs de acesso e atividades (para auditar ações de gestão de usuários).  
- **RNF (Segurança)** – Regras de controle de acesso à funcionalidade de administração.  
- **RNF (Usabilidade)** – Requisitos de usabilidade relacionados à filtragem e ordenação de usuários.