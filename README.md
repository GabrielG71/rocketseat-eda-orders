# Análise Exploratória de Dados (EDA) — Vendas de Loja Online

Este projeto documenta a realização de uma **Análise Exploratória de Dados (EDA)** utilizando **Python + Pandas**, aplicada a um dataset fictício de compras em uma loja online.

O objetivo é demonstrar domínio em:
- Estatística descritiva (média, mediana, moda, variância, desvio padrão)
- Interpretação de distribuição (assimetria e dispersão)
- Detecção de outliers (regra do IQR)
- Comparação de variabilidade (coeficiente de variação)
- Análise segmentada por categorias

---

## Contexto

Cada linha do dataset representa um cliente que realizou uma compra em janeiro.

O dataset contém variáveis quantitativas e qualitativas para permitir análises numéricas e segmentações por perfil.

## Estrutura do Projeto

├── pedidos.csv
├── rocketesat-orders-eda.ipynb
└── README.md

## Dataset

O dataset utilizado (`pedidos.csv`) contém **50 registros** e as seguintes colunas:

### Variáveis

- **Cliente_ID** (qualitativa nominal): identificador do cliente
- **Genero** (qualitativa nominal): M / F
- **Categoria_Produto** (qualitativa nominal): Eletronicos / Roupas / Casa
- **Idade** (quantitativa): idade do cliente
- **Valor_Compra** (quantitativa): valor gasto na compra (R$)
- **Itens_Comprados** (quantitativa): quantidade de itens comprados

---

## Etapas do EDA

### 1) Leitura e inspeção inicial

Foram realizadas as etapas iniciais para validar o dataset:
- `head()` para inspeção das primeiras linhas
- `info()` para verificar tipos e valores ausentes
- `describe()` para estatísticas descritivas iniciais

Principais constatações:
- Dataset com **50 registros**
- **Sem valores nulos**
- Tipos adequados (`int` para numéricas, `str` para categóricas)

---

### 2) Estatística descritiva

Para as variáveis quantitativas (`Idade`, `Valor_Compra`, `Itens_Comprados`) foram calculados:

- **Média**
- **Mediana**
- **Moda**
- **Variância**
- **Desvio padrão**

A análise identificou que:

- **Valor_Compra** possui alta dispersão, com média significativamente afetada por valores altos
- **Idade** é relativamente homogênea, com menor variabilidade relativa
- **Itens_Comprados** apresenta dispersão moderada, com maior concentração em poucos itens

---

### 3) Dispersão e variabilidade (Coeficiente de Variação)

Para comparar variáveis em escalas diferentes, foi utilizado o **Coeficiente de Variação (CV)**:

CV = desvio_padrao / media

Resultado interpretativo:
- A variável com maior volatilidade foi **Valor_Compra**
- Idade apresentou a menor dispersão relativa

---

### 4) Detecção de Outliers (Regra do IQR)

Foi aplicada a regra do **IQR** (Intervalo Interquartil):

- Q1 (25%)
- Q3 (75%)
- IQR = Q3 - Q1
- Limites = Q1 - 1.5*IQR e Q3 + 1.5*IQR

Resultado:
- Apesar de existirem valores altos, o método **não classificou compras como outliers** no dataset analisado.

---

### 5) Visualização de distribuição

Foram gerados histogramas para:
- `Valor_Compra`
- `Idade`
- `Itens_Comprados`

Objetivo:
- Identificar assimetria (ex: cauda à direita)
- Ver concentração de valores e dispersão

---

### 6) Análise segmentada

Foi realizada análise por agrupamento para observar diferenças entre categorias, como:
- média por `Categoria_Produto`
- mediana por `Categoria_Produto`
- desvio padrão por `Categoria_Produto`

---

## Principais Insights

- **Valor_Compra** é a variável mais volátil e heterogênea do dataset, indicando comportamento de compra desigual entre clientes.
- **Idade** apresenta menor variação relativa, sugerindo um público mais concentrado em uma faixa etária próxima.
- **Itens_Comprados** sugere padrão comum de compra com poucos itens, mas com variação suficiente para ações de aumento de carrinho médio.
- Mesmo com valores altos, o método IQR não apontou outliers formais para `Valor_Compra`.

---

## Como executar

### 1) Criar e ativar ambiente virtual

python3 -m venv .venv
source .venv/bin/activate

### 2) Instalar dependências

pip install pandas matplotlib

### 3) Rodar o notebook

jupyter notebook rocketesat-orders-eda.ipynb

---

## Tecnologias

- Python 3
- Pandas
- Matplotlib
- Jupyter Notebook

---

## Autor

Projeto desenvolvido como parte do aprendizado em análise de dados por Gabriel Gonçalves
