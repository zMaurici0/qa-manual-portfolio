# BUG-03 — Usuário bloqueado (Erro 1015) após navegação rápida entre produtos

Sumário:
- A navegação normal do usuário (abrindo produtos rapidamente) aciona o bloqueio de taxa do Cloudflare (Erro 1015). Isso bloqueia usuários legítimos e pode impactar negativamente as conversões.

Ambiente:
- Site: https://demo.opencart.com/
- Navegador: Chrome
- OS: macOS
- Área: Navegação de produtos
- Erro: Cloudflare 1015 (Rate Limited)

Pré-condições:
- Usuário consegue acessar a loja normalmente

Passos para reproduzir

- 1. Acesse https://demo.opencart.com/
- 2. Abra a página de um produto
- 3. Imediatamente abra outro produto
- 4. Repita rapidamente (2–3 vezes)
- 5. Continue navegando

Resultado atual
- Usuário é bloqueado com erro Cloudflare 1015 (Rate Limited)

Resultado esperado
- Usuários devem conseguir navegar pelos produtos normalmente. Caso seja necessário proteção contra bots, o sistema deve aplicar medidas progressivas (como limitação gradual ou captcha) em vez de bloquear usuários reais

Severidade: Alta (Bloqueia o uso do site)

Prioridade:
- P1

Evidência
![Ver imagem de evidência](/evidences/BUG-04.png)