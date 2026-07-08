# Metodologia CRISP-DM

Este projeto foi conduzido seguindo o **CRISP-DM** (Cross Industry Standard Process for Data Mining), o padrão de mercado mais utilizado em projetos de dados. O processo é dividido em 6 fases, não necessariamente lineares — é comum voltar a uma fase anterior conforme novas descobertas surgem.

```
1. Business Understanding  →  2. Data Understanding  →  3. Data Preparation
        ↑                                                        ↓
6. Deployment  ←  5. Evaluation  ←──────────────  4. Modeling
```

---

## 1. Business Understanding (Entendimento do Negócio)

**Objetivo:** traduzir uma dúvida de negócio em um problema de dados que pode ser respondido com análise.

**Pergunta central do projeto:**
> O que realmente faz um livro vender mais — a nota que recebe, o preço, a fama do autor ou o gênero?

**Perguntas de apoio:**
- A nota média se traduz em mais vendas?
- A reputação do autor faz diferença nas vendas?
- Existe um gênero que se destaca em engajamento e aceitação?
- Preço baixo garante mais vendas?
- Quais editoras e autores concentram a maior receita?
- O ano de publicação influencia o volume histórico de vendas?

**Critério de sucesso:** transformar os dados brutos em recomendações acionáveis para decisões editoriais e de marketing.

---

## 2. Data Understanding (Entendimento dos Dados)

**Objetivo:** conhecer a estrutura, qualidade e distribuição da base antes de qualquer tratamento.

**Atividades realizadas:**
- Carregamento da base (`pd.read_csv`) e inspeção inicial (`df.head()`)
- Verificação de estrutura e tipos de dados (`df.info()`)
- Identificação de valores nulos (`df.isna().sum()`)
- Estatísticas descritivas (`df.describe()`)

**Principal achado desta fase:** identificação de um valor de `Publishing Year` inconsistente (**-560**), que seria tratado na fase seguinte. Também foram identificados nulos em `Book Name` (23 registros) e `language_code` (53 registros).

📎 Detalhes completos em [`Dicionario_de_Dados.md`](Dicionario_de_Dados.md).

---

## 3. Data Preparation (Preparação dos Dados)

**Objetivo:** deixar a base consistente e confiável para a análise.

**Tratamentos aplicados:**

| Ação | Código | Resultado |
|---|---|---|
| Remover anos inválidos | `df = df[df["Publishing Year"] >= 1900]` | Elimina o outlier -560 e registros anteriores a 1900 |
| Remover nomes ausentes | `df = df[~df["Book Name"].isna()]` | Remove 23 linhas sem título |
| Checar duplicatas | `df.duplicated().sum()` | 0 duplicatas encontradas |
| Mapear cardinalidade | `df.nunique()` | 669 autores, 9 editoras, 4 gêneros, 8 idiomas |
| Consolidar gênero | `df['genre'] = df['genre'].apply(...)` | Unifica `"genre fiction"` em `"Ficção"` |

> ⚠️ **Nota técnica:** a consolidação de gênero ficou parcialmente incompleta — a categoria `"fiction"` (54 registros) não foi unificada com `"Ficção"`. Recomenda-se revisar essa regra em uma futura iteração.

---

## 4. Modeling (Modelagem / Análise Exploratória)

**Objetivo:** cruzar variáveis para responder às perguntas de negócio, usando estatística descritiva e inferencial.

Não foi construído um modelo preditivo (ex.: regressão) nesta iteração — o foco foi em análise exploratória e testes de hipótese. As principais técnicas aplicadas:

- **Visualização de distribuições:** histogramas, gráficos de barras e pizza
- **Comparação entre grupos:** boxplots (gênero, reputação do autor)
- **Relação entre variáveis contínuas:** gráficos de dispersão e matriz de correlação
- **Teste de hipótese:** teste t de Student para comparar médias entre grupos independentes

📎 Detalhes estatísticos completos em [`Estatistica_Aplicada.md`](Estatistica_Aplicada.md).

---

## 5. Evaluation (Avaliação)

**Objetivo:** confrontar os resultados obtidos com as perguntas de negócio da Fase 1, e avaliar a robustez e as limitações do estudo.

**Limitações identificadas:**
- Desequilíbrio amostral entre grupos de reputação do autor (Intermediate: 576 livros vs. Novice: 28 livros)
- Base enviesada para idioma inglês e gênero ficção
- Análise correlacional/descritiva, sem modelo preditivo formal
- Necessidade de validação contínua da qualidade dos dados de origem

---

## 6. Deployment (Implantação)

**Objetivo:** transformar os achados em recomendações práticas e definir próximos passos.

📎 Recomendações completas em [`Insights_de_Negocio.md`](Insights_de_Negocio.md).

**Próximos passos sugeridos:**
- Construir modelo preditivo combinando múltiplas variáveis
- Corrigir a unificação da categoria de gênero
- Buscar dados complementares para equilibrar a amostra por reputação do autor
- Investigar os "fenômenos de sucesso" (outliers) identificados nos boxplots
