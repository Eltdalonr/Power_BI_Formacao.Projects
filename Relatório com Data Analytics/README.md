# 📊 Relatório Análise de Vendas Internacionais

## 🧾 Descrição Geral

Este relatório foi desenvolvido com o objetivo de fornecer **insights estratégicos** sobre o desempenho de vendas de produtos em diferentes países. O foco é destacar produtos com maior impacto, identificar os países mais lucrativos e analisar padrões de vendas ao longo do tempo. O dashboard foi desenhado pensando na experiência do usuário final, priorizando a clareza visual e a navegação fluida.

---

## 🗂 Estrutura do Relatório

O relatório está dividido em **duas páginas**, com disposição pensada para consumo direto por gestores e stakeholders:

### 📄 Página 1 – Principal

#### ✅ KPIs Principais  
- Total de Vendas  
- Total de Lucro  
- Total de Unidades Vendidas  
- Número de Países Atendidos  
- Quantidade de Produtos Vendidos  

#### 🥇 Top 3 Produtos  
- **Gráfico de Barras Horizontais** mostrando os três produtos com maior volume de vendas e lucro.

#### 🌍 Principais Países  
- **Mapa interativo** com destaque por volume de vendas.  
- **Tabela classificada** com os países que mais contribuíram para o lucro.

#### 📈 Dispersão Temporal  
- **Gráfico de Dispersão** mostrando a relação entre unidades vendidas e total de vendas por mês.  
- Análise de sazonalidade e variações mensais.

---

### 📄 Página 2 – Detalhes

#### 🗓 Vendas por Semestre  
- **Gráfico de colunas empilhadas** comparando os dois semestres dos anos de 2013 e 2014.  
- Foco na sazonalidade e evolução semestral.

#### 📋 Tabela Trimestral  
- **Tabela detalhada por trimestre e ano**, com totais por linha e colunas.  
- Permite análise precisa da evolução trimestral de vendas.

#### 📊 Histograma – Unidades Vendidas  
- **Gráfico de histogramas** agrupando as unidades vendidas em buckets (faixas de volume).  
- Mostra a concentração de vendas por faixa de quantidade.

#### 🔢 Produtos Vendidos  
- **Gráfico de barras horizontais** com os produtos mais vendidos por unidades.  
- Destaque para os produtos com maior penetração no mercado (ex: VTT, Veículo, Carreta).

---

## 🧮 Medidas Criadas (DAX)

```DAX
Total Vendas = SUM(Fatos[Vendas])
Total Lucro = SUM(Fatos[Lucro])
Total Unidades = SUM(Fatos[UnidadesVendidas])

Top 3 Produtos = 
TOPN(3, 
    SUMMARIZE(Fatos, Produtos[Nome], "TotalVendas", SUM(Fatos[Vendas])), 
    [TotalVendas], 
    DESC
)

Lucro por País = 
SUMX(
    VALUES(Países[Nome]),
    CALCULATE(SUM(Fatos[Lucro]))
)

Vendas Mensais = 
CALCULATE(
    [Total Vendas],
    DATESMTD(Calendario[Data])
)
```

---