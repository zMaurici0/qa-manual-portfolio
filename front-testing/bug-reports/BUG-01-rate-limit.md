# BUG-01 — Usuário bloqueado após duas tentativas de registro

Sumário:
- Após o comportamento normal de registro (registrar > sair > registrar), o usuário é bloqueado pelo limite de taxa do Cloudflare. Isso impede que usuários continuem no site.

Ambiente:
- Site: https://demo.opencart.com/
- Navegador: Microsoft Edge
- OS: Windows 11
- Área: Fluxo de registro
- Erro: Cloudflare 1015 (Rate Limited)

Passos para reproduzir

- 1. Vá para https://demo.opencart.com/
- 2. Crie uma nova conta
- 3. Logout
- 4. Crie outra conta
- 5. Tente acessar a página de registro novamente

Resultado atual
- Usuário é bloqueado com erro Cloudflare 1015 (Rate Limited)

Resultado esperado
- Usuários normais não devem ser bloqueados após um comportamento padrão. Se for necessária proteção, ela deve ser gradual (aviso / captcha) em vez de um bloqueio rígido.


Severidade: Alta (Bloqueia fluxo do usuário)

Prioridade:
- P1

Evidencia
![Ver imagem de evidência](/evidences/BUG-01.png)