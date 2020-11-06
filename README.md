# Trabalho Big Data com Python

Esse repositório possui conteúdos da aula de Big Data com Python.

## Relatório

Os Dados analisados para o trabalho foram retirados do site: 

* UCI - Machine Learning Repository ( http://archive.ics.uci.edu/ml/datasets/Wine )

Os dados analisados foram o resultado de uma análise química de vinhos cultivados em uma mesma região da Itália, porém são derivados 
de três cultivos diferentes. A análise determinou as quantidades de treze compostos encontrados em cada um dos três tipos de vinho.

Os compostos encontrados foram esses: Álcool, Ácido málico, Cinza, Alcalinidade das cinzas, Magnésio, Fenóis totais, Flavanóides, 
Fenóis não flavonóides, Proantocianinas, Intensidade de cor, Matiz, OD280 / OD315 de vinhos diluídos, Prolina.

## Análise e Comandos dos Gráficos Gerados

* Dimensão do DataFrame:

Para retornar a quantidade de linhas e colunas do DataFrame utilizado:

### `print(df.shape)`

* Resumo estatístico

Para retornar a descrição do DataFrame como uma tabela pode se usar o comando:

### `print(df.describe())`

* Distribuição de classe

Para se realizar a análise geral dos dados, antes se deve realizar um agurpamento geral da base para buscar possíveis indicadores, na execução 
do documento foi utilizado o agrupamento por classe.

### `print(df.groupby('class').size())`

* Gráfico de box and whisker

### `df.plot(kind='box', subplots=True, layout=(7,2), sharex=False, sharey=False) plt.show()`

* Histograma

### `df.hist() plt.show()`

* Gráfico de dispersão

### `df.hist() plt.show()`

* Gráfico de dispersão

### `scatter_matrix(df,figsize=(12,12)) plt.show()`

Após a criação de conjunto de validação e a geração de métricas, é utilizado o uso de alguns algoritmos para a busca de alguns dados como:
Regressão Logística (LR), Análise Linear Discriminante (LDA), K-vizinhos mais próximos (KNN), Árvores de Classificação (Decision Tree),
Regressão (CART), Gaussian Naive Bayes (NB) e Support Vector Machines (SVM).

Os dados gerados por esse algoritmos foram:

 ```
    LR: 0.921429 (0.108091)
    LDA: 0.964762 (0.047581)
    KNN: 0.802381 (0.063003)
    CART: 0.916190 (0.082071)
    NB: 0.936190 (0.108069)
    SVM: 0.874286 (0.073900)
 ```

Utilizando o algoritmos de comparação, observa-se que o KNN está com a média próxima do 0,80

A precisão do modelo no conjunto de validação obteve os seguintes resultados, a acurácia está em 78%. A proporção de positivos 
que foram identificados como corretos pode se ver na coluna de recall com os valores 1.00, 0.76, 0.67 respectivamente. E o balanço 
entre precisão e o recall do modelo pode ser observada na coluna de f1-score com os valores 0.70, 0.84, 0.76 respectivamente.