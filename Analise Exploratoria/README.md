
---

# Análise Exploratória de Dados (AED)

O principal passo de um projeto de Ciência de Dados, antes da aplicação de modelos de Machine Learning, é entender e explorar os dados disponíveis. Abaixo estão as principais funções utilizadas para realizar a Análise Exploratória de Dados (AED), um processo essencial para identificar padrões, detectar anomalias e formular hipóteses.

## 1. Importação de Bibliotecas e Dataset

### Importação de Bibliotecas

```python
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns
```

Essas bibliotecas são amplamente usadas em projetos de Ciência de Dados. O `pandas` é utilizado para manipulação de dados tabulares, o `matplotlib` para visualização básica e o `seaborn` para visualização avançada de gráficos.

### Carregamento de Dataset

```python
base = pd.read_csv('dataset.csv')
```

O método `pd.read_csv()` é utilizado para ler arquivos no formato CSV e carregá-los como `DataFrame`, facilitando o tratamento de dados tabulares.

---

## 2. Visualização Inicial dos Dados

### Visualização das Primeiras Linhas

```python
base.head(n=5)
```

O método `head()` exibe as primeiras `n` linhas do dataset. Isso ajuda a ter uma visão inicial da estrutura dos dados.

### Visualização das Últimas Linhas

```python
base.tail(n=5)
```

A função `tail()` permite visualizar as últimas `n` linhas do dataset.

### Verificação do Tamanho do Dataset

```python
base.shape
```

A função `shape` retorna uma tupla contendo o número de linhas e colunas no dataset.

---

## 3. Informações sobre os Dados

### Resumo das Informações do Dataset

```python
base.info()
```

A função `info()` apresenta informações sobre o número de entradas, tipos de dados e valores nulos presentes em cada coluna. Isso é útil para identificar inconsistências no formato dos dados.

### Contagem de Valores Nulos

```python
base.isnull().sum()
```

Esse comando exibe a contagem de valores nulos por coluna, permitindo identificar onde faltam dados.

### Estatísticas Descritivas

```python
base.describe()
```

O método `describe()` gera estatísticas descritivas (contagem, média, desvio padrão, mínimo, máximo, etc.) para as colunas numéricas.

---

## 4. Análise de Cardinalidade

### Contagem de Valores Únicos

```python
base.nunique()
```

O método `nunique()` retorna o número de valores distintos em cada coluna. Isso é útil para identificar colunas com alta cardinalidade (muitos valores únicos), que podem não ser relevantes para a modelagem.

---

## 5. Visualização Gráfica

### Histograma

```python
x = base['coluna']
fig, ax = plt.subplots()
ax.hist(x, bins=40, linewidth=0.5, edgecolor="white")
plt.show()
```

O histograma é uma visualização da distribuição dos dados em uma coluna. Ele ajuda a identificar padrões como a presença de outliers e a forma da distribuição.

### Boxplot

```python
fig, ax = plt.subplots()
ax.boxplot(base['coluna'])
plt.show()
```

O boxplot exibe a mediana, quartis e valores atípicos (outliers) de uma variável. É útil para detectar anomalias.

---

## 6. Análise de Correlação

### Matriz de Correlação

```python
base.corr()
```

A função `corr()` calcula a correlação entre as variáveis numéricas, indicando o grau de relacionamento linear entre elas.

### Heatmap de Correlação

```python
sns.heatmap(base.corr(), annot=True, cmap='coolwarm')
plt.show()
```

O heatmap visualiza a matriz de correlação de forma gráfica, onde as cores representam a força da correlação entre variáveis. O parâmetro `annot=True` exibe os valores da correlação diretamente no gráfico.

### Pairplot

```python
sns.pairplot(base, hue='coluna_categórica')
```

O `pairplot()` cria gráficos de dispersão para todas as combinações de variáveis numéricas, colorindo os pontos de acordo com uma coluna categórica.

---

## Conclusão

Essas funções são essenciais para realizar uma Análise Exploratória de Dados, fornecendo insights valiosos sobre a estrutura e padrões presentes nos dados. 
## Fontes Utilizadas

- [Pandas Documentation](https://pandas.pydata.org/pandas-docs/stable/)
- [Matplotlib Documentation](https://matplotlib.org/stable/contents.html)
- [Seaborn Documentation](https://seaborn.pydata.org/)

---

