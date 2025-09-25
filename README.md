# 🛒 E-Commerce Recommendation System (Em Construção)

## 📄 Descrição do Projeto
Este projeto tem como objetivo desenvolver um **sistema de recomendação para e-commerce** baseado em análise de dados. O sistema sugere produtos relevantes aos clientes utilizando diferentes estratégias de recomendação, proporcionando insights sobre comportamento de usuários e produtos.  

O projeto está em **construção**, portanto algumas funcionalidades ainda estão sendo implementadas e o código pode ser atualizado frequentemente.

---

## 🔍 Tipos de Recomendações Implementadas

O sistema combina diferentes técnicas para gerar recomendações mais precisas e diversificadas:

### 1️⃣ Popularidade / Ranking
- Recomenda produtos mais populares ou mais bem avaliados.  
- Ideal para **clientes novos** (cold start).  
- **Colunas usadas:** `ReviewCount`, `Rating`  
- **Saída:** Top N produtos mais populares.

### 2️⃣ Histórico do Usuário (User-Item Collaborative Filtering)
- Recomenda produtos com base no histórico de compras e avaliações do usuário.  
- Técnicas: **Matrix Factorization (SVD)**  
- **Colunas usadas:** `ID`, `ProdID`, `Rating`  
- **Saída:** Top N produtos personalizados para cada usuário.

### 3️⃣ Clientes Parecidos (User-User Collaborative Filtering)
- Recomenda produtos com base no comportamento de usuários similares.  
- Técnica: cálculo de similaridade entre usuários (cosine similarity ou Pearson)  
- **Colunas usadas:** `ID`, `ProdID`, `Rating`  
- **Saída:** Produtos comprados por usuários parecidos que o usuário atual ainda não comprou.

### 4️⃣ Itens Comprados Juntos (Item-Item Collaborative Filtering)
- Recomenda produtos que costumam ser comprados juntos (cross-sell).  
- Técnica: cálculo de similaridade entre produtos  
- **Colunas usadas:** `ID`, `ProdID`, `Rating`  
- **Saída:** Produtos relacionados aos que o usuário já comprou.

### 5️⃣ Content-Based
- Recomenda produtos semelhantes aos que o usuário gostou, com base nos atributos do produto.  
- **Colunas usadas:** `Category`, `Brand`, `Description`, `Tags`  
- **Técnica:** vetorização de texto (`TF-IDF` ou embeddings) + cálculo de similaridade entre produtos  
- **Saída:** Produtos similares com base em conteúdo/atributos.

### 6️⃣ Sistema Híbrido
- Combina múltiplas estratégias de recomendação para gerar listas mais precisas e diversificadas.  
- Pode ponderar popularidade, histórico, usuários similares e atributos de produto.  
- **Saída:** Lista final de produtos recomendados para cada usuário, equilibrando personalização, popularidade e similaridade.

---

## 🗂 Dataset
O dataset utilizado contém as seguintes colunas:

- `ID`: ID do usuário  
- `ProdID`: ID do produto  
- `Rating`: Avaliação do produto pelo usuário  
- `ReviewCount`: Número de avaliações do produto  
- `Category`: Categoria do produto  
- `Brand`: Marca do produto  
- `Name`: Nome do produto  
- `ImageURL`: Link da imagem do produto  
- `Description`: Descrição do produto  
- `Tags`: Palavras-chave ou tags do produto  

> Observação: É possível utilizar datasets públicos como o **Amazon Reviews (Electronics)** ou outros datasets de e-commerce para testes.

---

## ⚙️ Ferramentas e Tecnologias
- Linguagem: **Python**  
- Bibliotecas: `pandas`, `NumPy`, `scikit-learn`, `TensorFlow` (opcional para modelos mais complexos)  
- Técnicas: **Filtragem Colaborativa, Content-Based, Matrix Factorization, SVD, KNN**  

---

## 🎯 Resultados Esperados
- Para cada usuário: lista de **produtos recomendados**, considerando:  
  - Popularidade  
  - Histórico de compras  
  - Usuários similares  
  - Produtos semelhantes (item-item / content-based)  
- Informações exibidas: `Name`, `Category`, `Brand`, `Rating`, `ImageURL`  
- Possível feedback do usuário para **atualizar recomendações** dinamicamente.
