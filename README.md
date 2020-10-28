# Projeto Visualização de Dados  

## Análise das métricas de acurácia de mapas de uso e cobertura do solo  
Este projeto tem como objetivo analisar as incertezas que as ferramentas de acurácias de mapas de uso e cobertura do solo podem apresentar na validação de mapas.  

### Introdução 
<p align="justify">Classificação de imagens é a abordagem mais comum para mensurar a acurácia (Lyons, 2018), onde geralmente é referida ao mapeamento temático, a rotulação de objetos e características de determinados grupos baseados em seus atributos (Sokal, 1974; Jensen, 2015). A avaliação da acurácia indica a qualidade do mapa que foi criado através dos dados de sensoriamento remoto, sendo dividida em acurácia posicional e acurácia temática (Congalton e Green, 2009.p. 02).  
 A acurácia posicional corresponde à diferença da concordância locacional entre dados gerados por Sensoriamento Remoto e pontos terrestres conhecidos ou outra fonte
considerada mais precisa que o mapa (Bolstad, 2005; Congalton, 2009.p.12). Já a acurácia temática avalia a concordância entre a classificação ou atributos dos recursos de um mapa gerados e a verdade em campo, geralmente representada através de uma matriz de confusão (Congalton, 2009.p. 32). Em outras palavras, a matriz de confusão é o resultado de uma tabulação cruzada entre dados classificados (através de análises por sensoriamento remoto por ensoriamento) e os dados de referência (dados válidos) (Comber et al, 2019).
Através da matriz de confusão podem ser aplicadas várias medidas para avaliar a acurácia dos dados, dentre elas tem-se a Acurácia Total, a estatística Kappa de Cohen, o
Índice de Tau, dentre outras.</p>
<p align="justify">O objetivo desse trabalho é analisar a confiabilidade de cinco índices de acurácias baseadas na matriz de confusão: acurácia total, Kappa, Pi de Scott, Tau e Pabak.</p>
  
### Descrição do problema  
<p align="justify">Inicialmente, são criados mapas de referência e mapas de classificação com 4, 5 e 6 classes. Sendo que para a construção dos mapas de classificação, são realizadas alterações nos mapas de referências atribuindo valores de acurácia (50%, 70%, 85% e 95%). Com os dois mapas prontos, são considerados que os valores de acurácia (acurácia real ou atribuída) são desconhecidos e são calculadas novos valores de acurácias (acurácia calculada) variando o tipo de amostragem (aleatória, sistemática) e o tamanho das janelas (5x5, 20x20 e 25x25). Os cálculos são realizados por quatro ferramentas de acurácias baseadas na matriz de confusão (Acurácia Total, Kappa, Pi de Scott e Pabak).</p>
Dois tópicos em questão estão sendo avaliados:  

- O quão próximo os valores de acurácia entre a atribuída (verdadeira ou real) e a calculada são uma da outra, ou seja, como as acurácias calculadas pelas métricas estão distribuídas da acurácia atribuída;
  
* Como as ferramentas (ou métricas) de acurácia podem sofrer variações em suas acurácias calculadas com as variáveis: número de classes, tipo de amostra e tamanho da amostra.

 ### Base de dados   
<p align="justify">A base de dados provém da minha dissertação onde foram criados mapas, também chamados de mapas sintéticos. Os dados são qualitativos-quantitativos, uma vez que foram criados modelos de mapas para cada valor de acurácia.</p>
Resumindo: o dataframe contém 6264 linhas e 10 colunas (variáveis), sendo:
  
1. variáveis categóricas:
  
- Classes: 4, 5 e 6, 

- Amostragem: Sistemática e Aleatória,

- Modelo de mapa: A a I,  
- Tamanho de Janela: 5x5, 20x20 e 25x25 pixels,  
- Acurácia Atribuída: 0.50, 0.70, 0.85 e 0.95   
2. Variáveis quantitativas:
- Métricas: Acurácia Total, Kappa, Pi de Scott e Pabak. 

Na tabela 1 é mostrada as três primeiras linhas do dataframe.

| Classes   | Modelo de Mapa   | Tamanho de Janela   | Acurácia Atribuída   | Acurácia Total   | Kappa   | Tau     | Pi de Scott   | Pabak   | Amostragem   |
| --------- |:----------------:| ------------------: | --------------------:|-----------------:| -------:|--------:|--------------:|--------:|-------------:|
| 4c        | A                | 5x5                 | 0.50                 | 0.514375         | 0.348899| 0.352500| 0.348188      | 0.028750| Sistemática  |
| 4c        | A                | 5x5                 | 0.50                 | 0.532500         | 0.373507| 0.376667| 0.373479      | 0.065000| Sistemática  |
| 4c        | A                | 5x5                 | 0.50                 | 0.571795         | 0.424826| 0.429060| 0.424294      | 0.985710| Sistemática  |

###### Tabela 1: Daataframe com as três primeiras linhas

### Programas e Pacotes
  O Software utilizado para a análise dos dados e a construção dos gráficos foi o Rstudio 1.2.5033 e seus pacotes foram:   
 
 -  dplyr
  - GGally
 - stats
 - ggplot2
 - parcoords
 - plotly
 Foram realizadas imagens interativas e não interativas, de modo que as não interativas são uma alternativa para inserir na dissertação impressa.

### Análises
#### Interativas
<p align="justify">Incialmente são analisadas como as acurácias calculadas por cada métrica estão distribuídas em relação à acurácia atribuída sem considerar as variáveis "Classes", "Tamanho de Janela", "Amostragem" e "Modelo de Mapa".</p>

[Boxplot](https://josiaparecida.github.io/projeto_visualizacao_dados/boxlplotacuraciatotal.html)

#### Não interativas

![bpAT](https://user-images.githubusercontent.com/73483644/97359708-f1b2c100-187b-11eb-920b-6cdc0368dacd.png)  

![bpKP](https://user-images.githubusercontent.com/73483644/97359736-fd05ec80-187b-11eb-8481-b6ed748e9888.png)  

![bpPB](https://user-images.githubusercontent.com/73483644/97359740-fe371980-187b-11eb-9197-f42f56304904.png)  

![bpPI](https://user-images.githubusercontent.com/73483644/97359743-00997380-187c-11eb-8712-544eecf7dda1.png)  

![bpTAU](https://user-images.githubusercontent.com/73483644/97359751-02fbcd80-187c-11eb-91e0-82da2c375383.png)  

