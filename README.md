# Projeto QA Manual – Web & API Testing

![Manual Testing](https://img.shields.io/badge/Testing-Manual-blue)
![Postman](https://img.shields.io/badge/API-Postman-orange)
![Edge](https://img.shields.io/badge/Browser-Microsoft%20Edge-blue)
![Windows](https://img.shields.io/badge/OS-Windows%2011-lightgrey)

Este projeto demonstra habilidades práticas de Quality Assurance (QA) aplicadas a testes Web e de API de forma manual, utilizando Postman e Microsoft Edge como ferramentas principais.

O objetivo deste repositório é praticar atividades comuns do dia a dia de um QA Engineer, como elaboração de planos de teste, criação de casos de teste, execução manual e documentação de evidências.

O projeto foi dividido em dois módulos, cada um com sua própria aplicação testada, simulando cenários reais de testes, incluindo:

- Criação e execução de casos de teste manuais
- Validação de respostas de API (status codes e mensagens)
- Verificação de fluxos positivos e negativos
- Testes de autenticação e controle de acesso
- Validação do comportamento esperado da aplicação web

---

## 📋 Estrutura do Projeto

```
QA-MANUAL-PORTFOLIO/
│
├── api-testing/
│   ├── evidences/
│   └── manual-testing/
│       ├── test-cases.md
│       └── test-plan.md
│
└── web-testing/
    ├── bug-reports/
    ├── evidences/
    └── manual-testing/
        ├── test-cases.md
        └── test-plan.md
```

---

## 🎯 Fases de Teste Realizadas

### 1️⃣ Testes de API — ServeRest

**Objetivo:** Validar os endpoints da API ServeRest, garantindo que as respostas retornem os dados, status codes e mensagens esperados, incluindo cenários de erro e controle de acesso.

**O que foi feito:**
- Elaboração do plano de teste e casos de teste para os módulos de Usuários e Produtos
- Validação de status codes HTTP (200, 201, 400, 401)
- Verificação da estrutura das respostas em JSON
- Testes de autenticação via Bearer Token
- Testes negativos: email duplicado, token ausente e IDs inexistentes

**Resultados:**
- 15 casos de teste executados
- Taxa de aprovação: 100%
- Todos os endpoints responderam com os status codes e mensagens esperados

---

### 2️⃣ Testes Web — OpenCart Demo

**Objetivo:** Validar as funcionalidades principais da plataforma OpenCart, simulando ações reais do usuário nos módulos de registro, autenticação, catálogo e carrinho.

**O que foi feito:**
- Elaboração do plano de teste e casos de teste para os módulos principais da aplicação
- Validação de fluxos de registro e login de usuários
- Verificação do comportamento da busca de produtos
- Validação do carrinho de compras (adicionar, atualizar quantidade e remover itens)
- Testes negativos: registro com email duplicado e login com senha incorreta

**Resultados:**
- 11 casos de teste executados
- Taxa de aprovação: 100%
- Todos os fluxos principais da aplicação validados com sucesso

---

## 💼 Skills Demonstradas

- [x] Elaboração de Plano de Teste
- [x] Criação de Casos de Teste (positivos e negativos)
- [x] Testes Manuais de API (REST — GET, POST, PUT, DELETE)
- [x] Testes de CRUD em API
- [x] Testes de Autenticação (Bearer Token)
- [x] Testes de Controle de Acesso (perfil administrador)
- [x] Validação de Status Codes e Respostas de API
- [x] Testes Funcionais e de Interface do Usuário (UI)
- [x] Testes Exploratórios
- [x] Documentação de Evidências
- [x] Registro e Documentação de Bugs

---

## 📊 Estatísticas do Projeto

| Módulo | Ferramenta | Casos de Teste | Aprovados | Taxa |
|---|---|---|---|---|
| API — ServeRest | Postman | 15 | 15 | 100% |
| Web — OpenCart | Microsoft Edge | 11 | 11 | 100% |
| **Total** | | **26** | **26** | **100%** |

---

## 🛠️ Ferramentas & Tecnologias

| Categoria | Ferramenta |
|---|---|
| Testes de API | Postman |
| Testes Web | Microsoft Edge |
| Documentação | Markdown |
| Versionamento | Git, GitHub |
| Sistema Operacional | Windows 11 |

---

## 🌐 Aplicações Testadas

### ServeRest API
API REST gratuita que simula uma loja virtual, utilizada para praticar testes de API com autenticação, CRUD e validação de regras de negócio.

- Documentação: https://serverest.dev
- Endpoints testados: /usuarios, /usuarios/{_id}, /produtos, /produtos/{_id}

### OpenCart Demo
Plataforma de e-commerce de demonstração, utilizada para praticar testes web manuais em fluxos reais de usuário.

- Aplicação: https://demo.opencart.com
- Módulos testados: Registro de Conta, Autenticação, Catálogo e Carrinho
