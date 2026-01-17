# Especificação – Gerenciar perfil do orientando no SiGT

## 1. Informações gerais

- **Caso de uso:** Gerenciar perfil do orientando no SiGT  
- **Código relacionado:** RF-GES-001  
- **Versão:** 1.0  
- **Atores principais:** Orientando  
- **Atores secundários:** Nenhum

## 2. Descrição

Este caso de uso descreve como o orientando gerencia seu perfil no SiGT, incluindo o cadastro e a atualização de seus dados pessoais e das informações do TCC, de forma a manter o registro acadêmico atualizado para uso no fluxo de defesas.

## 3. Pré-condições

- O orientando deve estar autenticado no SiGT.  
- O orientando deve possuir vínculo ativo com o curso que utiliza o SiGT.  
- O módulo de gestão de perfil deve estar disponível no sistema.

## 4. Pós-condições

- Os dados pessoais do orientando são armazenados ou atualizados no sistema.  
- As informações básicas do TCC do orientando (título, área, orientador vinculado, etc.) são registradas ou atualizadas.  
- O perfil do orientando fica disponível para consulta pelos demais módulos (fluxo de TCC, bancas, relatórios).

## 5. Fluxo principal

1. O orientando acessa o SiGT estando autenticado.  
2. O sistema exibe o menu principal com a opção **“Meu perfil”** ou equivalente.  
3. O orientando seleciona a opção de gerenciar perfil.  
4. O sistema apresenta um formulário com os dados pessoais já cadastrados (nome, e-mail institucional, matrícula, curso) e campos de informações do TCC.  
5. O orientando revisa seus dados pessoais e altera as informações desejadas.  
6. O orientando preenche ou atualiza as informações do TCC, como título provisório/definitivo, área de conhecimento, orientador responsável e resumo (quando aplicável).  
7. O orientando aciona a opção **“Salvar”** ou equivalente.  
8. O sistema valida os campos obrigatórios e o formato dos dados (e-mail, tamanho dos textos, etc.).  
9. Em caso de sucesso, o sistema grava as alterações no banco de dados.  
10. O sistema apresenta uma mensagem de confirmação de atualização do perfil.

## 6. Fluxos alternativos e de exceção

### 6.1 Dados obrigatórios não informados

- Passos relacionados: 7–8 do fluxo principal.

1. O orientando tenta salvar o perfil sem preencher todos os campos obrigatórios (por exemplo, título do TCC ou orientador).  
2. O sistema impede a gravação e exibe mensagens de erro indicando quais campos precisam ser corrigidos ou preenchidos.  
3. O orientando corrige as informações e tenta salvar novamente.

### 6.2 Formato de dados inválido

- Passos relacionados: 7–8 do fluxo principal.

1. O orientando informa algum dado em formato inválido (por exemplo, e-mail sem “@”, texto maior que o limite permitido).  
2. O sistema exibe mensagens de validação indicando o problema em cada campo.  
3. O orientando ajusta os dados e repete a operação de salvar.

### 6.3 Falha de gravação

- Passos relacionados: 9 do fluxo principal.

1. O sistema encontra uma falha ao gravar as informações (erro de banco de dados ou indisponibilidade momentânea).  
2. O sistema exibe mensagem informando que não foi possível salvar os dados naquele momento.  
3. O orientando pode tentar novamente mais tarde, mantendo os dados já preenchidos no formulário sempre que possível.

## 7. Regras de negócio

- **RN01** – Alguns campos do perfil podem ser apenas de visualização (por exemplo, nome e matrícula trazidos do SUAP), não podendo ser editados diretamente pelo orientando.  
- **RN02** – O título do TCC deve respeitar um tamanho máximo definido (por exemplo, 255 caracteres).  
- **RN03** – O orientador selecionado deve ser um docente cadastrado e autorizado a orientar TCC no curso.  
- **RN04** – Atualizações de dados do TCC podem ser bloqueadas após determinada etapa do fluxo (por exemplo, após aprovação definitiva do cadastro).

## 8. Restrições

- Dados considerados oficiais (matrícula, nome completo) devem ser sincronizados com o SUAP e não podem ser alterados pelo orientando via SiGT.  
- O formulário deve ser acessível e responsivo, permitindo uso em diferentes dispositivos (desktop, tablet, smartphone).  
- Alterações em dados sensíveis podem gerar registro em log para fins de auditoria.

## 9. Requisitos relacionados

- **RF-GES-001** – Como orientando, gostaria de cadastrar e atualizar meus dados pessoais e as informações do meu TCC, para manter meu registro acadêmico organizado no sistema.  
- **RF-TCC-004** – Visualizar histórico do TCC (usa dados mantidos no perfil).  
- **RNF (Usabilidade)** – Interface clara e simples para edição de dados.  
- **RNF (Segurança)** – Controle de acesso para que apenas o próprio orientando altere seu perfil.