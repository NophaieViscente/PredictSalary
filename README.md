# Projeto de Previsão Salarial

* Esse projeto faz parte da competição https://www.kaggle.com/c/job-salary-prediction do Kaggle, onde o objetivo é analisar textos de vagas de emprego e efetuar predições dos salários para essas vagas.
* O projeto será executado totalmente via jupyter notebook.

O projeto vem composto de dois notebooks, um onde teremos a [Analise Textual Vagas de Emprego - Análise Exploratória de Dados](/PredictSalary_RegressionProblemExample_AED.ipynb) e outro onde efetuaremos as predições, avaliação do modelo e geração da saida.
A ideia usada na análise, foi a de usar o texto da descrição das vagas para a predição do salário das mesmas, o algoritmo usado para a vetorização do texto foi o [Word2Vec](https://medium.com/@everton.tomalok/word2vec-e-sua-import%C3%A2ncia-na-etapa-de-pr%C3%A9-processamento-d0813acfc8ab#:~:text=Word2Vec%20%C3%A9%20um%20m%C3%A9todo%20estat%C3%ADstico%20para%20aprender%20eficientemente,independente%2C%20a%20partir%20de%20um%20corpus%20de%20texto.), que consiste em uma incorporação de palavras a partir de um corpus de texto e o algoritmo usado para as predições foi o [XGBoost](https://xgboost.readthedocs.io/en/stable/), que é um algoritmo baseado em árvores de decisão com reforço de gradiente descendente, para a minimização do erro das predições.
A métrica usada para a avaliação do modelo foi o Erro Médio Absoluto(MAE), o [MAE](https://medium.com/data-hackers/prevendo-n%C3%BAmeros-entendendo-m%C3%A9tricas-de-regress%C3%A3o-35545e011e70) é a média da diferença entre valores reais e valores previstos.


# Execução do projeto 

O projeto começa sendo executado, pelo notebook [Analise Textual Vagas de Emprego - Análise Exploratória de Dados](/PredictSalary_RegressionProblemExample_AED.ipynb). Onde encontram-se algumas análises além da exportação do dataset que usaremos posteriormente para as predições.

### Importação das Bibliotecas necessárias para a AED

![lib_AED](https://user-images.githubusercontent.com/61605612/148662577-9156b474-5359-4688-8f67-ae89e2fe0ca9.jpg)

### Carregamento do Dataset

![AED](https://user-images.githubusercontent.com/61605612/148663831-6240b0d9-c7d7-434e-80c0-8eb2ac08fd9a.jpg)
* Aqui temos uma parte importante, dentro do parenteses fica o caminho do arquivo .csv a ser analisado que é variável. No caso da imagem o 'train.csv' mas em sua máquina poderá ser outro caminho, como sugestão sempre sugiro que o arquivo fique sempre na mesma pasta do notebook.

### Insights Iniciais

![AED2](https://user-images.githubusercontent.com/61605612/148663971-d9622199-c9ad-459f-b801-4dc0b98f0ac3.jpg)
* Aqui pode-se observar que a cidade onde mais se tem vagas é **Londres**. 
* Essa análise fora obtida com uma contagem do agrupamento através da localização bruta das vagas e organizada de forma ascendente.

### Criação de Características

Caso os dados os quais necessitem ser análisados não contenham características relevantes, pode-se adicionar características a partir de outras. Aqui efetuamos a criação de algumas características, tais como faixa salarial, base para cálculo anual do salário (caso esse dataset não tivesse essa característica seria de grande valia), entre outras.

* Aqui criamos uma função para percorrer a coluna determinada e ficar com apenas os algarismos.
![AED3](https://user-images.githubusercontent.com/61605612/148664222-23e1dc0d-2cbe-49c8-a986-0e80ccdd09b6.jpg)

![AED4](https://user-images.githubusercontent.com/61605612/148664247-07b39f24-e6f5-44de-9fdb-ec7d77353f2e.jpg)

* Aqui pode-se observar a criação de duas novas características que são 


# Referências 

**XGBoost** - https://xgboost.readthedocs.io/en/stable/

**Word2Vec** - https://medium.com/@everton.tomalok/word2vec-e-sua-import%C3%A2ncia-na-etapa-de-pr%C3%A9-processamento-d0813acfc8ab#:~:text=Word2Vec%20%C3%A9%20um%20m%C3%A9todo%20estat%C3%ADstico%20para%20aprender%20eficientemente,independente%2C%20a%20partir%20de%20um%20corpus%20de%20texto.

**Erro Médio Absoluto** - https://medium.com/data-hackers/prevendo-n%C3%BAmeros-entendendo-m%C3%A9tricas-de-regress%C3%A3o-35545e011e70
