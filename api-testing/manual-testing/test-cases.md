# Casos de Teste - ServeRest API (Manual)

## Informações do Projeto

- **Projeto:** ServeRest API Testing
- **Aplicação:** https://serverest.dev
- **Ferramenta:** Postman
- **Ambiente:** OS: Windows 11
- **Objetivo:** Verificar o funcionamento dos endpoints de Login, Usuários e Produtos, validando fluxos positivos e negativos, autenticação via token e controle de acesso por perfil de administrador.

---

## Resumo dos Testes

- **Total de testes executados:** 18
- **Módulos testados:** Login, Usuários, Produtos
- **Métodos testados:** GET, POST, PUT, DELETE 
- **Testes aprovados:**
- **Testes reprovados:**
- **Taxa de aprovação:** 

---

## ℹ️ Sobre Autenticação
 
Os endpoints de criação, edição e exclusão de produtos exigem um token de administrador. Antes de executar os testes do módulo de Produtos, realize o login via POST /login com as credenciais do usuário administrador e copie o valor do campo authorization retornado na resposta. Esse token deve ser informado no header Authorization de cada requisição autenticada.

Segue exemplo: [Ver print](./evidences/login.png)
 
> ⚠️ O token expira em 10 minutos. Caso expire durante a execução, refaça o login para obter um novo token.
 

## CT-01 - Listar usuários cadastrados

- **ID:** CT-03
- **Método:** GET
- **Endpoint:** /usuarios
- **Objetivo:** Verificar se a listagem de usuários é retornada corretamente
- **Pré-requisito:** Nenhum

**Body:** Nenhum
**Resultado esperado:**
- Status HTTP: 200
- Campo quantidade presente com valor numérico
- Campo usuarios presente e com itens

**Resultado obtido:** Status 200 retornado, campos quantidade e usuarios presentes

**Evidência:** [Ver print](../evidences/CT-01.png)

**Status:** passou

---

## CT-02 - Buscar usuário por ID válido
 
- **ID:** CT-04
- **Método:** GET
- **Endpoint:** /usuarios/{_id}
- **Objetivo:** Verificar se um usuário é retornado corretamente ao buscar por ID válido
- **Pré-requisito:** Usar um _id retornado no CT-01
**Resultado esperado:**
- Status HTTP: 200
- Campos nome, email, administrador e _id presentes na resposta
 
**Resultado obtido:** Status 200 retornado, todos os campos estão presentes na resposta

**Evidência:** [Ver print](../evidences/CT-02.png)
 
**Status:** — passou
 
---


