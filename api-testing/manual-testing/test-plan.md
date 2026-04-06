# 📑 Plano de Teste: ServeRest API

## 1. Introdução
Este plano define a estratégia para validar os endpoints públicos e autenticados da API ServeRest, com foco na integridade dos dados, no controle de acesso por perfil de administrador e no comportamento da API diante de entradas inválidas.

## 2. Escopo
- Módulos: Usuários e Produtos
- Endpoints: /usuarios, /usuarios/{_id}, /produtos, /produtos/{_id}
- Métodos HTTP: GET, POST, PUT, DELETE
- Tipos de Teste: Testes Baseados em Script (CT-01 a CT-15), cobrindo fluxos positivos e negativos

## 3. Estratégia de Teste
Será utilizada uma abordagem de Testes Baseados em Script executados manualmente via Postman. Os testes seguirão a ordem definida nos casos de teste para garantir as pré-condições de cada etapa, o _id` gerado no cadastro de usuário e de produto é reutilizado nas requisições de busca, edição e exclusão.

Os testes negativos cobrem cenários como: email duplicado, token ausente e IDs inexistentes, validando que a API responde com os status codes e mensagens corretos.

> Os endpoints de criação, edição e exclusão de produtos exigem autenticação. Antes de executar o módulo de Produtos, realize o login via POST /login com as credenciais do usuário administrador criado no CT-02 e informe o token retornado no header Authorization. O token expira em 10 minutos — caso expire, refaça o login.

## 4. Gerenciamento de Riscos

| Risco | Impacto | Mitigação |
|---|---|---|
| Token de autenticação expirado durante a execução | Alto | Refazer o login e atualizar o token no header antes de continuar |
| Email ou nome de produto já cadastrado na base | Médio | Usar valores únicos a cada ciclo de execução |
| ID de usuário ou produto inexistente ou inválido | Médio | Capturar e reutilizar o _id retornado nos testes de criação (CT-02 e CT-10) |
| Instabilidade da API pública | Baixo | Aguardar normalização e reagendar a execução |

## 5. Critérios de Saída
- 100% dos casos de teste (CT-01 a CT-15) executados
- Nenhum bug de severidade "Crítica" ou "Alta" em aberto