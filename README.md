# Analise_vendas_livros

> Um projeto completo de Ciência de Dados aplicando a metodologia **CRISP-DM**, Python e Estatística para identificar os fatores que influenciam o sucesso comercial de livros.

---

# 📖 Sobre o Projeto

O mercado editorial produz milhares de títulos todos os anos, mas poucos se tornam verdadeiros best-sellers.

Este projeto busca responder uma pergunta simples, porém estratégica:

> **O que realmente faz um livro vender mais?**

Para responder essa questão foi realizada uma análise completa utilizando técnicas de Ciência de Dados, passando por todas as etapas da metodologia **CRISP-DM**, desde o entendimento do negócio até a geração de recomendações para tomada de decisão.

---

# 🎯 Objetivos

Responder às seguintes perguntas de negócio:

- A nota média influencia as vendas?
- Livros mais baratos vendem mais?
- A reputação do autor impacta nas vendas?
- Quais editoras concentram a maior receita?
- Existe relação entre quantidade de avaliações e vendas?
- O gênero literário influencia o desempenho comercial?

---

# 📊 Base de Dados

**Dataset:** Books_Data_Clean.csv

Características da base:

- 📚 1.070 livros
- ✍️ 669 autores
- 🏢 9 editoras
- 🌎 8 idiomas
- 📖 4 gêneros
- 📈 15 variáveis

Principais variáveis analisadas:

- Book Name
- Author
- Publisher
- Publishing Year
- Book Average Rating
- Book Ratings Count
- Sale Price
- Gross Sales
- Units Sold
- Publisher Revenue
- Genre
- Language

---

# 🛠️ Tecnologias Utilizadas

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- SciPy
- Jupyter Notebook
- GitHub

---

# 📚 Metodologia

Este projeto foi desenvolvido seguindo a metodologia **CRISP-DM (Cross Industry Standard Process for Data Mining)**.

## Fluxo do Projeto

```text
Business Understanding
        ↓
Data Understanding
        ↓
Data Preparation
        ↓
Exploratory Data Analysis
        ↓
Statistical Analysis
        ↓
Business Insights
        ↓
Final Report
```

---

# 📂 Estrutura do Projeto

```text
book-sales-analysis-crisp-dm

│
├── data/
│
├── notebooks/
│
├── images/
│
├── reports/
│
├── docs/
│
└── README.md
```

---

# 📈 Principais Análises

Durante o projeto foram realizadas análises como:

- Estatísticas Descritivas
- Limpeza de Dados
- Tratamento de Valores Nulos
- Remoção de Outliers
- Distribuições
- Histogramas
- Scatter Plot
- Boxplots
- Correlação de Pearson
- Teste t de Student
- Geração de Insights

---

# 📊 Principais Resultados

## 📌 Nota média não explica vendas

Não foi encontrada correlação significativa entre a nota média dos livros e o volume de vendas.

---

## 📌 Quantidade de avaliações é um forte indicador

Foi encontrada uma correlação moderada entre quantidade de avaliações e vendas.

**Correlação: 0,49**

Quanto maior o engajamento dos leitores, maior tende a ser o desempenho comercial.

---

## 📌 Autor famoso não vende necessariamente mais

O teste estatístico mostrou que não existe diferença significativa entre autores famosos e intermediários.

**Teste t**

Valor-p = 0,5121

---

## 📌 Livros caros dificilmente se tornam best-sellers

Livros acima de US$15 apresentam baixo volume de vendas quando comparados aos títulos de menor preço.

---

## 📌 Ficção domina o mercado

O gênero Ficção representa a maior parte dos títulos analisados e concentra o maior volume de avaliações.

---

# 💡 Recomendações de Negócio

Com base nas análises, recomenda-se:

- Incentivar campanhas de avaliações dos leitores.
- Priorizar estratégias de engajamento.
- Não utilizar apenas a nota média para decisões editoriais.
- Definir estratégias de precificação competitivas.
- Investir em títulos de Ficção com alto potencial de alcance.

---

# 📚 Competências Demonstradas

Este projeto demonstra conhecimentos em:

- Business Understanding
- Data Understanding
- Data Cleaning
- Data Preparation
- Exploratory Data Analysis (EDA)
- Data Visualization
- Estatística Descritiva
- Correlação
- Teste de Hipóteses
- Storytelling com Dados
- Geração de Insights para Negócios

---

# 📸 Principais Visualizações

O projeto contém diversos gráficos, incluindo:

- Histograma
- Scatter Plot
- Boxplots
- Distribuição por Gênero
- Receita por Editora
- Correlação entre Variáveis
- Evolução das Vendas

*(As imagens estão disponíveis na pasta `/images`.)*

---

# 📄 Documentação

A documentação completa está disponível na pasta **docs/**, incluindo:

- Metodologia CRISP-DM
- Dicionário de Dados
- Estatística Aplicada
- Insights de Negócio

---

# 📑 Relatório Técnico

O relatório completo do projeto encontra-se na pasta **reports/**.

---

# 🎯 Conclusão

Os resultados mostram que o sucesso comercial de um livro está muito mais relacionado ao engajamento do público do que à sua avaliação média.

Embora preço e reputação do autor exerçam alguma influência, a quantidade de avaliações demonstrou ser o principal indicador associado ao desempenho comercial dos títulos analisados.

Esses resultados podem apoiar editoras na definição de estratégias de marketing, precificação e lançamento de novos livros.

---

# 👩‍💻 Autora

**Viviane Andrade**

Analista de Dados | Business Intelligence | Python | Power BI | SQL | Estatística Aplicada

---

⭐ Se este projeto foi útil para você, considere deixar uma estrela no repositório.
