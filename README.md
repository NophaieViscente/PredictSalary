# Projeto de Previsão Salarial

* Esse projeto faz parte da competição https://www.kaggle.com/c/job-salary-prediction do Kaggle, onde o objetivo é analisar textos de vagas de emprego e efetuar predições dos salários para essas vagas.
* O projeto será executado totalmente via jupyter notebook. Ele fora executado em um laptop com a seguinte configuração. Intel Core i7 10510U 1.8 Ghz 8GB DDR4. Com essa configuração na avaliação do score dos modelos fora despendido mais de 7 horas.

A ideia usada na análise, foi a de usar o texto da descrição das vagas para a predição do salário das mesmas, o algoritmo usado para a vetorização do texto foi o [Word2Vec](/https://medium.com/@everton.tomalok/word2vec-e-sua-import%C3%A2ncia-na-etapa-de-pr%C3%A9-processamento-d0813acfc8ab#:~:text=Word2Vec%20%C3%A9%20um%20m%C3%A9todo%20estat%C3%ADstico%20para%20aprender%20eficientemente,independente%2C%20a%20partir%20de%20um%20corpus%20de%20texto.), que consiste em uma incorporação de palavras a partir de um chamado corpus de texto.



O projeto vem composto de dois notebooks, um onde teremos a [Analise Textual Vagas de Emprego - Análise Exploratória de Dados](/PredictSalary_RegressionProblemExample_AED.ipynb) e outro onde efetuaremos as predições, avaliação do modelo e geração da saida.

# Execução do projeto 

O projeto começa sendo executado, pelo notebook [Analise Textual Vagas de Emprego - Análise Exploratória de Dados](/PredictSalary_RegressionProblemExample_AED.ipynb). Onde encontram-se algumas análise além da exportação do dataset que usaremos posteriormente para as predições.

### Importação das Bibliotecas necessárias para a AED

![lib_AED](https://user-images.githubusercontent.com/61605612/148662577-9156b474-5359-4688-8f67-ae89e2fe0ca9.jpg)

# Referências 

**Word2Vec** - https://medium.com/@everton.tomalok/word2vec-e-sua-import%C3%A2ncia-na-etapa-de-pr%C3%A9-processamento-d0813acfc8ab#:~:text=Word2Vec%20%C3%A9%20um%20m%C3%A9todo%20estat%C3%ADstico%20para%20aprender%20eficientemente,independente%2C%20a%20partir%20de%20um%20corpus%20de%20texto.
