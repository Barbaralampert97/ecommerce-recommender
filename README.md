🛒 Sistema de Recomendação de Produtos para E-Commerce (Em Construção)
📄 Descrição do Projeto

Este projeto desenvolve um sistema de recomendação para e-commerce, sugerindo produtos relevantes aos clientes com base em dados de interações e atributos dos produtos.

O projeto está em construção, algumas funcionalidades ainda estão sendo implementadas.

🔍 Tipos de Recomendações

Popularidade / Ranking – Produtos mais populares ou melhor avaliados (cold start).

Histórico do Usuário (User-Item CF) – Produtos personalizados pelo histórico de compras/avaliações.

Clientes Parecidos (User-User CF) – Produtos comprados por usuários similares que o cliente ainda não comprou.

Itens Comprados Juntos (Item-Item CF) – Produtos frequentemente comprados juntos (cross-sell).

Content-Based – Produtos semelhantes com base em atributos (Category, Brand, Description, Tags).

Sistema Híbrido – Combina as estratégias acima para recomendações mais precisas.

🗂 Estrutura do Dataset

products.csv – Produtos Únicos

Cada linha representa um produto distinto.

Colunas: ProdID, Name, Category, Brand, Description, Tags, ReviewCount, Rating.

interactions.csv – Histórico Cliente × Produto

Cada linha = avaliação ou compra.

Colunas: CustomerID, ProdID, Rating.

Pode haver múltiplas interações por cliente ou produto.

customers.csv – Clientes Fictícios

Cadastro de clientes gerado com dados fictícios para análise.

Colunas: CustomerID, Name, Age, Gender, Location.

IDs consistentes com interactions.csv.

⚠️ Observação: Pode-se usar datasets públicos, como Amazon Reviews (Electronics), para testes.

⚙️ Ferramentas e Tecnologias

Python

Bibliotecas: pandas, NumPy, scikit-learn, TensorFlow (opcional)

Técnicas: Filtragem Colaborativa, Content-Based, Matrix Factorization, SVD, KNN

🎯 Resultados Esperados

Para cada usuário, gerar lista de produtos recomendados considerando:

Popularidade

Histórico de compras

Usuários similares

Produtos semelhantes

Informações exibidas: Name, Category, Brand, Rating, ImageURL

Possibilidade de atualização dinâmica das recomendações com feedback do usuário.