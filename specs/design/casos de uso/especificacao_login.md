# Especificação – Fazer login no SiGT

## 1. Informações gerais

- **Caso de uso:** Fazer login no SiGT  
- **Código relacionado:** RF-AUT-001  
- **Versão:** 1.0  
- **Atores principais:** Usuário (orientando, orientador, coordenador de TCC, administrador)  
- **Atores secundários:** Sistema SUAP (serviço de autenticação)

## 2. Descrição

Este caso de uso descreve o processo pelo qual um usuário acessa o SiGT utilizando suas credenciais do SUAP, de forma autenticada e segura, para utilizar as funcionalidades condizentes com o seu perfil (orientando, orientador, coordenador de TCC ou administrador).

## 3. Pré-condições

- O usuário deve possuir um cadastro válido no SUAP.  
- O SiGT deve estar corretamente configurado e integrado ao serviço de autenticação do SUAP.  
- O usuário deve ter acesso à internet e a um navegador compatível com o SiGT.  
- A API de autenticação do SUAP deve estar disponível.

## 4. Pós-condições

- Uma sessão autenticada é criada no SiGT para o usuário.  
- O perfil de acesso do usuário é identificado (orientando, orientador, coordenador de TCC ou administrador).  
- As funcionalidades do sistema são liberadas de acordo com o perfil identificado.

## 5. Fluxo principal

1. O usuário acessa a página inicial do SiGT.  
2. O sistema exibe a tela de login com a opção **“Entrar com SUAP”**.  
3. O usuário aciona a opção “Entrar com SUAP”.  
4. O sistema redireciona o usuário para a página de autenticação do SUAP.  
5. O usuário informa suas credenciais (usuário e senha) do SUAP e confirma o envio.  
6. O SUAP valida as credenciais do usuário.  
7. Em caso de sucesso, o SUAP retorna um token de autenticação/autorização para o SiGT.  
8. O SiGT valida o token recebido e identifica o usuário e seu perfil.  
9. O sistema cria uma sessão autenticada para o usuário.  
10. O sistema redireciona o usuário para a página inicial do SiGT, exibindo o menu e as funcionalidades correspondentes ao seu perfil.

## 6. Fluxos alternativos e de exceção

### 6.1 Credenciais inválidas

- Passos relacionados: 5–6 do fluxo principal.

1. O usuário informa usuário e/ou senha incorretos na tela do SUAP.  
2. O SUAP rejeita a autenticação e exibe mensagem de erro indicando falha de credenciais.  
3. O usuário pode tentar autenticar-se novamente ou cancelar a operação.  
4. Nenhuma sessão é criada no SiGT.

### 6.2 Falha na integração com o SUAP

- Passos relacionados: 4 ou 7 do fluxo principal.

1. Ao tentar redirecionar para o SUAP ou validar o token, ocorre falha de comunicação (timeout, erro de rede ou erro interno).  
2. O sistema exibe mensagem informando indisponibilidade temporária do serviço de autenticação.  
3. O sistema orienta o usuário a tentar novamente mais tarde.  
4. Nenhuma sessão é criada no SiGT.

### 6.3 Usuário sem permissão de acesso ao SiGT

- Passo relacionado: 8 do fluxo principal.

1. O token retornado pelo SUAP é válido, mas o usuário não possui vínculo ou papel autorizado a utilizar o SiGT.  
2. O sistema exibe mensagem informando que o usuário não possui permissão para acessar o SiGT.  
3. A sessão não é criada e o usuário permanece não autenticado.

## 7. Regras de negócio

- **RN01** – A autenticação no SiGT deve ser realizada exclusivamente por meio da integração com o SUAP; o sistema não deve armazenar senhas dos usuários.  
- **RN02** – Após autenticação, o perfil de acesso deve ser obtido a partir das informações do SUAP (vínculos ativos e papéis do usuário).  
- **RN03** – A sessão do usuário deve expirar após um período de inatividade definido pela instituição (por exemplo, 30 minutos), exigindo novo login.  
- **RN04** – Cada token de autenticação recebido do SUAP deve ser validado quanto à integridade e prazo de expiração antes de ser aceito.

## 8. Restrições

- O SiGT depende da disponibilidade da infraestrutura do SUAP para autenticar usuários.  
- O acesso ao SiGT deve ser realizado por HTTPS, garantindo a confidencialidade dos dados de autenticação em trânsito.  
- O sistema deve funcionar apenas em navegadores suportados pela instituição (por exemplo, versões recentes de Chrome, Firefox, Edge e Safari).

## 9. Requisitos relacionados

- **RF-AUT-001** – Como usuário, gostaria de me autenticar utilizando o SUAP, para acessar as funcionalidades específicas de acordo com o meu perfil (orientando, orientador, coordenador ou administrador).  
- **RNF (Segurança/LGPD)** – Requisitos de segurança e privacidade relacionados à proteção dos dados de autenticação e integração com sistemas externos.  
- **RNF (Disponibilidade)** – Requisitos que tratam da disponibilidade do serviço de autenticação e do próprio SiGT.