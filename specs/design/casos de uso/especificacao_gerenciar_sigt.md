# Especificação – Gerenciar permissões de acesso no SiGT

## 1. Informações gerais

- **Caso de uso:** Gerenciar permissões de acesso no SiGT  
- **Código relacionado:** RF-GES-003  
- **Versão:** 1.0  
- **Atores principais:** Administrador do sistema  
- **Atores secundários:** Nenhum

## 2. Descrição

Este caso de uso descreve como o administrador configura e mantém as permissões de acesso dos usuários no SiGT, controlando quais funcionalidades cada perfil (orientando, orientador, coordenador de TCC, administrador) poderá utilizar.

## 3. Pré-condições

- O administrador deve estar autenticado no SiGT.  
- O administrador deve possuir permissão para gerenciar perfis e permissões.  
- Devem existir perfis ou papéis previamente definidos (por exemplo: Orientando, Orientador, Coordenador, Administrador).

## 4. Pós-condições

- Permissões de acesso para cada perfil são atualizadas no sistema.  
- As telas e funcionalidades disponíveis para cada usuário passam a refletir as permissões configuradas.  
- Alterações em permissões são registradas para fins de rastreabilidade.

## 5. Fluxo principal

### 5.1 Configurar permissões por perfil

1. O administrador acessa o menu de administração do SiGT.  
2. O administrador seleciona a opção **“Perfis e permissões”** ou equivalente.  
3. O sistema exibe a lista de perfis existentes (Orientando, Orientador, Coordenador, Administrador etc.).  
4. O administrador seleciona um perfil para edição (por exemplo, Orientador).  
5. O sistema apresenta uma lista de funcionalidades/telas com opções de marcação (permitir/negar acesso).  
6. O administrador marca ou desmarca as funcionalidades desejadas para o perfil selecionado.  
7. O administrador aciona a opção **“Salvar”**.  
8. O sistema valida as alterações (por exemplo, não permitir que todos os administradores fiquem sem acesso à administração).  
9. O sistema grava as permissões atualizadas para o perfil e exibe mensagem de confirmação.

### 5.2 Visualizar permissões de um perfil

1. O administrador acessa a tela de perfis e permissões.  
2. O administrador seleciona um perfil.  
3. O sistema exibe, em modo somente leitura ou editável, todas as funcionalidades associadas àquele perfil.  

## 6. Fluxos alternativos e de exceção

### 6.1 Tentativa de remoção de todas as permissões de administrador

- Passos relacionados: 6–8 do fluxo principal.

1. O administrador tenta desmarcar todas as funcionalidades para o perfil “Administrador”.  
2. O sistema identifica que isso deixaria o sistema sem nenhum perfil com poderes de administração.  
3. O sistema bloqueia a operação e exibe uma mensagem de erro explicando que pelo menos um conjunto mínimo de permissões deve ser mantido para administradores.  
4. O administrador ajusta a configuração e tenta salvar novamente.

### 6.2 Falha ao salvar permissões

1. Após o administrador confirmar a alteração, ocorre falha de gravação (erro de banco ou indisponibilidade).  
2. O sistema informa que não foi possível aplicar as alterações.  
3. As permissões anteriores permanecem válidas.  
4. O administrador poderá tentar novamente mais tarde.

## 7. Regras de negócio

- **RN01** – Permissões são aplicadas por perfil/papel; todos os usuários de um mesmo perfil compartilham o mesmo conjunto de permissões.  
- **RN02** – Alterações em permissões de perfis devem ser registradas em log, incluindo usuário administrador responsável, data/hora e alterações realizadas.  
- **RN03** – Não é permitido remover do perfil administrador o acesso às funcionalidades críticas (por exemplo, gestão de usuários, visualização de logs, configuração de backup).  
- **RN04** – Novos perfis só podem ser criados ou removidos mediante regras definidas pelo colegiado/coordenador do curso (se implementado).

## 8. Restrições

- Somente usuários com perfil de administrador podem acessar a tela de perfis e permissões.  
- A interface de permissões deve ser suficientemente clara para evitar configurações incorretas (ex.: grupos de permissões, categorias por módulo).  
- As permissões devem ser avaliadas em todas as requisições a funcionalidades restritas (tanto na interface quanto na camada de serviço/API).

## 9. Requisitos relacionados

- **RF-GES-003** – Como administrador, gostaria de gerenciar as permissões de acesso dos usuários, para definir quais funcionalidades cada perfil pode utilizar.  
- **RF-GES-002** – Manter usuário (pois o usuário recebe um perfil que usa essas permissões).  
- **RF-ADM-003** – Visualizar logs de acesso e atividades (para auditar alterações de permissões).  
- **Requisitos não-funcionais de segurança** – Controle de acesso, autorização por perfil.