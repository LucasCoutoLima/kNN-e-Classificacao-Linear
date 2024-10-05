# kNN e Regressão Logística

Esse projeto foi feito para a disciplina de mestrado da Unicamp IA048 - Aprendizado de Máquina.

Nesse projeto foi abordado o problema de reconhecimento de atividades humanas a partir de informações capturadas por sensores de smartphones. Em particular, trabalhei com a base de dados UCI HAR, 
que contém registros de sensores inerciais presentes em um smartphone preso à cintura de 30 sujeitos realizando atividades cotidianas. Cada pessoa realizou seis atividades, as quais correspondem aos seguintes rótulos

| Atividade  | Rótulo |
| ------------- | ------------- |
| Caminhar  | 0  |
| Subir escadas  | 1  |
| Descer escadas | 2 |
| Sentado | 3 |
| Em pé | 4 |
| Deitado | 5 |

Foram capturadas as amostras dos três eixos (x, y e z) do acelerômetro e do giroscópio presentes no smartphone, empregando uma taxa de amostragem de 50 Hz. O conjunto completo de amostras foi particionado aleatoriamente em treinamento (70%) e teste (30%).

O projeto foi dividido da seguinte maneira:

## Primeira parte
Primeiramente, será explorada uma versão do conjunto de dados na qual já houve pré-processamento e extração
de características. No caso, cada amostra contém 561 atributos derivados de uma mesma janela de 2,56 s dos 6
sinais disponíveis (ACC: x,y,z; GYR: x,y,z), considerando suas representações tanto no domínio do tempo quanto
no domínio da frequência.

a) Construa uma solução para este problema baseada no modelo de regressão logística. Descreva a abordagem
escolhida para resolvê-lo (softmax, classificadores binários combinados em um esquema um-contra-um ou
um-contra-todos). Obtenha, então, a matriz de confusão para o classificador considerando os dados do
conjunto de teste. Além disso, adote uma métrica global para a avaliação do desempenho (médio) deste
classificador. Discuta os resultados obtidos.

b) Considere, agora, a técnica k-nearest neighbors (kNN). Adotando um esquema de validação cruzada, mostre
como o desempenho do classificador, computado com a mesma métrica adotada no item a)) varia em função
do parâmetro k. Escolhendo, então, o melhor valor para k, apresente a matriz de confusão para os dados de
teste e o desempenho medido nesse conjunto. Comente os resultados obtidos, inclusive estabelecendo uma
comparação com o desempenho da regressão logística.

## Segunda parte
Agora, vamos utilizar os dados “brutos” combinados de ACC e GYR como entradas dos classificadores. Para
isso, devemos recorrer aos registros disponibilizados no diretório ’Inertial Signals’, os quais estão separados por eixo
e por sensor, sendo que cada amostra individual agora  ́e formada por 128 valores (atributos), que correspondem `as
amplitudes instantâneas de aceleração (ACC) ou velocidade angular (GYR) dentro de uma janela de 2,56 s.

c) Monte, então, a nova matriz de entrada concatenando os seis sinais temporais e, então, repita o procedimento
experimental detalhado nos itens a) e b). Ao final, com base no desempenho obtido, teça uma análise
comparativa entre a abordagem do item anterior e a abordagem baseada nos sinais ”brutos”empregada nesta
segunda parte.
