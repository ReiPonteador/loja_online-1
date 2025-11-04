# 🛍️ Projeto 3: Loja Online

**Disciplina:** Banco de Dados  
**Curso:** Técnico em Desenvolvimento de Sistemas  
**Aluno(a):** [Seu Nome]  
**Turma:** [Sua Turma]  
**Professor:** [Nome do Professor]
**Data de Entrega:** [dd/mm/aaaa]  

---

## 🎯 Objetivo
Desenvolver uma aplicação simples de loja online que integra:
- Um banco de dados relacional (**MySQL**) para lojas, produtos e características.
- Um banco NoSQL (**MongoDB Atlas**) para avaliações de produtos e logs de navegação.
- Uma interface web em **PHP** que exibe produtos e seus estoques dinâmicos.

Este projeto demonstra como usar diferentes tipos de bancos de dados conforme a natureza dos dados.

---

## 🛠️ Tecnologias Utilizadas
- 💾 **MySQL** – Para dados estruturados e transacionais
- 📦 **MongoDB Atlas** – Para dados flexíveis (avaliações, comentários)
- 💬 **PHP** – Integração e exibição na web
- 🔗 **GitHub** – Versionamento de código
- 🖥️ **XAMPP** – Ambiente local para execução

---

## 🗄️ Banco de Dados Relacional (MySQL)

### Banco: `loja_online`

### Estrutura das Tabelas
```sql
-- Tabela: Produto
--- tipo (enum: Novo, Usado, Liquidacao, Promocao, Outros)
--- categoria (set: Eletronico, Telefonia, Informatica, Eletrodomesticos, Acessorios, Outros)
--- desconto para produtos usados (decimal)
produto (id, nome, descricao, preco, tipo, categoria, data_de_lancamento, desconto)

-- Características do Produto
caracteristica (id, nome, descricao)

-- Relação entre os produtos e suas respectivas características
produto_caracteristica (id, id_prodtudo, id_caracteristica)

-- Loja
loja (id, nome, telefone, rua, numero, bairro, cep, complemento, cidade)

-- Estoque
estoque (id, id_produto, id_loja, quantidade_disponivel)
