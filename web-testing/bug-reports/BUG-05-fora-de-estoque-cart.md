# BUG-05 — Produto fora de estoque pode ser adicionado ao carrinho e seguir para checkout

Sumário:
- Produtos marcados como "Out of Stock" podem ser adicionados ao carrinho e avançar até o checkout. Isso pode causar falhas em pedidos, necessidade de reembolso e insatisfação do cliente.

Ambiente:
- Site: https://demo.opencart.com/
- Navegador: Microsoft Edge
- OS: Windows 11
- Área: Carrinho / Checkout

Passos para reproduzir

- 1. Acesse a página inicial da loja
- 2. Selecione um produto marcado como "Out of Stock"
- 3. Clique em Add to Cart
- 4. Vá para o Shopping Cart
- 5. Prossiga para o Checkout

Resultado atual
- O produto fora deS estoque é adicionado ao carrinho e o checkout é permitido

Resultado esperado
- O sistema deve bloquear a adição de produtos fora de estoque e exibir uma mensagem de erro clara

Severidade: Alta (Impacto no negócio / fluxo de compra)

Prioridade:
- P1

Evidência
[Ver imagem de evidência](/evidences/BUG-05.png)
