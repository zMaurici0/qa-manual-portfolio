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
- **Testes aprovados:** 15
- **Testes reprovados:** 0
- **Taxa de aprovação:** 100%

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

## CT-02 - Cadastrar usuário administrador com dados válidos
 
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

## CT-03 - Buscar usuário por ID válido
 
- **Método:** GET
- **Endpoint:** /usuarios/{_id}
- **Objetivo:** Verificar se um usuário é retornado corretamente ao buscar por ID válido
- **Pré-requisito:** Usar O _id retornado no CT-02

**Resultado esperado:**
- Status HTTP: 200
- Campos nome, email, administrador e _id presentes na resposta
 
**Resultado obtido:** Status 200 retornado, todos os campos estão presentes na resposta

**Evidência:** [Ver print](../evidences/CT-02.png)
 
**Status:** Passou
 
---

## CT-04 - Buscar usuário por ID inexistente
 
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
 
## 📂 Produtos
 
---

## CT-09 - Listar produtos cadastrados
 
- **Método:** GET
- **Endpoint:** /produtos
- **Objetivo:** Verificar se a listagem de produtos é retornada corretamente
- **Pré-requisito:** Nenhum
 
**Body:** Nenhum
 
**Resultado esperado:**
- Status HTTP: 200
- Campo quantidade presente com valor numérico
- Campo produtos presente e com itens
 
**Resultado obtido:** Status 200 retornado, quantidade e produtos presentes na resposta
 
**Evidência:** [Ver print](../evidences/CT-09.png)
 
**Status:** Passou
 
---

## CT-10 - Cadastrar produto como administrador
 
- **Método:** POST
- **Endpoint:** /produtos
- **Objetivo:** Verificar se um produto é cadastrado com sucesso por um usuário administrador
- **Pré-requisito:** Realizar login e informar o token no header
 
**Header:**
| Key | Value |
|---|---|
| Authorization | Bearer {token obtido via login} |
 
**Body (application/json):**
```json
{
  "nome": "Mouse Gamer RGB",
  "preco": 350,
  "descricao": "Mouse sem fio",
  "quantidade": 100
}
```

**Resultado esperado:**
- Status HTTP: 201
- message: "Cadastro realizado com sucesso"
- Campo _id presente na resposta
 
**Resultado obtido:** Status 201 retornado, mensagem e id presente na resposta
 
**Evidência:** [Ver print](../evidences/CT-10.png)
  
**Status:** Passou
 
 ---

## CT-11 - Buscar produto por ID válido
 
- **Método:** GET
- **Endpoint:** /produtos/{_id}
- **Objetivo:** Verificar se um produto é retornado corretamente ao buscar por ID válido
- **Pré-requisito:** Usar o _id retornado no CT-10
 
**Resultado esperado:**
- Status HTTP: 200
- Campos nome, preco, descricao, quantidade e _id presentes na resposta
 
**Resultado obtido:** Status 200 retornado, todos os campos estão presentes na resposta
 
**Evidência:** [Ver print](../evidences/CT-11.png)
 
**Status:** Passou
 
---

## CT-12 - Cadastrar produto com nome duplicado
 
- **Método:** POST
- **Endpoint:** /produtos
- **Objetivo:** Verificar se a API impede o cadastro de produto com nome já existente
- **Pré-requisito:** Produto com o mesmo nome já deve estar cadastrado (CT-10)
 
**Header:**
| Key | Value |
|---|---|
| Authorization | Bearer {token obtido via login} |
 
**Body (application/json):**
```json
{
  "nome": "Mouse Gamer RGB",
  "preco": 200,
  "descricao": "Produto duplicado",
  "quantidade": 10
}
```
 
**Resultado esperado:**
- Status HTTP: 400
- message: "Já existe produto com esse nome"
 
**Resultado obtido:** Status 400 retornado, mensagem presente na resposta
 
**Evidência:** [Ver print](../evidences/CT-12.png)
 
**Status:** Passou
 
---

## CT-13 - Cadastrar produto sem token de autenticação
 
- **Método:** POST
- **Endpoint:** /produtos
- **Objetivo:** Verificar se a API bloqueia o cadastro sem token de autenticação
- **Pré-requisito:** Nenhum — não informar token no header
 
**Body (application/json):**
```json
{
  "nome": "Produto Sem Token",
  "preco": 100,
  "descricao": "Teste sem autenticação",
  "quantidade": 10
}
```
 
**Resultado esperado:**
- Status HTTP: 401
- message: "Token de acesso ausente, inválido, expirado ou usuário do token não existe mais"
 
**Resultado obtido:** Status 401 retornado, mensagem presente na resposta
 
**Evidência:** [Ver print](../evidences/CT-13.png)
 
**Status:** Passou
 
---

## CT-14 - Editar produto como administrador
 
- **Método:** PUT
- **Endpoint:** /produtos/{_id}
- **Objetivo:** Verificar se os dados de um produto são alterados com sucesso
- **Pré-requisito:** Token de administrador válido e _id do produto criado no CT-10
 
**Header:**
| Key | Value |
|---|---|
| Authorization | Bearer {token obtido via login} |
 
**Body (application/json):**
```json
{
  "nome": "Mouse Gamer RGB Editado",
  "preco": 400,
  "descricao": "Mouse editado",
  "quantidade": 80
}
```
 
**Resultado esperado:**
- Status HTTP: 200
- message: "Registro alterado com sucesso"
 
**Resultado obtido:** Status 200 retornado, mensagem presente na resposta
 
**Evidência:** [Ver print](../evidences/CT-14.png)
 
**Status:** Passou
 
---

## CT-15 - Excluir produto como administrador
 
- **Método:** DELETE
- **Endpoint:** /produtos/{_id}
- **Objetivo:** Verificar se um produto é excluído com sucesso
- **Pré-requisito:** Token de administrador válido e _id do produto criado no CT-10.
 
**Header:**
| Key | Value |
|---|---|
| Authorization | Bearer {token obtido via login} |
 
**Resultado esperado:**
- Status HTTP: 200
- message: "Registro excluído com sucesso"
 
**Resultado obtido:** Status 200 retornado, mensagem presente na resposta
 
**Evidência:** [Ver print](../evidences/CT-15.png)
 
**Status:** Passou
 
---

## Cobertura de Testes
 
**Módulos e cenários cobertos:**
 
Usuários
- ✅ GET — Listar usuários (CT-01)
- ✅ POST — Cadastrar usuário administrador (CT-02)
- ✅ GET — Buscar por ID válido (CT-03)
- ✅ GET — Buscar por ID inexistente (negativo) (CT-04)
- ✅ POST — Cadastrar com email duplicado (negativo) (CT-05)
- ✅ PUT — Editar usuário (CT-06)
- ✅ DELETE — Excluir usuário (CT-07)
- ✅ DELETE — Excluir ID inexistente (negativo) (CT-08)
 
Produtos
- ✅ GET — Listar produtos (CT-09)
- ✅ POST — Cadastrar produto como administrador (CT-10)
- ✅ GET — Buscar por ID válido (CT-11)
- ✅ POST — Cadastrar com nome duplicado (negativo) (CT-12)
- ✅ POST — Cadastrar sem token (negativo) (CT-13)
- ✅ PUT — Editar produto (CT-14)
- ✅ DELETE — Excluir produto (CT-15)
