# Estatística Aplicada

Este documento detalha as técnicas estatísticas utilizadas no projeto, os resultados numéricos obtidos e como interpretá-los.

---

## 1. Estatística Descritiva

Usada na fase de Data Understanding para resumir a distribuição de cada variável numérica (`df.describe()`): média, desvio, mínimo, máximo e quartis. Foi essa análise que revelou o outlier de `Publishing Year = -560`, corrigido na preparação dos dados.

---

## 2. Análise de Correlação (Coeficiente de Pearson)

**O que mede:** a força e a direção da relação **linear** entre duas variáveis numéricas. Varia de -1 (relação inversa perfeita) a +1 (relação direta perfeita); valores próximos de 0 indicam ausência de relação linear.

**Matriz de correlação calculada:**

| | Nota média | Qtd. avaliações | Vendas brutas | Preço |
|---|---|---|---|---|
| **Nota média** | 1,00 | 0,12 | -0,04 | -0,02 |
| **Qtd. avaliações** | 0,12 | 1,00 | **0,49** | -0,07 |
| **Vendas brutas** | -0,04 | **0,49** | 1,00 | 0,27 |
| **Preço** | -0,02 | -0,07 | 0,27 | 1,00 |

**Como interpretar a força da correlação:**

| Faixa (valor absoluto) | Interpretação |
|---|---|
| 0,00 – 0,19 | Muito fraca / desprezível |
| 0,20 – 0,39 | Fraca |
| 0,40 – 0,59 | Moderada |
| 0,60 – 0,79 | Forte |
| 0,80 – 1,00 | Muito forte |

**Leitura dos resultados:**
- **Qtd. de avaliações × Vendas brutas (0,49):** a correlação mais relevante da base — moderada e positiva. É a evidência estatística central por trás do insight "engajamento importa mais que nota".
- **Nota média × Vendas brutas (-0,04):** praticamente nula — não há relação linear relevante entre a nota de um livro e o quanto ele vende.
- **Preço × Vendas brutas (0,27):** fraca a moderada e positiva — não indica que preço mais alto causa mais vendas; é mais provável que reflita que livros de sucesso comercial tendem a ter preços um pouco mais altos, mas dentro de um teto (ver Gráfico 5 no relatório completo).

> ⚠️ **Importante:** correlação não implica causalidade. Uma correlação moderada indica associação estatística, não que uma variável *causa* o comportamento da outra.

---

## 3. Teste de Hipótese — Teste t de Student (amostras independentes)

**Pergunta:** autores com reputação "Famous" vendem mais unidades do que autores "Intermediate"?

**Hipóteses estatísticas:**
- **H₀ (hipótese nula):** não há diferença real entre a média de vendas dos dois grupos.
- **H₁ (hipótese alternativa):** existe diferença real entre a média de vendas dos dois grupos.

**Código utilizado:**
```python
import scipy.stats as stats

grupo_A = df[df['Author_Rating'] == 'Famous']['units sold']
grupo_B = df[df['Author_Rating'] == 'Intermediate']['units sold']

t_stats, p_val = stats.ttest_ind(grupo_A, grupo_B, equal_var=False)
```
*(usa a variante de Welch — `equal_var=False` — recomendada quando os grupos têm tamanhos e variâncias diferentes, como é o caso aqui: 48 vs. 576 registros)*

**Resultado:**

| Estatística | Valor |
|---|---|
| Estatística t | -0,6595 |
| Valor-p | 0,5121 |

**Como interpretar o valor-p:**

| Valor-p | Interpretação |
|---|---|
| p < 0,05 | Diferença estatisticamente significativa — rejeita-se H₀ |
| p ≥ 0,05 | Sem evidência suficiente de diferença — não se rejeita H₀ |

Como **p = 0,5121 > 0,05**, **não rejeitamos H₀**: não há evidência estatística de que autores "Famous" vendam mais do que "Intermediate". A diferença observada nas médias amostrais é compatível com variação ao acaso.

> ⚠️ **Limitação:** o grupo "Famous" tem apenas 48 observações contra 576 de "Intermediate". Amostras pequenas reduzem o poder estatístico do teste — ou seja, mesmo que existisse uma diferença real pequena, o teste teria dificuldade em detectá-la. Isso não invalida o resultado, mas é um ponto de atenção para quem for tomar decisões com base nele.

---

## 4. Análise Visual (Boxplots)

Usados para comparar a distribuição de uma variável numérica entre categorias (gênero, reputação do autor), permitindo visualizar:

- **Mediana** (linha central da caixa)
- **Amplitude interquartil** (altura da caixa — onde estão os 50% centrais dos dados)
- **Outliers** (pontos fora dos "bigodes") — nesta análise, usados para identificar "fenômenos de sucesso" (livros com vendas ou avaliações muito acima do padrão do seu grupo)

---

## 5. Resumo das técnicas por pergunta de negócio

| Pergunta | Técnica estatística usada |
|---|---|
| Nota influencia vendas? | Correlação de Pearson + dispersão |
| Reputação do autor influencia vendas? | Teste t de Student (Welch) + boxplot |
| Gênero influencia engajamento/nota? | Boxplot comparativo por grupo |
| Preço influencia vendas? | Dispersão + correlação de Pearson |
| Editoras/autores líderes? | Agregação (`groupby` + `sum`) e ranking |
