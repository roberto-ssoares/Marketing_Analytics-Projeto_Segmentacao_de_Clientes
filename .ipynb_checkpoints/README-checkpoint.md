# Marketing Analytics

Marketing Analytics compreende os processos e tecnologias que permitem aos profissionais de Marketing avaliar o sucesso de suas iniciativas. 

![image](imagens/marketing_analytics.png)
-

Isso é feito medindo o desempenho das campanhas de Marketing, coletando os dados e analisando os resultados. Marketing Analytics utiliza métricas importantes de negócios, como ROI (Retorno Sobre o Investimento), Atribuição de Marketing e Eficácia Geral do Marketing. Em outras palavras, o Marketing Analytics mostra se os programas de Marketing estão sendo efetivos ou não.

Marketing Analytics reúne dados de todos os canais de marketing e os consolida em uma visão de marketing comum. A partir dessa visão comum, você pode extrair resultados analíticos que podem fornecer assistência inestimável para impulsionar os esforços de marketing.


![image](imagens/marketing_analytics_importante.png)
-


Você pode responder a perguntas como estas:

![image](imagens/marketing_analytics_oque_se_pode_fazer.png)
-




## Projeto de Segmentação de Clientes - Food Delivery

![image](imagens/projeto_segmentacao_clientes.png)
-

A segmentação permite que os profissionais de marketing adaptem melhor seus esforços de marketing a vários subconjuntos de público-alvo.


![image](imagens/segmentacao_ajuda.png)
-


## O Que é Segmentação de Clientes?

A segmentação de clientes é o processo de dividir os clientes em grupos com base em características comuns, para que as empresas possam comercializar para cada grupo de forma eficaz e adequada, ou simplesmente compreender o padrão de consumo dos clientes.

![image](imagens/segmentation.png)


##  Marketing B2B x Marketing B2C

No Marketing Business-to-Business (B2B), uma empresa pode segmentar clientes de acordo com uma ampla variedade de fatores, incluindo:

- Indústria
- Número de empregados
- Produtos comprados anteriormente na empresa
- Localização

No Marketing Business-to-Consumer (B2C), as empresas geralmente segmentam os clientes de acordo com dados demográficos e padrões de consumo, tal como:

- Idade
- Gênero
- Estado civil
- Localização (urbana, suburbana, rural)
- Estágio da vida (sem filhos, aposentado, etc.)
- Produtos comprados
- Valor gasto
- Horário de consumo


## Como Segmentar Clientes?

A segmentação de clientes exige que uma empresa colete informações específicas - dados - sobre clientes e analise-as para identificar padrões que podem ser usados para criar segmentos.

Parte disso pode ser obtida a partir de informações de compra - cargo, geografia, produtos adquiridos, por exemplo. Algumas delas podem ser obtidas da forma como o cliente entrou no seu sistema. Um profissional de marketing que trabalha com uma lista de e-mail de inscrição pode segmentar mensagens de marketing de acordo com a oferta de inscrição que atraiu o cliente, por exemplo. Outras informações, no entanto, incluindo dados demográficos do consumidor, como idade e estado civil, precisarão ser adquiridas de outras maneiras.

Os métodos típicos de coleta de informações incluem:

- Entrevistas presenciais ou por telefone
- Pesquisas
- Coleta de informações publicadas sobre categorias de mercado
- Grupos de foco
- Dados de acessos a sistemas ou apps


## Usando Segmentos de Clientes

Características comuns nos segmentos de clientes podem orientar como uma empresa comercializa segmentos individuais e quais produtos ou serviços ela promove. Uma pequena empresa que vende guitarras feitas à mão, por exemplo, pode decidir promover produtos com preços mais baixos para guitarristas mais jovens e guitarras premium com preços mais altos para músicos mais velhos, com base no conhecimento do segmento que lhes diz que os músicos mais jovens têm menos renda disponível do que seus colegas mais velhos. 

A segmentação de clientes pode ser praticada por todas as empresas, independentemente do tamanho ou setor, e se vendem on-line ou presencialmente. Começa com a coleta e a análise de dados e termina com a atuação nas informações coletadas de maneira apropriada e eficaz, com a entrega das conclusões.

## Iniciando o Desenvolvimento do Projeto

### Carregando e Compreendendo os Dados

![image](imagens/imagem01.png)

Dataset com 260645 linhas e 7 colunas

## Dicionário de Dados

|Variável                              | Descrição                                                             |
|--------------------------------------|-----------------------------------------------------------------------|
|id_transacao                          | ID da transação. Um mesmo ID pode ter vários itens de um pedido.      |
|horario_pedido                        | Horário exato do pedido.                                              |
|localidade                            | Localidade que processou o pedido (unidade do restaurante).           |
|nome_item                             | Nome do item (pizza, salada, bebida e sobremesa).                     |
|quantidade_item                       | Quantidade de itens no pedido.                                        |
|latitude                              | Latitude da localidade onde o pedido foi gerado.                      |
|longitude                             | Longitude da localidade onde o pedido foi gerado.                     |
|______________________________________|_______________________________________________________________________|



## Dicionário de Dados

|Variável                              | Descrição                                                             |
|--------------------------------------|-----------------------------------------------------------------------|
|id_transacao                          | ID da transação. Um mesmo ID pode ter vários itens de um pedido.      |
|horario_pedido                        | Horário exato do pedido.                                              |
|localidade                            | Localidade que processou o pedido (unidade do restaurante).           |
|nome_item                             | Nome do item (pizza, salada, bebida e sobremesa).                     |
|quantidade_item                       | Quantidade de itens no pedido.                                        |
|latitude                              | Latitude da localidade onde o pedido foi gerado.                      |
|longitude                             | Longitude da localidade onde o pedido foi gerado.                     |
|______________________________________|_______________________________________________________________________|


### Análise Exploratória

Vamos explorar os dados por diferentes perspectivas e compreender um pouco mais o relacionamento entre as variáveis.

|Variaveis      |Cardinalidade| 
|---------------|-------------|
|id_transacao   |       100000|
|horario_pedido |        76799|
|localidade     |            9|
|nome_item      |            4|
|quantidade_item|            5|
|latitude       |            9|
|longitude      |            9|

Após aplicar a função unique no dataset "df_food_delivery.nunique()", verificou-se a cardinalidade das variáveis:

|Variável        | Valores Únicos | Observações                                                                   |
|----------------| ---------------|-------------------------------------------------------------------------------|
|id_transacao    |       100000   | 100K de transações, que corresponde a uma fatia dos dados.                    |
|horario_pedido  |        76799   | Grande variabilidade no tempo, o que é bom para análises temporais.           |
|localidade      |            9   | Neste recorde observa-se apenas nove locais ou unidade do restaurante.        |
|nome_item       |            4   | Observa-se 4 produtos no estudo.                                              |
|quantidade_item |            5   | A quantidade de qualquer produto analisado não ultrapassou 5 quantidades.     |
|latitude        |            9   | Representa a localidade.                                                      |
|longitude       |            9   | Representa a localidade.                                                      |
|................|................|...............................................................................|


Aplicamos "df_food_delivery.info(memory_usage='deep')"

- Este método imprime informações sobre um DataFrame, incluindo o tipo de índice e colunas, valores não nulos e uso de memória.
- O parâmetro memory_usage permite o modo de introspecção profunda, especialmente útil para grandes DataFrames e otimização de memória de ajuste fino:

<class 'pandas.core.frame.DataFrame'>
RangeIndex: 260645 entries, 0 to 260644
Data columns (total 7 columns):
| #   |Column           |Non-Null|  Count   |Dtype  |
|---  |------           |------- |-------   |-----  |
| 0   |id_transacao     |260645  |non-null  |object |
| 1   |horario_pedido   |260645  |non-null  |object |
| 2   |localidade       |260645  |non-null  |int64  |
| 3   |nome_item        |260645  |non-null  |object |
| 4   |quantidade_item  |260645  |non-null  |int64  |
| 5   |latitude         |260645  |non-null  |float64|
| 6   |longitude        |260645  |non-null  |float64|

dtypes: float64(2), int64(2), object(3)
memory usage: 58.9 MB

Verificamos 260645 linhas, nenhum valor nulo, as variáveis são dos tipos float64(2), int64(2), object(3) e esse dataset está ocupando 58.9 MB da memória.


Resumo das colunas numéricas com "df_food_delivery.describe()"

|calc |     localidade|  quantidade_item|       latitude|      longitude|
|-----|---------------|-----------------|---------------|---------------|
|count|  260645.000000|    260645.000000|  260645.000000|  260645.000000|
|mean |       5.134904|         2.447010|      41.836095|     -87.733930|
|std  |       2.551846|         1.330863|       0.144459|       0.136369|
|min  |       1.000000|         1.000000|      41.524598|     -88.010140|
|25%  |       3.000000|         1.000000|      41.784576|     -87.849468|
|50%  |       5.000000|         2.000000|      41.881818|     -87.677606|
|75%  |       7.000000|         4.000000|      41.889047|     -87.627059|
|max  |       9.000000|         5.000000|      42.049306|     -87.607565|

Aqui observamos que as vendas não estão concentradas, na média 5 locais estão operando. Quanto a quantidade no itens, confirmamos a quantidade máxima de 5 como verificamos acima.


|x |id_transacao|       horario_pedido|  localidade|  bebida|  pizza|  sobremesa|  salada|
|--|------------|---------------------|------------|--------|-------|-----------|--------|
|0 |    0x10000a|  2019-01-29 00:48:00|           9|       0|      1|          1|       0|
|1 |    0x100058|  2019-05-05 00:08:00|           6|       0|      2|          2|       0|
|2 |    0x1000c8|  2019-01-28 19:24:00|           9|       4|      4|          5|       1|
|3 |    0x10014c|  2019-02-23 00:15:00|           6|       0|      1|          1|       0|
|4 |    0x1001d8|  2019-06-30 17:50:00|           2|       3|      3|          3|       0|

Observe como uma simples mudança nos dados já oferece uma perspectiva completamente diferente dos dados. Na prática, o que fizemos foi criar uma tabela pivot.


|calc |             bebida|          pizza|         salada|      sobremesa|
|-----|-------------------|---------------|---------------|---------------|
|count|      100000.000000|  100000.000000|  100000.000000|  100000.000000|
|mean |           1.239590|       1.857840|       0.711370|       2.569210|
|std  |           1.627886|       1.588589|       1.086524|       1.332084|
|min  |           0.000000|       0.000000|       0.000000|       1.000000|
|25%  |           0.000000|       1.000000|       0.000000|       1.000000|
|50%  |           0.000000|       1.000000|       0.000000|       2.000000|
|75%  |           3.000000|       3.000000|       1.000000|       4.000000|
|max  |           5.000000|       5.000000|       5.000000|       5.000000|

Observamos que os valores para salada são baixos, os clientes não consomem muito.



Extraindo Granularidade de Tempo

|idx   |id_transacao|horario_pedido      |localidade | bebida | pizza | sobremesa | salada | mes|   ano|
|------|------------|--------------------|-----------|--------|-------|-----------|--------|----|------|
|0     |0x10000a    |2019-01-29 00:48:00 |          9|       0|      1|          1|       0|  01|  2019|
|1     |0x100058    |2019-05-05 00:08:00 |          6|       0|      2|          2|       0|  05|  2019|
|2     |0x1000c8    |2019-01-28 19:24:00 |          9|       4|      4|          5|       1|  01|  2019|
|3     |0x10014c    |2019-02-23 00:15:00 |          6|       0|      1|          1|       0|  02|  2019|
|4     |0x1001d8    |2019-06-30 17:50:00 |          2|       3|      3|          3|       0|  06|  2019|
|5     |0x1002af    |2019-12-28 17:25:00 |          9|       3|      3|          4|       1|  12|  2019|
|6     |0x10034c    |2019-03-12 18:17:00 |          5|       3|      4|          4|       0|  03|  2019|
|7     |0x100378    |2019-10-13 18:44:00 |          4|       4|      4|          5|       1|  10|  2019|
|8     |0x100391    |2019-10-10 18:07:00 |          5|       4|      4|          4|       0|  10|  2019|
|9     |0x1003a9    |2019-06-23 00:39:00 |          6|       0|      2|          2|       0|  06|  2019|

- A coluna de horário do pedido tem detalhes como mês, dia e ano. Em algum momento pode ser interessante fazer a segmentação por mês, por exemplo. 
- Extraímos o mês e colocamos em uma coluna separada.


### Análise Descritiva

#### "Distplot"/Histplot dos Atributos Usados Para Segmentação

Um histograma é uma ferramenta de visualização clássica que representa a distribuição de uma ou mais variáveis contando o número de observações que se enquadram em compartimentos discretos.

Esta função pode normalizar a estatística calculada dentro de cada compartimento para estimar frequência, densidade ou massa de probabilidade, e pode adicionar uma curva suave obtida usando uma estimativa de densidade de kernel, semelhante a kdeplot().

![image](imagens/distplot01.png)

 - Nos temos os pedidos registrados 24h por dia. Em alguns horários temos um volume alto e em outros próximos a zero.
 - Para pizza e sobremesa, observamos um equilíbrio indicando um frequência similar, o mesmo não vemos em salada onde temos um pico em quantidade zero.
 - Localida temos também um padrão, com dois picos específicos.
 
 
 #### Gráfico de Total de Pedidos Por Localidade
 
 
 ![image](imagens/count_plot01.png)
 
 - Observamos na localidade 2 o maior número de pedidos e na localidade 5 o menor número de pedidos.
 
 
 #### Regplot dos Atributos Usados Para Segmentação
 
- A função regplot() do Seaborn é uma ferramenta poderosa para criar gráficos de dispersão com uma linha de regressão ajustada aos dados. Essa função combina duas funcionalidades principais:
    
    - Gráfico de Dispersão (Scatter Plot): Exibe pontos no plano cartesiano, onde cada ponto representa um par de valores. Isso é útil para visualizar a relação entre duas variáveis.
    
    - Linha de Regressão (Regression Line): A função regplot() calcula automaticamente e exibe uma linha de regressão linear. Essa linha representa a melhor estimativa da relação linear entre as variáveis dependentes e independentes.

- A linha de regressão é ajustada aos dados usando métodos estatísticos para minimizar a soma dos quadrados dos resíduos, proporcionando uma representação visual da tendência geral nos dados. 
    
    - Se a linha de regressão estiver inclinada para cima, indica uma correlação positiva entre as variáveis, 
    - enquanto uma inclinação para baixo indica uma correlação negativa.

- A função regplot() é útil para identificar padrões, tendências e para fazer previsões aproximadas com base na relação entre duas variáveis. 
- Além disso, ela pode fornecer intervalos de confiança ao redor da linha de regressão para indicar a variabilidade da estimativa.

![image](imagens/regplot01.png)

Aqui podemos ver o comportamento entre as variáveis. 


### Análise de Cluster

- Clusterização é um processo de aprendizagem não supervisionada, quando entregamos a um algoritmo de Machine Learning somente os dados de entrada e durante o treinamento, o algoritmo cria um modelo capaz de gerar saídas, nesse caso grupos, ou clusters.

![image](imagens/cluster.png)


#### Algoritmo de Clusterização - K-means

https://scikit-learn.org/stable/modules/generated/sklearn.cluster.KMeans.html

O K-Means Clustering é um algoritmo de aprendizado de máquina não supervisionado. Em contraste com os algoritmos tradicionais de aprendizado de máquina supervisionado, o K-Means tenta classificar dados sem antes ter sido treinado com dados rotulados. Depois que o algoritmo é executado e os grupos são definidos, qualquer novo dado pode ser facilmente atribuído ao grupo mais relevante.


![image](imagens/kmeans.png)


K-Means é provavelmente o algoritmo de agrupamento mais conhecido. É fácil entender e implementar! Confira o gráfico abaixo para obter uma ilustração.

![image](imagens/k-means.gif)


- Para começar, primeiro selecionamos um número de classes / grupos que desejamos e inicializamos aleatoriamente seus respectivos pontos centrais (centróides). Para descobrir o número de classes a serem usadas, é bom dar uma olhada rápida nos dados e tentar identificar grupos distintos. 


- Cada ponto de dados é classificado calculando a distância entre esse ponto e cada centro de grupo e, em seguida, classificando o ponto no grupo cujo centro está mais próximo.


- Com base nesses pontos classificados, recalculamos o centro do grupo, calculando a média de todos os vetores do grupo.


- Repitimos essas etapas para um número definido de iterações ou até que os centros dos grupos não alterem muito entre as iterações. Você também pode optar por inicializar aleatoriamente os centros do grupo algumas vezes e selecionar a execução que parece ter fornecido os melhores resultados.

O K-Means tem a vantagem de ser muito rápido, pois estamos realmente calculando as distâncias entre pontos e centros de grupos; são poucos cálculos! Portanto, possui uma complexidade linear O(n).

Por outro lado, o K-Means tem algumas desvantagens. Primeiro, você deve selecionar quantos grupos / clusters. Isso nem sempre é trivial e, idealmente, com um algoritmo de agrupamento, queremos que ele os descubra, porque o objetivo é obter algumas informações dos dados. 

O K-means também começa com uma escolha aleatória de centros de cluster e, portanto, pode produzir resultados de cluster diferentes em execuções diferentes do algoritmo. Assim, os resultados podem não ser repetíveis e não têm consistência. Outros métodos de cluster são mais consistentes.

K-Medians é outro algoritmo de agrupamento relacionado ao K-Means, exceto que, em vez de recalcular os pontos centrais do grupo usando a média, usamos o vetor de medianas do grupo. Esse método é menos sensível a outliers (por causa do uso da Mediana), mas é muito mais lento para conjuntos de dados maiores, pois a classificação é necessária em cada iteração ao calcular o vetor Mediana.


#### Outros Algoritmos de Clusterização:
    
- Mean-Shift Clustering
- Density-Based Spatial Clustering of Applications with Noise (DBSCAN)
- Expectation–Maximization (EM) Clustering using Gaussian Mixture Models (GMM)
- Agglomerative Hierarchical Clustering


#### Métricas de Clusterização

Métrica: Número de observações
- O número de observações em cada cluster na partição final.

Interpretação:
- Examine o número de observações em cada cluster ao interpretar as medidas de variabilidade, como a distância média e a soma dos quadrados dentro do cluster. 
- A variabilidade de um cluster pode ser afetada por ter um número menor ou maior de observações. 
    - Por exemplo, a soma dos quadrados dentro do cluster se torna maior à medida que mais observações são adicionadas.
- Examine os clusters que possuem significativamente menos observações que outros clusters. 
- Clusters que têm poucas observações podem conter discrepâncias ou observações incomuns com características únicas.


Métrica: Soma de quadrados dentro do cluster (Within cluster sum of squares)
- A soma dos desvios ao quadrado de cada observação e do centróide do cluster.

Interpretação:
- A soma dos quadrados dentro do cluster é uma medida da variabilidade das observações dentro de cada cluster. 
- Em geral, um cluster que possui uma pequena soma de quadrados é mais compacto do que um cluster que possui uma grande soma de quadrados.
- Clusters com valores mais altos exibem maior variabilidade das observações dentro do cluster.
- No entanto, semelhante à soma dos quadrados e dos quadrados médios na ANOVA, a soma dos quadrados dentro do cluster é influenciada pelo número de observações. 
- À medida que o número de observações aumenta, a soma dos quadrados se torna maior. 
- Portanto, a soma dos quadrados dentro do cluster geralmente não é diretamente comparável entre os clusters com diferentes números de observações. 
- Para comparar a variabilidade dentro do cluster de diferentes clusters, use a distância média do centróide.


Métrica: Distância média do centróide
- A média das distâncias das observações ao centróide de cada cluster.

Interpretação:
- A distância média das observações ao centróide do cluster é uma medida da variabilidade das observações dentro de cada cluster. 
- Em geral, um cluster que possui uma distância média menor é mais compacto do que um cluster que tem uma distância média maior.
- Clusters com valores mais altos exibem maior variabilidade das observações dentro do cluster.

Métrica: Distância máxima do centróide
- O máximo das distâncias das observações ao centróide de cada cluster.

Interpretação:
- A distância máxima das observações ao centróide do cluster é uma medida da variabilidade das observações dentro de cada cluster. 
- Um valor máximo mais alto, especialmente em relação à distância média, indica uma observação no cluster que fica mais distante do centróide do cluster.


Métrica: Centróide do cluster
- O meio de um cluster. Um centróide é um vetor que contém um número para cada variável, e que cada número é a média de uma variável para as observações nesse cluster. 
- O centróide pode ser considerado a média multidimensional do cluster.

Interpretação:
- Use o centróide do cluster como uma medida geral da localização do cluster e para ajudar a interpretar cada cluster. 
- Cada centróide pode ser visto como representando a "observação média" dentro de um cluster em todas as variáveis da análise.


Métrica: Distâncias entre centróides de cluster
- As distâncias entre os centróides do cluster medem a distância entre os centróides dos clusters na partição final.

Interpretação:
- Embora os valores da distância não sejam muito informativos, você pode comparar as distâncias para ver quão diferentes os clusters são. 
- Uma distância maior geralmente indica uma diferença maior entre os clusters.

Referências:
Cluster Analysis
https://www-users.cs.umn.edu/~kumar001/dmbook/ch8.pdf





