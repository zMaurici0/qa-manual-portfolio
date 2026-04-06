# BUG-03 — Usuário bloqueado (Erro 1015) após navegação rápida entre produtos

Sumário:
- A navegação normal do usuário (abrindo produtos rapidamente) aciona o bloqueio de taxa do Cloudflare (Erro 1015). Isso bloqueia usuários e pode impactar negativamente as conversões.

Ambiente:
- Site: https://demo.opencart.com/
- Navegador: Microsoft Edge
- OS: Windows 11
- Área: Navegação de produtos
- Erro: Cloudflare 1015 (Rate Limited)

Passos para reproduzir

- 1. Acesse https://demo.opencart.com/
- 2. Abra a página de um produto
- 3. Imediatamente abra outro produto
- 4. Repita rapidamente (2–3 vezes)
- 5. Continue navegando

Resultado atual
- Usuário é bloqueado com erro Cloudflare 1015 (Rate Limited)

Resultado esperado
- Usuários devem conseguir navegar pelos produtos normalmente.

Severidade: Alta (Bloqueia o uso do site)

Prioridade:
- P1

Evidência
<<<<<<< HEAD:front-testing/bug-reports/BUG-03-rate-limit-navegacao.md
[Ver imagem de evidência](/evidences/BUG-03.png)
=======
[Ver imagem de evidência](/evidences/BUG-04.png)
>>>>>>> 532f0dc82ef1c74397af7217c858c4a989b0d9a5:bug-reports/BUG-03-rate-limit-navegacao.md
