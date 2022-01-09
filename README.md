# Projeto de Previsão Salarial - Usando Processamento de Linguagem Natural (PLN)

* Esse projeto visa uma solução para a competição https://www.kaggle.com/c/job-salary-prediction do Kaggle, onde o objetivo é analisar textos de vagas de emprego e efetuar predições dos salários para essas vagas.
* O projeto será executado totalmente via jupyter notebook. Será necessário a instalação de algumas bibliotecas, são elas :
[word2vec](https://radimrehurek.com/gensim/auto_examples/tutorials/run_word2vec.html), [nltk](https://www.nltk.org/), [wordcloud](http://amueller.github.io/word_cloud/).  

### Visão Geral
A Análise das vagas de emprego pode ser importante tanto para usuários quanto para empresas, para usuários para saber se determinada vaga atende a seus requisitos salariais e para emoresas para que se possa praticar um salário justo, alinhado com o mercado. Neste projeto tem se por objetivo analisar os dados fornecidos na competição da Adzuna do Kaggle, para tentar predizer o salário anual para cada vaga.
O projeto vem composto de dois notebooks, um onde teremos a [Analise Textual Vagas de Emprego - Análise Exploratória de Dados (AED)](/PredictSalary_RegressionProblemExample_AED.ipynb) e outro onde efetuaremos as predições, avaliação do modelo e geração da saida.
A ideia usada na análise, foi a de usar o texto da descrição das vagas para a predição do salário das mesmas, o algoritmo usado para a vetorização do texto foi o [Word2Vec](https://medium.com/@everton.tomalok/word2vec-e-sua-import%C3%A2ncia-na-etapa-de-pr%C3%A9-processamento-d0813acfc8ab#:~:text=Word2Vec%20%C3%A9%20um%20m%C3%A9todo%20estat%C3%ADstico%20para%20aprender%20eficientemente,independente%2C%20a%20partir%20de%20um%20corpus%20de%20texto.), que consiste em uma incorporação de palavras a partir de um corpus de texto e o algoritmo usado para as predições foi o [XGBoost](https://xgboost.readthedocs.io/en/stable/), que é um algoritmo baseado em árvores de decisão com reforço de gradiente descendente, para a minimização do erro das predições.
A métrica usada para a avaliação do modelo foi o Erro Médio Absoluto(MAE), o [MAE](https://medium.com/data-hackers/prevendo-n%C3%BAmeros-entendendo-m%C3%A9tricas-de-regress%C3%A3o-35545e011e70) é a média da diferença entre valores reais e valores previstos.

### Fonte de dados

https://www.kaggle.com/c/job-salary-prediction/data

# Execução do projeto

* Para a execução do projeto fora usado a metodologia CRISP-DM, apenas não sendo contemplada a etapa de deploy do modelo, que poderá ser executada posteriormente.

O projeto começa sendo executado, pelo notebook [Analise Textual Vagas de Emprego - Análise Exploratória de Dados (AED)](/PredictSalary_RegressionProblemExample_AED.ipynb). Onde encontram-se algumas análises além da exportação do dataset que usaremos posteriormente para as predições que estão no notebook ...

### Entendimento Objetivos do Projeto 

* O objetivo do projeto é predizer salários com base na descrição textual de suas vagas.

**Quem poderá utilizar as análises ?**
* Empresas podem utilizar as análises para equiparar seus salários e criar vagas atrativas a determinado tipo de profissional.
* Usuários podem utilizar as análises para validar se a vaga contém o salário desejado.

### Entendimento dos Dados

* Os dados utilizados são dados fornecidos pela Adzuna para a competição [Job Prediction](https://www.kaggle.com/c/job-salary-prediction) do Kaggle, os dados de treino contém as colunas:
***Id, Title, FullDescription, LocationRaw, LocationNormalized, ContractType, ContractTime, Company, Category, SalaryRaw, SalaryNormalized e SourceName.***

* Os dados de teste e validação não contém as colunas relacionadas ao salário, SalaryRaw e SalaryNormalized.

O dataSet de treino tem ***244768*** linhas. Conforme imagem : 

![AED5](https://user-images.githubusercontent.com/61605612/148666686-c971e04d-bdc4-423e-b8b8-1bef1e2e27b8.jpg)
* Existem algumas colunas com dados nulos/faltantes, são elas : ContractType, ContractTime, Company e Title.

### Preparação dos Dados

***Várias etapas estão contempladas nessa etapa.***

* Retirada de caracteres indesejados do texto, como caracteres especiais e numerais;
* Transformação de todo o texto em minúscula, para a padronização de texto;
* Remoção de palavras não aproveitáveis, como 'stopwords' por exemplo; 
* Criação de novas características, como Faixa Salarial, Base de Cálculo para Salário;
* Normalização de dados;
* Processamento e vetorização do texto. 

### Modelagem

* Ambos os modelos testados foram contemplados com pré-processamento de palavras do modelo [Word2Vec](https://medium.com/@everton.tomalok/word2vec-e-sua-import%C3%A2ncia-na-etapa-de-pr%C3%A9-processamento-d0813acfc8ab#:~:text=Word2Vec%20%C3%A9%20um%20m%C3%A9todo%20estat%C3%ADstico%20para%20aprender%20eficientemente,independente%2C%20a%20partir%20de%20um%20corpus%20de%20texto.).
*  Após isso foram passados os dados para os modelos preditores [Regressão Linear](https://medium.com/@lauradamaceno/regress%C3%A3o-linear-6a7f247c3e29) e [XGBoost](https://xgboost.readthedocs.io/en/stable/) para treinamento e validação.

### Avaliação

* Para a avaliação fora usada a métrica de MAE. 
* O modelo que teve melhor performance foi o XGBoost, com um score de 0.71 e MAE no conjunto de treinamento de ...

### Deploy

Essa parte do projeto ainda não foi desenvolvida.

### Limitações e Trabalhos Futuros

* Como sugestão sugere-se o uso de outras características para as análises. 
* Utilização de modelos diferentes de vetorização para o texto, como TF-IDF. 
* Possibilidade de utilização de um algoritmo linear mais poderoso como o [Vowpal Wabbit](https://vowpalwabbit.org/docs/vowpal_wabbit/python/latest/index.html). 
* Dentre as limitações estão o Hardware, por se tratar de um grande volume textual, é interessante ter um hardware sgnificativamente bom para o treinamento/otimização dos modelos.


# Referências 

**Erro Médio Absoluto** - https://medium.com/data-hackers/prevendo-n%C3%BAmeros-entendendo-m%C3%A9tricas-de-regress%C3%A3o-35545e011e70

**Regressão Linear** - https://medium.com/@lauradamaceno/regress%C3%A3o-linear-6a7f247c3e29

**Vowpal Wabbit** - https://vowpalwabbit.org/docs/vowpal_wabbit/python/latest/index.html

**XGBoost** - https://xgboost.readthedocs.io/en/stable/

**Word2Vec** - https://medium.com/@everton.tomalok/word2vec-e-sua-import%C3%A2ncia-na-etapa-de-pr%C3%A9-processamento-d0813acfc8ab#:~:text=Word2Vec%20%C3%A9%20um%20m%C3%A9todo%20estat%C3%ADstico%20para%20aprender%20eficientemente,independente%2C%20a%20partir%20de%20um%20corpus%20de%20texto.


