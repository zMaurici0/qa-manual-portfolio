# Casos de Teste - OpenCart Demo (Manual)

## Informações do Projeto

- **Projeto:** OpenCart Demo Web Testing
- **Aplicação:** https://demo.opencart.com/
- **Ferramenta:** Microsoft Edge
- **Ambiente:** OS: Windows 11
- **Objetivo:** Verificar o funcionamento das principais funcionalidades da plataforma OpenCart, validando fluxos de registro, autenticação, catálogo de produtos e carrinho de compras.

---

## Resumo dos Testes

- **Total de testes executados:** 11
- **Módulos testados:** Registro de Conta, Autenticação, Catálogo, Carrinho
- **Testes aprovados:**
- **Testes reprovados:**
- **Taxa de aprovação:**

---

## 📂 Registro de Conta

---

## TC-01 - Registro com dados válidos

- **Objetivo:** Verificar se um novo usuário consegue criar uma conta com dados válidos
- **Pré-requisito:** Usuário deve estar na página de registro

**Passos:**
- 1. Vá para https://demo.opencart.com/
- 2. Clique em My Account > Register
- 3. Preencha todos os campos com dados válidos
- 4. Aceite a política de privacidade
- 5. Clique em Continue

**Resultado esperado:**
- Conta criada com sucesso
- Usuário é redirecionado para a página de sucesso/confirmação

**Resultado obtido:** a conta foi criada com sucesso e o usuário redirecionado

**Evidência:** [Ver print](../evidences/CT-01.png)

**Status:** Passou

---

## TC-02 - Registro com email já cadastrado

- **Objetivo:** Verificar se a plataforma impede o registro com um email já existente
- **Pré-requisito:** Uma conta com o email utilizado já deve existir na base

**Passos:**
- 1. Vá para a página de registro
- 2. Preencha as informações utilizando um email já cadastrado
- 3. Clique em Continue

**Resultado esperado:**
- Mensagem de erro exibida: "Warning: E-Mail Address is already registered!"
- A conta não deve ser criada

**Resultado obtido:** A mensagem de erro foi exibida com sucesso 

**Evidência:** [Ver print](../evidences/CT-02.png)

**Status:** Passou

---

## 📂 Autenticação

---

## TC-03 - Login com dados válidos

- **Objetivo:** Verificar se o usuário consegue realizar login com credenciais válidas
- **Pré-requisito:** Usuário deve ter uma conta existente

**Passos:**
- 1. Clique em My Account > Login
- 2. Preencha um email e senha válidos
- 3. Clique em Login

**Resultado esperado:**
- Usuário logado com sucesso
- Página de informações da conta é exibida

**Resultado obtido:** Login bem sucedido, página de informações da conta exibida

**Evidência:** [Ver print](../evidences/CT-03.png)

**Status:** Passou

---

## TC-04 - Login com senha incorreta

- **Objetivo:** Verificar se a plataforma bloqueia o login ao informar uma senha inválida
- **Pré-requisito:** Usuário deve ter uma conta existente

**Passos:**
- 1. Clique em My Account > Login
- 2. Preencha um email válido e uma senha incorreta
- 3. Clique em Login

**Resultado esperado:**
- Mensagem de erro é exibida
- Usuário permanece deslogado

**Resultado obtido:** Mensagem de erro foi exibida e o usuário permaneceu deslogado

**Evidência:** [Ver print](../evidences/CT-04.png)

**Status:** Passou

---

## TC-05 - Logout

- **Objetivo:** Verificar se o usuário consegue encerrar a sessão com sucesso
- **Pré-requisito:** Usuário deve estar logado

**Passos:**
- 1. Clique em My Account > Logout
- 2. Clique em Continue

**Resultado esperado:**
- Usuário é redirecionado para a página de logout
- Sessão é finalizada

**Resultado obtido:** Logout realizado com sucesso

**Evidência:** [Ver print](../evidences/CT-05.png)

**Status:** Passou

---

## 📂 Catálogo

---

## TC-06 - Buscar produto existente

- **Objetivo:** Verificar se a busca retorna resultados ao pesquisar por um produto existente
- **Pré-requisito:** Nenhum

**Passos:**
- 1. Use a barra de pesquisa
- 2. Pesquise por um produto conhecido (ex: iPhone)

**Resultado esperado:**
- Produtos correspondentes são exibidos nos resultados

**Resultado obtido:** O produto correspondente foi exibido

**Evidência:** [Ver print](../evidences/CT-06.png)

**Status:** Passou

---

## TC-07 - Buscar produto inexistente

- **Objetivo:** Verificar se a plataforma exibe mensagem adequada ao pesquisar por um produto que não existe
- **Pré-requisito:** Nenhum

**Passos:**
- 1. Use a barra de pesquisa
- 2. Pesquise por uma string aleatória (ex: zzzzz123)

**Resultado esperado:**
- Mensagem "There is no product that matches the search criteria." é exibida

**Resultado obtido:** mensagem exibida com sucesso

**Evidência:** [Ver print](../evidences/CT-07.png)

**Status:** Passou

---

## TC-08 - Navegar por categoria

- **Objetivo:** Verificar se a página de categoria é carregada corretamente ao clicar em uma categoria
- **Pré-requisito:** Nenhum

**Passos:**
- 1. Clique em uma das categorias do menu (ex: Desktops / Components)

**Resultado esperado:**
- Página da categoria é exibida com os produtos correspondentes

**Resultado obtido:** Produtos correspondentes foram exibidos

**Evidência:** [Ver print](../evidences/CT-08.png)

**Status:** Passou

---

## 📂 Carrinho

---

## TC-09 - Adicionar produto ao carrinho

- **Objetivo:** Verificar se um produto é adicionado ao carrinho com sucesso
- **Pré-requisito:** Nenhum

**Passos:**
- 1. Abra a página de qualquer produto
- 2. Clique em Add to Cart

**Resultado esperado:**
- Produto adicionado ao carrinho com sucesso
- Contador do carrinho é incrementado

**Resultado obtido:** O produto foi adicionado ao carrinho e o contador aumentou em 1

**Evidência:** [Ver print](../evidences/CT-09.png)

**Status:** Passou

---

## TC-10 - Atualizar quantidade no carrinho

- **Objetivo:** Verificar se a quantidade e o preço total são atualizados corretamente no carrinho
- **Pré-requisito:** Deve haver pelo menos um item no carrinho

**Passos:**
- 1. Clique em Shopping Cart
- 2. Aumente a quantidade do item
- 3. Clique em Update

**Resultado esperado:**
- Quantidade atualizada com sucesso
- Preço total atualizado de acordo com a nova quantidade

**Resultado obtido:** Quantidade e preço total foram atualizados com sucesso

**Evidência:** [Ver print](../evidences/CT-10.png)

**Status:** Passou

---

## TC-11 - Remover item do carrinho

- **Objetivo:** Verificar se um item é removido do carrinho com sucesso
- **Pré-requisito:** Deve haver pelo menos um item no carrinho

**Passos:**
- 1. Clique em Shopping Cart
- 2. Clique no botão de remover o item

**Resultado esperado:**
- Item removido com sucesso
- Carrinho fica vazio e mensagem de carrinho vazio é exibida

**Resultado obtido:** Item removido e a mensagem foi exibida

**Evidência:** [Ver print](../evidences/CT-11.png)

**Status:** Passou

---

## Cobertura de Testes

**Módulos e cenários cobertos:**

Registro de Conta
- TC-01 — Registro com dados válidos
- TC-02 — Registro com email já cadastrado (negativo)

Autenticação
- TC-03 — Login com dados válidos
- TC-04 — Login com senha incorreta (negativo)
- TC-05 — Logout

Catálogo
- TC-06 — Buscar produto existente
- TC-07 — Buscar produto inexistente (negativo)
- TC-08 — Navegar por categoria

Carrinho
- TC-09 — Adicionar produto ao carrinho
- TC-10 — Atualizar quantidade no carrinho
- TC-11 — Remover item do carrinho
