# Insights de Negócio

Síntese dos achados da análise traduzidos em leitura de negócio, com o nível de confiança de cada um e recomendações práticas associadas.

---

## 1. Popularidade vende mais do que qualidade percebida

**Achado:** a quantidade de avaliações recebidas por um livro tem correlação moderada e positiva (0,49) com suas vendas brutas — a relação mais forte encontrada em toda a análise.

**Confiança:** ✅ Alta — maior correlação da base, com volume amostral robusto (1.070 livros).

**Recomendação:** priorizar ações que aumentem o volume de avaliações e o engajamento do público (campanhas de review, parcerias com influenciadores, incentivos pós-compra) tende a gerar mais retorno comercial do que investir apenas em melhorar a percepção de qualidade.

---

## 2. Nota alta não é garantia de mais vendas

**Achado:** a correlação entre nota média e vendas brutas é praticamente nula (-0,04). Livros com nota 4,5 vendem tão pouco (ou tanto) quanto livros com nota 3,5.

**Confiança:** ✅ Alta — corroborado tanto pela correlação quanto pela inspeção visual da dispersão (inclusive isolando a faixa de vendas mais comum, abaixo de 10 mil unidades).

**Recomendação:** não usar a nota média isoladamente como critério de decisão editorial ou de investimento em marketing. Nota é indicador de satisfação do leitor, não de potencial comercial.

---

## 3. Preço baixo é necessário, mas não suficiente

**Achado:** nenhum livro com preço acima de US$15 atingiu o patamar de best-seller (>30 mil unidades vendidas) na base analisada. Ao mesmo tempo, a maioria dos livros com preço baixo (US$1–5) também vende pouco — preço baixo não garante sucesso, mas parece ser uma condição de entrada para o sucesso em grande escala.

**Confiança:** ⚠️ Média — padrão visualmente claro (ver gráfico de dispersão preço x vendas), mas correlação linear é apenas fraca a moderada (0,27), pois a relação não é proporcional/contínua.

**Recomendação:** manter preços competitivos (idealmente abaixo de US$15) para títulos com ambição de best-seller, mas sem esperar que o preço baixo, isoladamente, garanta alto volume de vendas — outros fatores (como engajamento) continuam sendo decisivos.

---

## 4. Reputação do autor não garante mais vendas

**Achado:** teste estatístico (teste t de Student) não encontrou diferença significativa nas vendas entre autores "Famous" e "Intermediate" (p = 0,51).

**Confiança:** ⚠️ Média — resultado estatisticamente válido, mas o grupo "Famous" tem amostra pequena (48 livros), o que limita a capacidade de detectar diferenças sutis.

**Recomendação:** não tratar a fama do autor como fator decisivo isolado ao prever o sucesso de um título. Autores menos conhecidos podem performar tão bem quanto autores renomados — vale investir em divulgação independentemente da reputação prévia do autor.

---

## 5. Ficção domina em volume, mas gera reações mais polarizadas

**Achado:** Ficção concentra a maior parte dos títulos (759 de 988) e do volume de avaliações, mas também apresenta a maior amplitude de notas — tanto os livros mais bem avaliados quanto os mais malvistos da base pertencem a esse gênero. Livros infantis (`children`), por outro lado, têm recepção mais consistente e uniforme.

**Confiança:** ✅ Alta — padrão visualmente claro nos boxplots de nota e volume de avaliações por gênero.

**Recomendação:** ao investir em Ficção, esperar (e monitorar) uma variabilidade maior na recepção do público. Gêneros como infantil, embora menores em volume, representam menor risco de reação negativa forte.

---

## 6. Concentração de receita em poucas editoras e autores

**Achado:** a Penguin Group (USA) LLC lidera a receita total entre editoras, seguida por Random House LLC e Amazon Digital Services — esta última reforçando o peso crescente da distribuição digital direta. Entre autores, Harper Lee, Stephen King e David Sedaris lideram em vendas brutas acumuladas.

**Confiança:** ✅ Alta — dado agregado direto, sem necessidade de teste estatístico.

**Recomendação:** observar de perto o desempenho de canais de distribuição digital nas estratégias de receita, dado seu peso já relevante mesmo comparado a editoras tradicionais consolidadas.

---

## Resumo — nível de confiança dos insights

| Insight | Confiança | Base estatística |
|---|---|---|
| Engajamento (avaliações) prediz vendas | ✅ Alta | Correlação 0,49 |
| Nota não prediz vendas | ✅ Alta | Correlação -0,04 |
| Preço baixo é condição, não garantia | ⚠️ Média | Correlação 0,27 + padrão visual |
| Fama do autor não garante vendas | ⚠️ Média | Teste t, p = 0,51 (amostra pequena) |
| Ficção é volumosa e polarizada | ✅ Alta | Boxplots comparativos |
| Concentração de receita em poucas editoras | ✅ Alta | Agregação direta |

---

## Recomendações consolidadas para o negócio

1. 📣 Investir em campanhas que gerem reviews e engajamento — é o fator com maior relação estatística com vendas.
2. ⭐ Não usar nota média isoladamente como critério de decisão editorial.
3. 💲 Manter preços abaixo de US$15 para títulos com potencial de best-seller.
4. 📚 Priorizar Ficção para maximizar alcance, mas monitorar a recepção — é o gênero mais sujeito a polarização.
5. 👤 Não depender exclusivamente da fama do autor para prever sucesso comercial.
6. 🖥️ Acompanhar de perto o crescimento de canais de distribuição digital.
