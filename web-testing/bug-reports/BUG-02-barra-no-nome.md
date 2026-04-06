# BUG-03 — Registro aceita caractere especial "/" nos campos de nome

Sumário:
- A aplicação permite a criação de conta utilizando "/" nos campos de Nome e Sobrenome. Isso pode causar problemas de qualidade de dados e possíveis falhas em processamentos posteriores.

Ambiente:
- Site: https://demo.opencart.com/
- Navegador: Microsoft Edge
- OS: Windows 11
- Área: Registro de Conta

Pré-requisitos:
- Usuário está na página de registro de conta

Passos para reproduzir

- 1. Acesse https://demo.opencart.com/
- 2. Clique em My Account > Register
- 3. Insira "/" no campo First Name
- 4. Insira "/" no campo Last Name
- 5. Preencha os demais campos obrigatórios com valores válidos
- 6. Clique em Continue

Resultado atual
- A conta é criada com sucesso utilizando "/" como valores de nome

Resultado esperado
- O sistema deve rejeitar caracteres especiais nos campos de nome e exibir uma mensagem de validação

Severidade: Média (Integridade de dados)

Prioridade:
- P2

Evidência
[Ver imagem de evidência](/evidences/BUG-02.png)
