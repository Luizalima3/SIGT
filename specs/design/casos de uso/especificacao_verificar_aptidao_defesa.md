# Especificação – Verificar aptidão para defesa de TCC

## 1. Informações gerais

- **Caso de uso:** Verificar aptidão para defesa de TCC  
- **Código relacionado:** RF-TCC-001  
- **Versão:** 1.0  
- **Atores principais:** Orientando  
- **Atores secundários:** SUAP (fonte de dados acadêmicos), Coordenador de TCC (definição de regras)

## 2. Descrição

Este caso de uso descreve como o orientando verifica automaticamente, no SiGT, se está apto a iniciar o processo de defesa de TCC, com base em informações acadêmicas obtidas do SUAP e em regras definidas pelo curso (disciplinas concluídas, carga horária, situação de matrícula etc.).

## 3. Pré-condições

- O orientando deve estar autenticado no SiGT.  
- O orientando deve possuir vínculo ativo com o curso no SUAP.  
- A integração entre o SiGT e o SUAP deve estar operacional.  
- As regras de aptidão para defesa devem estar previamente configuradas pela coordenação de TCC/curso.

## 4. Pós-condições

- O sistema informa ao orientando se ele está **apto** ou **não apto** à defesa de TCC.  
- Quando não apto, o sistema apresenta os motivos principais (por exemplo, disciplinas pendentes, carga horária insuficiente).  
- O status de aptidão pode ser armazenado para consulta em outros módulos (por exemplo, solicitação de banca).

## 5. Fluxo principal

1. O orientando acessa o SiGT e navega até a opção **“Verificar aptidão para defesa”** ou funcionalidade equivalente.  
2. O sistema exibe uma tela com a opção de verificar aptidão.  
3. O orientando aciona o comando para verificar aptidão.  
4. O sistema consulta o SUAP para obter a situação acadêmica do orientando (disciplinas cursadas, aprovadas, carga horária, situação de matrícula, etc.).  
5. O sistema aplica as regras de aptidão configuradas pelo curso sobre os dados obtidos.  
6. O sistema determina se o orientando está apto ou não apto à defesa de TCC.  
7. O sistema exibe o resultado ao orientando (apto / não apto).  
8. Se não apto, o sistema lista os requisitos que ainda não foram cumpridos (por exemplo, “Disciplina X reprovada”, “Carga horária mínima não atingida”).  

## 6. Fluxos alternativos e de exceção

### 6.1 Falha na consulta ao SUAP

- Passos relacionados: 4 do fluxo principal.

1. Ao tentar consultar o SUAP, ocorre erro de comunicação (timeout, indisponibilidade da API ou erro interno).  
2. O sistema informa ao orientando que não foi possível verificar a aptidão no momento.  
3. O sistema orienta o usuário a tentar novamente mais tarde.  
4. Nenhum resultado de aptidão é atualizado.

### 6.2 Regras de aptidão não configuradas

- Passos relacionados: 5 do fluxo principal.

1. O sistema identifica que não existem regras de aptidão configuradas (por exemplo, primeira execução do sistema).  
2. O sistema exibe mensagem informando que a verificação não está disponível porque as regras ainda não foram definidas pela coordenação.  
3. O sistema pode registrar essa situação para que o coordenador ou administrador tome providências.

### 6.3 Dados incompletos no SUAP

- Passos relacionados: 4–5 do fluxo principal.

1. O SUAP retorna informações incompletas (por exemplo, histórico acadêmico inconsistente).  
2. O sistema não consegue aplicar as regras de forma segura.  
3. O sistema informa que a aptidão não pôde ser determinada devido à inconsistência de dados e orienta o aluno a procurar a coordenação.

## 7. Regras de negócio

- **RN01** – A aptidão para defesa deve ser determinada exclusivamente com base em dados oficiais obtidos do SUAP (sem edição manual pelo aluno).  
- **RN02** – As regras de aptidão (como disciplinas obrigatórias concluídas e carga horária mínima) devem ser parametrizáveis pela coordenação de TCC/curso.  
- **RN03** – O orientando não deve conseguir solicitar agendamento de banca se estiver marcado como não apto.  
- **RN04** – A data e o resultado da última verificação de aptidão podem ser armazenados para auditoria e rastreabilidade.

## 8. Restrições

- O desempenho da verificação depende do tempo de resposta do SUAP.  
- As regras de aptidão devem estar alinhadas ao regulamento institucional do TCC e podem variar entre cursos.  
- A interface deve apresentar o resultado de forma clara, destacando em linguagem simples os requisitos pendentes.

## 9. Requisitos relacionados

- **RF-TCC-001** – Como orientando, gostaria de verificar automaticamente minha aptidão para defesa com base nos dados do SUAP, para saber se posso iniciar o processo.  
- **RF-TCC-002** – Acompanhar status do TCC (usa o resultado de aptidão como parte do fluxo).  
- **RF-AUT-001** – Fazer login via SUAP (necessário para identificar o aluno e acessar dados).  
- **Requisitos não-funcionais de segurança e interoperabilidade** – Integração com SUAP e proteção de dados acadêmicos.