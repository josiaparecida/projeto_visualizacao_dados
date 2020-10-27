# Projeto Visualizacao Dados  

<p align="justify"> 

# Análise das métricas de acurácia de mapas de uso e cobertura do solo  
Este projeto tem como objetivo analisar as incertezas das ferramentas de acurácias de mapas de uso e cobertura do solo podem apresentar em validação de mapas.  

**Introdução** 
<p align="justify"> 
Classificação de imagens é a abordagem mais comum para mensurar a acurácia (Lyons, 2018), onde geralmente é referida ao mapeamento temático, a rotulação de objetos e características de determinados grupos baseados em seus atributos (Sokal, 1974; Jensen, 2015). A avaliação da acurácia indica a qualidade do mapa que foi criado através dos dados de sensoriamento remoto, sendo dividida em acurácia posicional e acurácia temática (Congalton e Green, 2009.p. 02).  
A acurácia posicional corresponde à diferença da concordância locacional entre dados gerados por Sensoriamento Remoto e pontos terrestres conhecidos ou outra fonte
considerada mais precisa que o mapa (Bolstad, 2005; Congalton, 2009.p.12). Já a acurácia temática avalia a concordância entre a classificação ou atributos dos recursos de um mapa gerados e a verdade em campo, geralmente representada através de uma matriz de confusão (Congalton, 2009.p. 32). Em outras palavras, a matriz de confusão é o resultado de uma tabulação cruzada entre dados classificados (através de análises por sensoriamento remoto por ensoriamento) e os dados de referência (dados válidos) (Comber et al, 2019).
Através da matriz de confusão podem ser aplicadas várias medidas para avaliar a acurácia dos dados, dentre elas tem-se a Acurácia Total, a estatística Kappa de Cohen, o
Índice de Tau, dentre outras.  
O objetivo desse trabalho é analisar a confiabilidade de cinco índices de acurácias baseadas na matriz de confusão: acurácia total, Kappa, Pi de Scott, Tau e Pabak.</p>
  
**Descrição do problema** 
<p align="justify">
Dois tópicos em questão estão sendo avaliados:  
*	O quão próximo os valores de acurácia entre a atribuída (verdadeira ou real) e a calculada são uma da outra – em outras palavras o nível de incerteza entre elas;  
*	Como as ferramentas (ou métricas) de acurácia podem sofrer alterações em seus valores calculados com as variáveis: número de classes, tipo de amostra e tamanho da amostra.  
Por enquanto algumas técnicas que serão utilizadas são: o gráfico de linhas para comparar a diferença entre as acurácias real e calculada, boxplot com linhas de tendência, diagrama de pareto. Pequenos múltiplos serão utilizados para comparar como as acurácias se alteram com as variáveis.  
Medidas quantitativas como média, mediana, desvio padrão e variância.  
Ao final espero verificar a incerteza entre as acurácias e qual(is) é(são) as variáveis que mais influenciam no cálculo das métricas de acurácia.</p>  
 
**Base de dados**  
<p align="justify">
Minha base de dados provém a partir de mapas criados, também chamados de mapas sintéticos. Inicialmente, são criados mapas de referência e mapas de classificação com 4, 5 e 6 classes. Sendo que para a construção dos mapas de classificação, são realizadas alterações nos mapas de referências atribuindo valores de acurácia (50%, 70%, 85% e 95%). Com os dois mapas prontos, são considerados que os valores de acurácia (acurácia real) são desconhecidos e são calculadas novas acurácias (acurácia calculada) variando o tipo de amostragem (aleatória, sistemática) e o tamanho das janelas (5x5, 20x20 e 25x25). Os cálculos são realizados por quatro ferramentas de acurácias baseadas na matriz de confusão (Acurácia Total, Kappa, Pi de Scott e Pabak).  
Os dados são qualitativos-quantitativos, uma vez que foram criados modelos de mapas para cada valor de acurácia.</p>











