# BUG-05 — Registro aceita formato de email irrealista (validação fraca de email)

Sumário:
- O sistema permite o registro de contas utilizando formatos mínimos/irrealistas de email (ex: 2@a.c). Isso aumenta o risco de spam/contas falsas e prejudica a confiabilidade da comunicação.

Ambiente:
- Site: https://demo.opencart.com/
- Navegador: Microsoft Edge
- OS: Windows 11
- Área: Registro de Conta

Passos para reproduzir

- 1. Acesse https://demo.opencart.com/
- 2. Vá em My Account > Register
- 3. Preencha os campos obrigatórios com valores válidos
- 4. Insira o email: 2@a.c
- 5. Envie o formulário (Continue)

Resultado atual
- A conta é criada com sucesso

Resultado esperado
- O sistema deve aplicar validações mais rigorosas e/ou exigir verificação de email (etapa de confirmação)

Severidade: Média (Qualidade de dados / risco de abuso)

Prioridade:
- P2

Evidência
![Ver imagem de evidência](/evidences/BUG-04.png)