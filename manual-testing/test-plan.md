# 📑 Plano de Teste: OpenCart E-Commerce Demo

## 1. Introdução
Este plano define a estratégia para validar as funcionalidades principais da plataforma OpenCart, com foco na experiência do usuário final e na integridade dos dados.

## 2. Escopo
- Módulos: Registro de Conta, Autenticação, Catálogo, Carrinho e Checkout  
- Tipos de Teste: Teste de Fumaça (Smoke Testing) e Testes Exploratórios

## 3. Estratégia de Teste
Será utilizada uma combinação de Testes Baseados em Script (com base nos casos de teste TC-01 a TC-11) e Testes Exploratórios para identificar comportamentos inesperados, especialmente nas validações de formulários.

## 4. Gerenciamento de Riscos

| Risco                            | Impacto| Mitigação                                                      |
|------------------------------    -------- |------------------------------------------------------------------|
| Ambiente de demonstração instável| Alto  | Limpar cookies/cache periodicamente e reiniciar a sessão    |
| Mudanças na interface do site    | Médio  | Manter locators e passos de teste atualizados                   |

## 5. Critérios de Saída
- 100% dos testes de Smoke executados com sucesso  
- Nenhum bug de severidade "Crítica" ou "Alta" em aberto  
 