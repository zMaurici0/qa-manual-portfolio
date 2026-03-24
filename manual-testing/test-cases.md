# Casos de teste - OpenCart Demo (Manual)
---------------------------------------------------------
Aplicação:
- https://demo.opencart.com/

Ambiente:
- OS: Windows 11
- Navegador: Microsoft Edge

------------------------------------------------------------

## TC-01 - Registro com dados válidos

Pré-requisitos
- Usuário deve estar na página de registro

Passos

- 1. vá para https://demo.opencart.com/
- 2. Clique em My Account > Register
- 3. Preencha todos os campos com dados válidos
- 4. Aceite a política de privacidade
- 5. Clique em Continue

Resultado esperado

- Conta criada
- Usuário é redirecionado para a página de sucesso/confirmação
-----------------------------------------------------------------------

## TC-02 - Registro com email existente

Pré-requisitos
- uma conta com o email utilizado já deve existir

Passos

- 1. Vá para a página de registro 
- 2. Preencha as informações utilizando um email existente
- 3. Clique em Continue

Resultado Esperado

- deve aparecer um erro na tela escrito:  Warning: E-Mail Address is already registered!
- a conta não deve ser criada
--------------------------------------------------------------------------------------------

## TC-03 - Login com dados válidos

pré-requisitos
- Usuário deve ter uma conta existente

Passos

- 1. Clique em My Account > Login
- 2. Preencha um email e senha válidos
- 3. Clique em Login

Resultado esperado

- Usuário logado
- Página de informações da conta é mostrado
----------------------------------------------------------------------------------------------

## TC-04 - Login com senha errada

pré-requisitos
- Usuário deve ter uma conta existente

Passos

- 1. Clique em My Account > Login
- 2. Preencha um email válido e uma senha inválida
- 3. Clique em Login

Resultado esperado

- Mensagem de erro é mostrada
- Usuário permanece deslogado
----------------------------------------------------------------------------------------------

## TC-05 - Logout

pré-requisitos
- Usuário deve estar logado

Passos
 
- 1. Clique em My Account > Logout
- 2. Clique em Continue

Resultado esperado

- Usuário é redirecionado para a página de confirmação de logout
- Sessão é finalizada
----------------------------------------------------------------------------------------------

## TC-06 - Procurar um produto existente

pré-requisitos
- nenhuma

Passos
 
- 1. Use a barra de pesquisa
- 2. pesquise por um produto conhecido (ex: iPhone)

Resultado esperado

- Produtos correspondentes são exibidos nos resultados
----------------------------------------------------------------------------------------------

## TC-07 - Procurar um produto não existente

pré-requisitos
- nenhuma

Passos
 
- 1. Use a barra de pesquisa
- 2. pesquise por uma string aleatória (ex: zzzzz123)

Resultado esperado

- Mensagem escrita "No results" / "No products found"
----------------------------------------------------------------------------------------------

## TC-08 - Adicionar produto ao carrinho

pré-requisitos
- nenhuma

Passos
 
- 1. Abra a página de qualquer produto
- 2. Clique em Add to Cart

Resultado esperado

- Produto adicionado ao carrinho
- contador do carrinho aumenta
----------------------------------------------------------------------------------------------

## TC-09 - Atualizar quantidade no carrinho

pré-requisitos
- deve haver pelo menos um item no carrinho

Passos
 
- 1. Cliqu em Shopping Cart
- 2. Aumente a quantidade
- 3. Clique em Update

Resultado esperado

- Quantidade atualiza
- preço total atualiza de acordo com a quantidade
----------------------------------------------------------------------------------------------

## TC-10 - Remover item do carrinho

pré-requisitos
- deve haver pelo menos um item no carrinho

Passos
 
- 1. Clique em Shopping Cart
- 2. Remova o item

Resultado esperado

- Carrinho fica vazio
- mensagem de carrinho vazio é mostrada
----------------------------------------------------------------------------------------------

## TC-11 - Navegar por categoria 

pré-requisitos
- nehhum

Passos
 
- 1. Clique em uma das categorias (ex: Desktop/Components)

Resultado esperado

- Página da categoria é mostrada
----------------------------------------------------------------------------------------------
