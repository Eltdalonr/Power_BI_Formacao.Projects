# 📊 Integrando Dados com MySQL e Transformando com Power BI

## 🚀 Desafio de Projeto

Integração do Power BI com MySQL e aplicação de transformações para preparar os dados para análise.

---

## 🔧 Etapas do Projeto

### 1. Criação do Banco
- Banco construído a partir de base disponível no [GitHub](#).

### 2. Integração com Power BI
- Conexão direta entre Power BI e MySQL.

### 3. Transformações no Power BI

#### ✔️ Verificações Iniciais
- Cabeçalhos e tipos de dados corrigidos.
- Valores monetários convertidos para `double`.

#### ❗ Dados Nulos
- Análise e remoção de valores nulos conforme contexto.
- `Super_ssn` nulo: indica gerente — validado.
- Departamentos sem gerente foram identificados e corrigidos (valores fictícios atribuídos).

#### 🔍 Verificações Técnicas
- Horas por projeto revisadas.
- Colunas complexas separadas conforme necessidade.

#### 🔗 Mesclas e Junções
- **Employee + Department**: junção baseada na tabela `employee` para associar nome dos departamentos.
- Colunas desnecessárias removidas.
- **Colaboradores + Nome do gerente**:


- Colunas de nome e sobrenome unificadas.
- Nome do departamento + local concatenados para criar chave única de dimensão.

#### 🧠 Observação Importante
> Utilizamos **mesclar** (e não **atribuir**) pois não há transformação de linha/valor, apenas expansão de dados relacionados — mantendo a granularidade original.

#### 📊 Agrupamentos
- Agrupado por gerente para contar colaboradores.

#### 🧹 Limpeza Final
- Remoção de colunas não utilizadas para otimização do modelo.