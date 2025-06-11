# Desafio - E_Commerce

Projeto utilizando **MySQL** – Diagrama EER


## 📊 Diagrama EER

![Diagrama EER](https://github.com/NatyAnalytcs-1/Desafio-E_Commerce/blob/main/Desafio%20e_commerce.png)


## 📚 Narrativa do Projeto - Venda de Produtos

### 🛒 PRODUTO
- Os produtos são vendidos por uma única plataforma online.
- Podem ter **vendedores terceiros** distintos.
- Cada produto possui um **fornecedor**.
- Um ou mais produtos podem compor um **pedido**.

**Cardinalidades:**
- Produto <-> Pedido: **N:N** (via `produto_pedido`)
- Produto <-> Fornecedor: **N:N** (via `produto_fornecedor`)
- Produto <-> Estoque: **N:N** (via `produto_estoque`)
- Produto <-> Vendedor Terceiro: **N:N** (via `produto_vendedor_terceiro`)

---

### 👤 CLIENTE
- Pode se cadastrar com **CPF ou CNPJ**, mas **nunca ambos**.
- O endereço do cliente é usado para **calcular o frete** e em **casos de cancelamento**.
- Um cliente pode ter **mais de um pedido**.
- Um cliente pode ter **mais de uma forma de pagamento**.

**Cardinalidades:**
- Cliente → Pedidos: **1:N**
- Cliente → Endereços: **1:N**
- Cliente → Formas de pagamento: **1:N**

---

### 📦 PEDIDO
- Criado por um cliente.
- Contém informações do endereço de entrega, data e status.
- Um pedido pode conter **um ou mais produtos**.
- Um pedido pode ser **cancelado**.
- Possui **código de rastreio**, **frete**, e **prazo para devolução**.
- Cada pedido está vinculado a **uma única forma de pagamento**.

**Cardinalidades:**
- Pedido → Cliente: **N:1**
- Pedido → Endereço: **N:1**
- Pedido → Forma de pagamento: **N:1**
- Pedido <-> Produto: **N:N** (via `produto_pedido`)

---

### 🧾 FORMA DE PAGAMENTO
- Um cliente pode ter várias formas cadastradas.
- Uma forma de pagamento pode ser usada em vários pedidos.

**Cardinalidades:**
- Cliente → Forma de pagamento: **1:N**
- Forma de pagamento → Pedido: **1:N**

---

### 🚚 ENDEREÇO
- Um cliente pode ter mais de um endereço.
- Cada pedido está vinculado a **um endereço de entrega**.

**Cardinalidades:**
- Cliente → Endereço: **1:N**
- Pedido → Endereço: **N:1**

---

## 🧑‍🏭 FORNECEDOR
- Um produto possui pelo menos um fornecedor.
- Um fornecedor pode fornecer diversos produtos.

**Cardinalidades:**
- Produto <-> Fornecedor: **N:N** (via `produto_fornecedor`)

---

## 🏬 ESTOQUE
- Os produtos são armazenados em locais diferentes com quantidades específicas.

**Cardinalidades:**
- Produto <-> Estoque: **N:N** (via `produto_estoque`)

---

### 👥 TERCEIROS VENDEDORES
- Um produto pode ser vendido por múltiplos **terceiros**.
- Cada terceiro pode vender múltiplos produtos.

**Cardinalidades:**
- Produto <-> Terceiro: **N:N** (via `produto_vendedor_terceiro`)

---

## 🔧 Tecnologias
- MySQL Workbench
- GitHub

---

Feito com 💻 por [NatyAnalytics-1](https://github.com/NatyAnalytics-1)
