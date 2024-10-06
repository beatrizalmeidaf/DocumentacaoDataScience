---

# Análise Exploratória de Dados (AED)

A análise exploratória de dados é uma das etapas mais importantes em um projeto de Ciência de Dados, pois permite compreender melhor as características do seu conjunto de dados antes de aplicar técnicas mais avançadas de aprendizado de máquina. Aqui estão as principais funções e etapas usadas em uma AED.

## 1. Importação de Bibliotecas e Dataset

### Importação do Pandas
```python
import pandas as pd
```
O `pandas` é uma biblioteca essencial para manipulação e análise de dados em Python. Ele fornece estruturas de dados como `DataFrame` e `Series`, que facilitam o trabalho com dados tabulares.

### Leitura de Arquivo CSV
```python
base = pd.read_csv('dataset.csv')
```
A função `pd.read_csv()` permite carregar um dataset em formato CSV em um `DataFrame` do Pandas, que será utilizado para as análises subsequentes.

## 2. Visualização Inicial dos Dados

### Visualização das Primeiras Linhas
```python
base.head(n)
```
O método `head()` mostra as primeiras `n` linhas do dataset. Isso é útil para obter uma visão geral da estrutura e conteúdo dos dados.

### Visualização das Últimas Linhas
```python
base.tail(n)
```
Semelhante ao `head()`, o método `tail()` exibe as últimas `n` linhas do dataset, permitindo verificar a parte final dos dados.

### Verificação do Tamanho do Dataset
```python
base.shape
```
A função `shape` retorna uma tupla com o número de linhas e colunas do `DataFrame`. Isso ajuda a entender a dimensão do conjunto de dados.

## 3. Informações sobre os Dados

### Resumo das Informações do Dataset
```python
base.info()
```
A função `info()` fornece um resumo com o número de entradas, tipos de dados de cada coluna, e a quantidade de valores nulos. Isso é essencial para identificar problemas como dados ausentes ou tipos incorretos.

### Contagem de Valores Nulos
```python
base.isnull().sum()
```
Esse comando exibe a contagem de valores nulos em cada coluna, permitindo identificar facilmente onde os dados estão faltando.

### Estatísticas Descritivas
```python
base.describe()
```
A função `describe()` gera um resumo estatístico das colunas numéricas, incluindo contagem, média, desvio padrão, valores mínimo e máximo, e os percentis. Isso fornece uma visão inicial das distribuições e variabilidade dos dados.

## 4. Análise de Cardinalidade

### Contagem de Valores Únicos
```python
base.nunique()
```
O método `nunique()` retorna o número de valores distintos em cada coluna. Isso ajuda a identificar colunas com alta cardinalidade, que podem não ser úteis para modelagem.

## 5. Visualização Gráfica

### Histograma
```python
import matplotlib.pyplot as plt

x = base['coluna']

fig, ax = plt.subplots()
ax.hist(x, bins=40, linewidth=0.5, edgecolor="white")
plt.show()
```
O histograma exibe a distribuição dos dados em uma coluna. É útil para identificar a dispersão, outliers, e a forma da distribuição (normal, enviesada, etc.).

### Boxplot
```python
fig, ax = plt.subplots()
ax.boxplot(base['coluna'])
plt.show()
```
O boxplot visualiza a distribuição, a mediana e os outliers de uma variável. É eficaz para comparar diferentes distribuições e identificar dados atípicos.

## 6. Análise de Correlação

### Matriz de Correlação
```python
base.corr()
```
A função `corr()` calcula a correlação entre as variáveis numéricas. Isso é crucial para entender relações lineares entre variáveis e identificar possíveis colinearidades.

### Heatmap de Correlação
```python
import seaborn as sns

sns.heatmap(base.corr())
plt.show()
```
Um heatmap é uma forma visual de representar a matriz de correlação, onde as cores indicam a força da correlação entre as variáveis. Isso facilita a interpretação rápida das relações entre as variáveis.

### Pairplot
```python
sns.pairplot(base, hue='coluna_categórica')
```
O `pairplot()` do Seaborn cria gráficos de dispersão para pares de variáveis, categorizando-os com base em uma coluna categórica. Isso permite identificar padrões e relações entre diferentes variáveis.

---

## Conclusão

Estas são as principais funções utilizadas na análise exploratória de dados com Python. Elas fornecem uma base sólida para entender a estrutura, qualidade e principais características do seu dataset antes de avançar para a modelagem de dados e outras etapas mais avançadas.

