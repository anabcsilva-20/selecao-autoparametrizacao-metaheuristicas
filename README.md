# Projeto de Seleção e Autoparâmetrização de Meta-heurísticas com Machine Learning


# Descrição Geral

Este documento apresenta, de forma resumida, a descrição e a finalidade de cada ficheiro incluído no projeto.

Os documentos presentes nesta pasta referem-se aos modelos preditivos desenvolvidos para a seleção e autoparâmetrização de Meta-heurísticas, com a utilização 
de técnicas de Machine Learning, para otimização de problemas de escalonamento. Ao longo do projeto, foi implementada a metodologia CRISP-DM, das quais algumas 
etapas são apresentadas nos ficheiros.

## Ficheiros Excel (pasta Data)
 os ficheiros excel são relativos às bases de dados utilizadas neste trabalho.
    - DataSet_DadosBrutos: ficheiro com os dados brutos usados no projeto. Todos os restantes ficheiros em excel resultam de transformações aplicadas 
    neste conjunto de dados. 

    - DataSet_ModeloClassificação: ficheiro utilizado para a realização do modelo preditivo de seleção da Meta-heurística (modelo de classificação). Ficheiro
    desenvolvido na etapa preparação dos dados. 

    - DataSet_Regressão_GA, DataSet_Regressão_PSO, DataSet_Regressão_SA, DataSet_Regressão_TS: ficheiros utilizados para a realização dos modelos preditivos
    individuais relativos à afinação dos parâmetros da Meta-heurística (modelo regressão). Cada ficheiro é relativo apenas a uma Meta-heurística, ficheiros 
    desenvolvidos na etapa preparação dos dados.

    - DataSet_Regressão_ModeloGeral: ficheiro utilizado para a realização do modelo preditivo geral de afinação das Meta-heurísticas. É a combinação dos
    ficheiros excel apresentados anteriormente (combinação dos ficheiros dos modelos preditivos individuais). Ficheiro desenvolvido na etapa preparação dos 
    dados. 

## Jupyter Notebooks (pasta Notebooks)
Compreensão dos dados: análise exploratória realizada aos dados brutos, com o intuito de compreender a distribuição e padrões que possam existir nos dados
brutos (utiliza o ficheiro excel DataSet_DadosBrutos). Todas as análises realizadas estão expressas no ficheiro CompreensãoDadosBrutos.ipynb. 

Modelo preditivo de seleção da Meta-heurística:

    - Preparação dos dados: os dados utilizados no modelo preditivo é o ficheiro excel DataSet_ModeloClassificação.
    
    - Modelação: o modelo preditivo está elaborado no ficheiro ModeloPred_Classificação.ipynb. Contém a aplicação de cinco técnicas de Machine Learning: 
    Árvores de Decisão, Random Forest, Support Vector Machines, Naive Bayes, Regressão Logística. 
    
    - Avaliação: no modelo preditivo do ficheiro ModeloPred_Classificação.ipynb é possível observar, em cada técnica de Machine Learning, os resultados
    das métricas de avaliação (Accuracy, F1 Score Precision, Recall, AUC).

Modelo preditivo de afinação dos parâmetros das Meta-heurísticas: foram desenvolvidos dois modelos, um modelo preditivo individual para cada Meta-heurística
(Algoritmos Genéticos, Simulated Annealing, Tabu Search, Particle Swarm Optimization) e um modelo preditivo geral que realiza a afinação dos parâmetros de 
todas as Meta-heurísticas. Em ambos os modelos são aplicadas três técnicas de Machine Learning: Árvores de Decisão, Random Forest e Regressão Linear. 

    - Modelos preditivos individuais:
    
        - Relativo à Meta-heurística Algoritmos Genéticos: modelo preditivo individual está elaborado no ficheiro ModeloRegressão_GA.ipynb. Utiliza o ficheiro
        excel DataSet_Regressão_GA.
        
        - Relativo à Meta-heurística Simulated Annealing: modelo preditivo individual está elaborado no ficheiro ModeloRegressão_SA.ipynb. Utiliza o ficheiro
        excel DataSet_Regressão_SA.
        
        - Relativo à Meta-heurística Particle Swarm Optimization e Tabu Search: estes dois modelos preditivo individuais estão elaborados no ficheiro 
        ModeloRegressão_PSO_TS.ipynb. O modelo individual de cada Meta-heurística pode ser realizado nesse ficheiro, apenas tem de trocar o ficheiro excel
        associado e as variáveis dependentes consideradas. O ficheiro ModeloRegressão_PSO_TS.ipynb neste momento está configurado para realizar o modelo 
        preditivo individual de Particle Swarm Optimization mas, em comentário, é possível observar as mudanças a realizar para modificar para o modelo 
        preditivo individual de Tabu Search. Utiliza o ficheiro DataSet_Regressão_PSO ou o DataSet_Regressão_TS.
        
    - Modelo preditivo geral: o modelo preditivo geral está elaborado no ficheiro ModeloRegressão_Geral.ipynb. Utiliza o ficheiro excel 
    DataSet_Regressão_ModeloGeral.
    
    - Avaliação: em todos os modelos, individuais e geral, é possível observar os resultados das métricas de avaliação consideradas (MSE, RMSE, MAE, MAPE, R^2). 


