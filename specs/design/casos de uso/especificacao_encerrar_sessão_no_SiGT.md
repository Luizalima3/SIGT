# Especificação – Encerrar sessão no SiGT

## 1. Informações gerais

- **Caso de uso:** Encerrar sessão no SiGT  
- **Código relacionado:** RF-AUT-002  
- **Versão:** 1.0  
- **Atores principais:** Usuário (orientando, orientador, coordenador de TCC, administrador)

## 2. Descrição

Este caso de uso descreve o processo pelo qual o usuário encerra voluntariamente sua sessão no SiGT, de forma segura, para evitar que outras pessoas utilizem sua conta em computadores compartilhados ou dispositivos de terceiros.

## 3. Pré-condições

- O usuário deve estar autenticado no SiGT, com sessão ativa.  
- O SiGT deve estar disponível e acessível no navegador do usuário.

## 4. Pós-condições

- A sessão do usuário é encerrada no SiGT.  
- Os dados de sessão (tokens, cookies de sessão) são invalidados.  
- O usuário é redirecionado para a tela inicial ou de login, sem acesso às funcionalidades restritas.

## 5. Fluxo principal

1. O usuário, estando autenticado, acessa o menu ou área da interface onde existe a opção **“Sair”** ou **“Encerrar sessão”**.  
2. O sistema exibe a opção de confirmação de saída (quando aplicável).  
3. O usuário confirma que deseja encerrar a sessão.  
4. O sistema invalida a sessão ativa do usuário (sessão de aplicação e/ou token de autenticação).  
5. O sistema remove ou invalida os cookies/tokens de sessão utilizados para identificar o usuário.  
6. O sistema redireciona o usuário para a página inicial pública ou tela de login do SiGT.  
7. O sistema não apresenta mais funcionalidades restritas que dependam de autenticação.

## 6. Fluxos alternativos e de exceção

### 6.1 Cancelamento do encerramento de sessão

- Passo relacionado: 2–3 do fluxo principal.

1. Ao ser perguntado se deseja realmente encerrar a sessão, o usuário seleciona a opção **“Cancelar”**.  
2. O sistema mantém a sessão ativa.  
3. O usuário permanece na tela em que estava antes de solicitar o logout.

### 6.2 Sessão já expirada

- Passo relacionado: 1 do fluxo principal.

1. O usuário tenta acionar a opção de encerrar sessão, mas a sessão já foi expirada automaticamente por inatividade.  
2. O sistema identifica que não existe sessão válida associada ao usuário.  
3. O sistema redireciona o usuário diretamente para a tela de login ou página inicial pública.  

## 7. Regras de negócio

- **RN01** – O sistema deve invalidar completamente a sessão do usuário no servidor ao encerrar a sessão, impedindo qualquer reutilização do identificador de sessão.  
- **RN02** – Após o encerramento da sessão, o usuário deve ser tratado como não autenticado em qualquer requisição subsequente.  
- **RN03** – Links de navegação que exigem autenticação devem redirecionar para a tela de login quando acessados após o logout.  
- **RN04** – O sistema pode aplicar encerramento automático da sessão após período de inatividade, seguindo a mesma lógica do encerramento manual.

## 8. Restrições

- O encerramento de sessão deve funcionar independentemente da página em que o usuário esteja dentro do SiGT.  
- O sistema deve assegurar que caches de navegador não exibam conteúdos sensíveis após o logout (orientação por cabeçalhos de cache e boas práticas de segurança).  
- O mecanismo de logout deve ser compatível com o fluxo de autenticação via SUAP, respeitando tokens e redirecionamentos definidos pela instituição.

## 9. Requisitos relacionados

- **RF-AUT-002** – Como usuário, gostaria de encerrar minha sessão (logout), para garantir que meus dados não sejam acessados por terceiros em computadores públicos.  
- **RNF (Segurança)** – Requisitos de segurança sobre controle de sessão, expiração e proteção contra acesso não autorizado.  
- **RNF (Usabilidade)** – Requisitos que tratam da visibilidade e facilidade de acesso à opção de logout na interface.