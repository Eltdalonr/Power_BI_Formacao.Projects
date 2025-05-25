# 📘 Modelagem Dimensional

## 🎯 Objetivo

Criar modelos dimensionais (**esquema em estrela**) focados na análise de dados, a partir de duas bases distintas:

- **Professores** – baseado em um modelo relacional fornecido.
- **Financial Sample** – fornecido em um único conjunto de dados.

---

## 🧩 O que foi feito

### 📚 Projeto 1 – Professores

- ✅ Definição da **tabela fato** com foco na atuação dos professores:  
  Cursos, disciplinas, departamentos e datas.
- ✅ Criação das **tabelas dimensão**:  
  `D_Professor`, `D_Curso`, `D_Disciplina`, `D_Departamento`, `D_Calendário (fictícia)`.
- ✅ Granularidade definida por **oferta de disciplina**.
- ⚠️ **Observação**: o modelo **não inclui dados sobre alunos**.

---

### 💼 Projeto 2 – Financial Sample

- ✅ Criação da tabela de **backup**: `Financials_origem`.
- ✅ Criação das **tabelas dimensão**:
  - `D_Produtos`
  - `D_Produtos_Detalhes`
  - `D_Descontos`
  - `D_Detalhes`
  - `D_Calendário` (criada com `calendar()` via DAX)
- ✅ Criação da **tabela fato**: `F_Vendas`.
- ✅ Utilização de **funções DAX** para:
  - Cálculo de **médias**, **medianas**, **máximos** e **mínimos**
  - Criação de colunas **condicionais** (ex: índice de produtos)
  - Geração de coluna `Date` para `D_Calendário`

---
