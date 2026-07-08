# Dicionário de Dados

Base analisada: `Books_Data_Clean.csv`
**1.070 registros** (após limpeza) &nbsp;|&nbsp; **15 variáveis**

---

## Visão geral das colunas

| Coluna | Tipo | Descrição | Exemplo |
|---|---|---|---|
| `Publishing Year` | Numérico (int) | Ano de publicação do livro | `2011` |
| `Book Name` | Texto | Título do livro | `The Hunger Games` |
| `Author` | Texto | Nome do autor | `Suzanne Collins` |
| `language_code` | Categórico | Código do idioma da edição | `eng`, `en-US`, `en-GB`, `fre`, `spa` |
| `Author_Rating` | Categórico | Classificação de reputação do autor | `Novice`, `Intermediate`, `Excellent`, `Famous` |
| `Book_average_rating` | Numérico (float) | Nota média do livro (escala de 0 a 5) | `4,33` |
| `Book_ratings_count` | Numérico (int) | Quantidade total de avaliações recebidas | `2.938.325` |
| `genre` | Categórico | Gênero literário do livro | `Ficção`, `nonfiction`, `fiction`, `children` |
| `gross sales` | Numérico (float) | Receita bruta gerada pelo livro (US$) | `1.856,60` |
| `publisher revenue` | Numérico (float) | Receita líquida repassada à editora (US$) | `1.299,62` |
| `sale price` | Numérico (float) | Preço de venda unitário (US$) | `6,50` |
| `sales rank` | Numérico (int) | Posição do livro no ranking de vendas | `1` |
| `Publisher` | Categórico | Nome da editora | `Penguin Group (USA) LLC` |
| `units sold` | Numérico (int) | Quantidade de unidades vendidas | `61.560` |
| *(coluna auxiliar de índice)* | Numérico (int) | Identificador sequencial da linha, gerado automaticamente na exportação do CSV | `0, 1, 2...` |

---

## Categorias das variáveis categóricas

### `genre` (gênero)
| Categoria | Qtde. de registros | Observação |
|---|---|---|
| Ficção (`genre fiction`) | 759 | Categoria consolidada na preparação dos dados |
| `nonfiction` | 160 | — |
| `fiction` | 54 | ⚠️ Não unificada com "Ficção" (ver nota na Metodologia) |
| `children` | 15 | — |

### `Author_Rating` (reputação do autor)
| Categoria | Qtde. de livros |
|---|---|
| `Intermediate` | 576 |
| `Excellent` | 336 |
| `Famous` | 48 |
| `Novice` | 28 |

### `language_code` (idioma)
Predominância de `eng` e `en-US` (juntos, mais de 80% da base). Demais códigos (`en-GB`, `en-CA`, `spa`, `fre`, `ara`, entre outros) somam participação residual.

---

## Estatísticas descritivas das principais variáveis numéricas

| Variável | Média | Mínimo | Máximo |
|---|---|---|---|
| Publishing Year | 1971,4 | 1900* | 2016 |
| Book_average_rating | 4,01 | 2,97 | 4,77 |
| Book_ratings_count | 94.910 | 27.308 | 206.792 |
| gross sales | 1.856,6 | 104,9 | 47.795 |
| sale price | 4,87 | 0,99 | 33,86 |
| units sold | 9.677 | 106 | 61.560 |

\* *Antes da limpeza, o valor mínimo original era **-560**, um dado inconsistente removido na fase de Preparação dos Dados.*

---

## Qualidade dos dados (antes da limpeza)

| Coluna | Valores nulos | Tratamento aplicado |
|---|---|---|
| `Publishing Year` | 1 | Removido junto ao filtro de anos < 1900 |
| `Book Name` | 23 | Linhas removidas |
| `language_code` | 53 | Mantido (não crítico para as análises realizadas) |
| Demais colunas | 0 | — |

**Duplicatas encontradas:** 0

**Cardinalidade (valores únicos por coluna):**
- 669 autores únicos
- 9 editoras
- 4 gêneros
- 8 códigos de idioma únicos
