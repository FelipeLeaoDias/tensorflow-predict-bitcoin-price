# Bitcoin Price Prediction using TensorFlow

## Alunos:
- Felipe Leão
- Rafael Santos
- Danilo Scheltes
- Henrique Lyrio

## Objetivo
Este projeto tem como objetivo criar uma IA usando TensorFlow para prever o preço do Bitcoin em USD. O dataset foi dividido em duas partes:

- **dataset.csv**: Utilizado para o treinamento e teste inicial, com o salvamento dos pesos da rede neural.
- **datasetteste.csv**: Contém menos dados e é usado para fazer predições e testes usando os pesos salvos.

## Passos do Projeto

### 1. Download dos Datasets
Baixamos os arquivos de dataset do Google Drive utilizando a biblioteca `gdown`.

### 2. Carregar e Pré-processar os Dados
Carregamos o dataset utilizando `pandas`, selecionamos as colunas de interesse como features e label, e realizamos a divisão dos dados entre treino e teste. Em seguida, normalizamos os dados utilizando `StandardScaler` e os convertimos em tensores do TensorFlow.

### 3. Definir a Arquitetura do Modelo
Definimos a arquitetura da rede neural utilizando o TensorFlow e Keras. A rede contém múltiplas camadas densas, com funções de ativação `ReLU` e dropout para prevenir overfitting. A última camada é configurada para realizar a previsão do preço de fechamento (regressão).

### 4. Compilar e Treinar o Modelo
Compilamos o modelo utilizando o otimizador `Adam` e a função de perda `mean_squared_error` (MSE). O treinamento foi realizado por 100 épocas, com uma validação de 20% do conjunto de dados de treino. Após o treinamento, os pesos do modelo foram salvos para serem usados em futuras predições.

### 5. Avaliar e Visualizar os Resultados
Após o treinamento, realizamos previsões utilizando o conjunto de teste. As métricas `MAE` (Mean Absolute Error) e `R²` (coeficiente de determinação) foram calculadas para avaliar o desempenho do modelo. Além disso, plotamos gráficos para comparar os valores reais com as predições e para visualizar a perda durante o treinamento.

### 6. Avaliar o Modelo com Novos Dados
Carregamos um novo dataset para realizar predições utilizando os pesos previamente salvos. O novo dataset foi normalizado e predito, e as métricas `MAE` e `R²` foram recalculadas para avaliar o desempenho nos novos dados. Também geramos gráficos para comparar os novos valores reais e predições.
