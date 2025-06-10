# Desafio - E_Commerce

Projeto utilizando **MySQL** – Diagrama EER


## 📊 Diagrama EER

![Diagrama EER](https://github.com/NatyAnalytcs-1/Desafio-E_Commerce/blob/main/Desafio%20e_commerce.png)


## 📚 Narrativa do Projeto

### 🛒 PRODUTO
- Os produtos são vendidos por uma única plataforma online.
- Podem ter **vendedores terceiros** distintos.
- Cada produto possui um **fornecedor**.
- Um ou mais produtos podem compor um **pedido**.

**Cardinalidades:**
- Um produto pode estar relacionado a muitos pedidos (N:1 com `produto_pedido`).
- Um produto pode ter múltiplos fornecedores (`produto_fornecedor`, N:N).
- Um produto pode estar em diversos estoques (`produto_estoque`, N:N).
- Um produto pode ser vendido por múltiplos vendedores terceiros (`produto_vendedor_terceiro`, N:N).

---

### 👤 CLIENTE
- Pode se cadastrar com **CPF ou CNPJ**, mas **nunca ambos**.
- O endereço do cliente é usado para **calcular o frete** e em **casos de cancelamento**.
- Um cliente pode ter **mais de um pedido**.
- Um cliente pode ter **mais de uma forma de pagamento**.

**Cardinalidades:**
- Um cliente pode ter vários endereços (1:N).
- Um cliente pode ter vários pedidos (1:N).
- Um cliente pode ter várias formas de pagamento (1:N).

---

### 📦 PEDIDO
- Criado por um cliente.
- Contém informações do endereço de entrega, data e status.
- Um pedido pode conter **um ou mais produtos**.
- Um pedido pode ser **cancelado**.
- Possui **código de rastreio**, **frete**, e **prazo para devolução**.
- Cada pedido está vinculado a **uma única forma de pagamento**.

**Cardinalidades:**
- Um pedido pode ter muitos produtos (N:N com `produto_pedido`).
- Um pedido pertence a um cliente (N:1).
- Um pedido possui um endereço (N:1).
- Um pedido possui **uma forma de pagamento** (N:1).

---

### 🧾 FORMA DE PAGAMENTO
- Um cliente pode ter várias formas cadastradas.
- Uma forma de pagamento pode ser usada em vários pedidos.

**Cardinalidades:**
- Forma de pagamento: 1 cliente → N formas
- Pedido: 1 forma → N pedidos

---

### 🚚 ENDEREÇO
- Um cliente pode ter mais de um endereço.
- Cada pedido está vinculado a **um endereço de entrega**.

**Cardinalidades:**
- 1 cliente → N endereços
- 1 pedido → 1 endereço

---

### 🧑‍🏭 FORNECEDOR & ESTOQUE
- Cada produto possui pelo menos **um fornecedor**.
- Cada produto possui **quantidade e localização em estoque**.

**Cardinalidades:**
- Produto → N fornecedores (via `produto_fornecedor`)
- Produto → N estoques (via `produto_estoque`)

---

### 👥 TERCEIROS VENDEDORES
- Um produto pode ser vendido por múltiplos **terceiros**.
- Cada terceiro pode vender múltiplos produtos.

**Cardinalidades:**
- N:N entre produto e terceiro (`produto_vendedor_terceiro`)

---

## 🔧 Tecnologias
- MySQL Workbench
- GitHub
- SQL DDL

---

Feito com 💻 por [NatyAnalytics-1](https://github.com/NatyAnalytics-1)
