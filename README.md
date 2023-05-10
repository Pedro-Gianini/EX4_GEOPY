## Solução dos exercícios da quarta aula do curso GeoPY
## OSM, análise de vizinhança e reclassificação de dados

Bibliotecas usadas: gdal-bin python-gdal python3-gdal ; python3-rtree ; geopandas==0.10.0 ; descartes ; os ; pandas ; matplotlib.pyplot ; re ; contextily ; mapclassify

Funções aprendidas: camin=''; os.chdir(''); tight_layout() ; re.findall ; .rename ; .dissolve('') ; .set_index ; .groupby ; .listdir() ; .startswith('') ; 

Conteúdos abordados/ explicação dos exercícios : 
# Exercício 1 #
A atividade consiste em analisar a acessibilidade de oito shoppings na cidade de Helsinque, com o objetivo de definir as áreas de dominância para cada um deles e descobrir quantas pessoas vivem nessas áreas. O primeiro passo é ler os arquivos de dados travel_time com a biblioteca Pandas e selecionar as colunas pt_r_tt (tempo de transporte público), car_r_t (tempo de carro), from_id (id da célula de origem) e to_id (id da célula de destino). Em seguida, os tempos de viagem classificados são visualizados usando os métodos de classificação aprendidos na aula. Para isso, é usada a biblioteca Geopandas para manipular dados vetoriais e o grid de polígonos com as zonas de transporte é lido. Depois, é feito um join (merge) entre as geometrias do grid e as informações sobre tempo de viagem do arquivo txt. Por fim, são removidas as linhas com no data (-1), ou seja, sem informação sobre o tempo de viagem por transporte público.

# Exercício 2 #
O código é uma implementação de um script Python que visa a definir a área de influência para cada um dos shopping centers com base no tempo de viagem de carro. O código é dividido em várias etapas:
Iterar sobre os arquivos de acessibilidade um por um e renomear as colunas de tempo de viagem para que possam ser identificadas para cada shopping;
Juntar as colunas que indicam o tempo de viagem para cada shopping ao shapefile em MetropAccess_YKR_grid_EurefFIN.shp onde YKR_ID na grade corresponde a from_id no arquivo de dados de tempo de viagem. No final, você deve ter um GeoDataFrame com diferentes colunas mostrando os tempos de viagem para diferentes shopping centers;
Para cada linha, descobrir o valor mínimo de todas as colunas XXX_car_r_tt e inserir esse valor em uma nova coluna chamada min_car;
Para cada linha, descobrir o nome do shopping mais próximo e inserir esse valor em uma nova coluna chamada influência.

O código utiliza a biblioteca Pandas para ler, manipular e salvar arquivos de dados em formato CSV. Além disso, utiliza a biblioteca GeoPandas para ler e manipular dados geoespaciais. O código também utiliza a biblioteca re para manipular padrões em textos. As operações realizadas no código incluem leitura de arquivos, seleção de colunas, renomeação de colunas, junção de tabelas, cálculo de valores mínimos e iteração sobre linhas de um GeoDataFrame.
