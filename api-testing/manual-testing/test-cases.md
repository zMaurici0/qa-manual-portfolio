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

Segue exemplo: [Ver print](../evidences/login.png)
 
> ⚠️ O token expira em 10 minutos. Caso expire durante a execução, refaça o login para obter um novo token.

---

## 📂 Usuários

---

## CT-01 - Listar usuários cadastrados

- **Método:** GET
- **Endpoint:** /usuarios
- **Objetivo:** Verificar se a listagem de usuários é retornada corretamente
- **Pré-requisito:** Nenhum

**Resultado esperado:**
- Status HTTP: 200
- Campo quantidade presente com valor numérico
- Campo usuarios presente e com itens

**Resultado obtido:** Status 200 retornado, campos quantidade e usuarios presentes

**Evidência:** [Ver print](../evidences/CT-01.png)

**Status:** Passou

---

## CT-02 - Buscar usuário por ID válido
 
- **Método:** GET
- **Endpoint:** /usuarios/{_id}
- **Objetivo:** Verificar se um usuário é retornado corretamente ao buscar por ID válido
- **Pré-requisito:** Usar um _id retornado no CT-01

**Resultado esperado:**
- Status HTTP: 200
- Campos nome, email, administrador e _id presentes na resposta
 
**Resultado obtido:** Status 200 retornado, todos os campos estão presentes na resposta

**Evidência:** [Ver print](../evidences/CT-02.png)
 
**Status:** Passou
 
---

## CT-03 - Buscar usuário por ID inexistente
 
- **Método:** GET
- **Endpoint:** /usuarios/{_id}
- **Objetivo:** Verificar se a API retorna erro ao buscar um ID que não existe
- **Pré-requisito:** O id deve ter exatamente 16 alfanuméricos
 
**ID utilizado:** A7fK2mQ9Zx4Lp8Tn
 
**Resultado esperado:**
- Status HTTP: 400
- message: "Usuário não encontrado"
 
**Resultado obtido:** Status 400 retornado, mensagem presente na resposta
 
**Evidência:** [Ver print](../evidences/CT-03.png)
 
**Status:** Passou 
 
---

## CT-04 - Cadastrar usuário administrador com dados válidos
 
- **Método:** POST
- **Endpoint:** /usuarios
- **Objetivo:** Verificar se um novo usuário administrador é cadastrado com sucesso
- **Pré-requisito:** O email utilizado não pode estar cadastrado na base
 
**Body (application/json):**
```json
{
  "nome": "Fulano Ciclano",
  "email": "fulano_teste@qa.com",
  "password": "teste123",
  "administrador": "true"
}
```
 
> Use um email diferente a cada execução para evitar conflito com usuários já cadastrados. Salve o _id retornado para os próximos testes.
 
**Resultado esperado:**
- Status HTTP: 201
- message: "Cadastro realizado com sucesso"
- Campo _id presente na resposta
 
**Resultado obtido:** Status 201 retornado, mensagem presente na resposta
 
**Evidência:** [Ver print](../evidences/CT-04.png)
  
**Status:** Passou
 
---

## CT-05 - Cadastrar usuário com email já utilizado
 
- **Método:** POST
- **Endpoint:** /usuarios
- **Objetivo:** Verificar se um novo usuário administrador é cadastrado com sucesso
- **Pré-requisito:** O email utilizado não pode estar cadastrado na base
 
**Body (application/json):**
```json
{
  "nome": "Outro usuário",
  "email": "fulano_teste@qa.com",
  "password": "senha",
  "administrador": "false"
}
```
 
**Resultado esperado:**
- Status HTTP: 400
- message: "Este email já está sendo usado"
 
**Resultado obtido:** Status 400 retornado, mensagem presente na resposta
 
**Evidência:** [Ver print](../evidences/CT-05.png)
  
**Status:** Passou
 
---

## CT-06 - Editar usuário com dados válidos
 
- **Método:** PUT
- **Endpoint:** /usuarios/{_id}
- **Objetivo:** Verificar se os dados de um usuário são alterados com sucesso
- **Pré-requisito:** Usar o _id retornado no CT-04
 
**Body (application/json):**
```json
{
  "nome": "Fulano Editado",
  "email": "fulano_editado@qa.com",
  "password": "teste123",
  "administrador": "true"
}
```
 
**Resultado esperado:**
- Status HTTP: 200
- message: "Registro alterado com sucesso"
 
**Resultado obtido:** Status 200 retornado, mensagem presente na resposta
 
**Evidência:** [Ver print](../evidences/CT-06.png)
 
**Status:** Passou
 
---

## CT-07 - Excluir usuário cadastrado
 
- **ID:** CT-07
- **Método:** DELETE
- **Endpoint:** /usuarios/{_id}
- **Objetivo:** Verificar se um usuário é excluído com sucesso
- **Pré-requisito:** Usar _id retornado no CT-04
 
**Resultado esperado:**
- Status HTTP: 200
- message: "Registro excluído com sucesso"
 
**Resultado obtido:** Status 200 retornado, mensagem presente na resposta
 
**Evidência:** [Ver print](../evidences/CT-07.png)
 
**Status:** — Passou
 
---
 
## CT-08 - Excluir usuário com ID inexistente
 
- **ID:** CT-08
- **Método:** DELETE
- **Endpoint:** /usuarios/{_id}
- **Objetivo:** Verificar o comportamento da API ao tentar excluir um ID que não existe
- **Pré-requisito:** O id deve ter exatamente 16 alfanuméricos
 
**ID utilizado:** A7fK2mQ9Zx4Lp8Tn
 
**Resultado esperado:**
- Status HTTP: 200
- message: "Nenhum registro excluído"
 
**Resultado obtido:** Status 200 retornado, mensagem presente na resposta
 
**Evidência:**  [Ver print](../evidences/CT-08.png)
 
**Status:** Passou
 
---


