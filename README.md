# **Dashboard para acompanhamento de empresa de marketplace de locação de imóveis para curta e longa temporada**

### Resumo

Análise dos dados do Airbnb de Nova Yorque com foco em avaliação da disponibilidade de imóveis na plataforma. Estima-se que a empresa deixou de arrecadar entre 8,42 e 273,61 milhões de dólares de receita bruta devido à indisponibilidade de imóveis, o que significa um aumento potencial na receita entre 31 e 39% caso os imóveis sejam disponibilizados novamente.

[Relatório - Análise da disponibilidade de imóveis e potencial de receita](https://app.powerbi.com/view?r=eyJrIjoiNjYxMTE4ZDctOTNmZC00MWU0LWI0MjItZjVlNGE5ZjIzMzM5IiwidCI6ImUyZjc3ZDAwLTAxNjMtNGNmNi05MmIwLTQ4NGJhZmY5ZGY3ZCJ9&pageName=ReportSectiond2b2e8909b25e91c4067).

[Texto no Medium sobre minha experiência realizando este projeto](https://medium.com/@luisamuzzi/desenvolvendo-um-projeto-de-dataviz-com-o-power-bi-minha-experi%C3%AAncia-8309f2b14f9c)

Leia mais sobre o projeto abaixo.

### Índice
* [1. Problema de negócio](https://github.com/luisamuzzi/marketplace_imoveis_dashboards?tab=readme-ov-file#1-problema-de-neg%C3%B3cio)
* [2. Premissas assumidas para a análise](https://github.com/luisamuzzi/marketplace_imoveis_dashboards?tab=readme-ov-file#2-premissas-assumidas-para-a-an%C3%A1lise)
* [3. Estratégias de solução](https://github.com/luisamuzzi/marketplace_imoveis_dashboards?tab=readme-ov-file#3-estrat%C3%A9gias-de-solu%C3%A7%C3%A3o)
* [4. O produto final do projeto](https://github.com/luisamuzzi/marketplace_imoveis_dashboards?tab=readme-ov-file#4-o-produto-final-do-projeto)
* [5. Principais insights de dados](https://github.com/luisamuzzi/marketplace_imoveis_dashboards?tab=readme-ov-file#5-principais-insights-de-dados)
* [6. Conclusão](https://github.com/luisamuzzi/marketplace_imoveis_dashboards?tab=readme-ov-file#6-conclus%C3%A3o)
* [7. Próximos passos](https://github.com/luisamuzzi/marketplace_imoveis_dashboards?tab=readme-ov-file#7-pr%C3%B3ximos-passos)

### 1. Problema de negócio

Uma empresa de marketplace de locação de imóveis para curta e longa temporada conecta pessoas que possuem imóveis para locação a hospedes.

A empresa coletou dados referentes aos imóveis cadastrados em seu site para a cidade de New York. Os dados coletados incluem o id dos imóveis, a data da última avaliação recebida, a região e o bairro de localização do imóvel (incluindo latitude e longitude), o preço por noite, o mínimo de noites de hospedagem e a quantidade de dias em que o imóvel está disponível no ano.

O time de negócios deseja avaliar a disponibilidade de imóveis na plataforma para estimar como a indisponibilidade está afetando o potencial de receita bruta da empresa. Entende-se como indisponibilidade quando o proprietário do imóvel declara que o imóvel está disponível por 0 (zero) dia ao ano.

Nesse contexto, o objetivo desse projeto é criar um relatório contendo dois dashboards utilizando o Power BI. Cada dashboard conterá indicadores e gráficos que permitirão ao negócio retirar insights sobre a situação da empresa.

### 2. Premissas assumidas para a análise

1. A análise foi realizada com dados entre 28/03/2011 e 08/07/2019;
2. Marketplace foi o modelo de negócio assumido;
3. Um imóvel está indisponível quando o proprietário do imóvel declara que o imóvel está disponível por 0 (zero) dia ao ano;
4. Um imóvel que consta como indisponível ainda não foi excluído da base, ou seja, o dono do imóvel ainda pode retornar à atividade;
5. Os dados utilizados se encontram em:  https://www.kaggle.com/datasets/dgomonov/new-york-city-airbnb-open-data

### 3. Estratégias de solução

O relatório foi desenvolvido considerando-se técnicas de ETL, análise exploratória de dados e recursos de visualização de dados (como gráficos, mapas, segmentações), além do contexto do negócio analisado.

A estratégia adotada seguiu as seguintes etapas:

1. Exploração dos dados:
    1. Carregar o conjunto de dados em um ambiente de análise (Excel);
    2. Análise exploratória dos dados para identificar a distribuição de features e padrões nos dados, e identificar outliers.
2. ETL no Power Query:
    1. Identificar e tratar dados ausentes ou inconsistentes;
    2. Verificar a classificação dos tipos de dados;
    3. Criação da tabela calendário para análises de inteligência temporal.
3. Visualização de Dados:
    1. Criar gráficos e outras visualizações para apresentar os dados de maneira clara e acessível.
4. Análise Temporal:
    1. Explorar tendências temporais na disponibilidade dos imóveis.
5. Insights estratégicos:
    1. Com base nas análises, verificar os principais insights que podem contribuir para o crescimento do negócio.

### 4. O produto final do projeto

Dashboards no Power BI com filtros de seleção (ano e mês, região, preço do imóvel por noite e disponibilidade anual do imóvel em dias), botão para a limpeza de segmentações, botões de navegação entre tela inicial e dashboards.

O relatório pode ser visualizado por meio do link: [Relatório - Análise da disponibilidade de imóveis e potencial de receita](https://app.powerbi.com/view?r=eyJrIjoiNjYxMTE4ZDctOTNmZC00MWU0LWI0MjItZjVlNGE5ZjIzMzM5IiwidCI6ImUyZjc3ZDAwLTAxNjMtNGNmNi05MmIwLTQ4NGJhZmY5ZGY3ZCJ9&pageName=ReportSectiond2b2e8909b25e91c4067).

1. Dashboard Disponibilidade de Imóveis:
    1. Cartões:
        1. Número total de imóveis cadastrados na base de dados;
        2. Número de imóveis disponíveis (disponibilidade diferente de 0 dia) 
        3. Taxa de disponibilidade (imóveis disponíveis/imóveis cadastrados). Ao todo, há uma disponibilidade de 67,27% em New York, ou seja, mais de 30% dos imóveis cadastrados se encontram indisponíveis para locação.
    2. Gráficos:
        1. Imóveis cadastrados por região e imóveis indisponíveis por região: Manhattan e Brooklyn são as regiões com o maior número de imóveis (cadastrados, disponíveis e indisponíveis). Também é possível verificar a disponibilidade de imóveis por cada bairro das regiões;
        2. Disponibilidade por região: A região com a maior média de dias disponíveis para locação é Staten Island, essa também é a região com o menor número de imóveis disponíveis. Essa tendência de “inversão” entre a média de disponibilidade de dias e o número de imóveis disponíveis também está presente nos dados das outras regiões.
        3. Disponibilidade por tipo de quarto: Comportamento semelhante ao gráfico anterior. O tipo de quarto com a maior média de dias disponíveis para locação é o tipo compartilhado, possuindo também o menor número de imóveis disponíveis.
        4. Número de imóveis por ano: Considerou-se os anos de 2015 a 2019 devido a maior consistência dos dados. Observa-se que o número de imóveis disponíveis e cadastrados aumentou de forma similar no período analisado, apresentando um pico em 2019.
        5. Número de imóveis por meses dos ano: observa-se um pico de imóveis disponíveis e cadastrados que receberam a última avaliação nos meses de junho. Esse mês também possui a maior taxa de disponibilidade (88,17%).
        6. Taxa de disponibilidade por ano: Considerou-se os anos de 2016 a 2019 devido a maior consistência dos dados. Observa-se um aumento da taxa de disponibilidade de imóveis ao longo dos anos. Saindo de 14,19% em 2016 e alcançando 87,73% em 2019.

2. Dashboard de Preço dos imóveis e potencial de receita:

1. Cartões:
    1. Preço médio de todos os imóveis cadastrados na base;
    2. Receita potencial mínima dos imóveis disponíveis (considerando que o imóvel é alugado pelo mínimo de noites exigido pelo anfitrião);
    3. Receita potencial dos imóveis disponíveis (considerando que o imóvel seja alugado por toda a disponibilidade anual declarada pelo anfitrião);
    4. Receita potencial mínima dos imóveis indisponíveis (considerando que o imóvel é alugado pelo mínimo de noites exigido pelo anfitrião);
    5. Receita potencial média dos imóveis indisponíveis (considerando que o imóvel é alugado pela média de dias disponíveis dos imóveis da base de dados).
2. Gráficos:
    1. Mapa da distribuição dos imóveis cadastrados;
    2. Distribuição do preço médio por mínimo de noites de aluguel: a maioria dos imóveis está disponível por um baixo número mínimo de noites e um baixo preço (abaixo de 100 dólares);
    3. Preço médio por região: Manhattan é a região mais cara, equanto o Bronxs é a mais barata;
    4. Preço médio por tipo de acomodação: o preço dos quartos segue uma ordenação lógica (a maior média de preço é dos alugueis de casas completas e a menor dos alugueis de quartos compartilhados).
    

### 5. Principais insights de dados

1. A taxa de disponibilidade dos imóveis da base de dados indica que um total de mais de 30% dos imóveis se encontra indisponível. Alguns desses imóveis se encontram indisponíveis há anos. No entanto, a taxa de disponibilidade anual demonstrou crescimento; em 2019, havia pouco mais de 10% de imóveis indisponíveis naquele ano.
2. O mês de junho (verão e férias escolares nos Estados Unidos) é o mês onde a maior quantidade de imóveis recebeu sua última avaliação registrada.
3. Estima-se uma margem entre aproximadamente 8,42 e 273,61 milhões de dólares em potencial de receita bruta que não está sendo angariado devido à indisponibilidade  de imóveis. Isso significa um aumento potencial na receita entre 31 e 39% caso os imóveis sejam disponibilizados novamente.

### 6. Conclusão

O objetivo desse projeto foi criar um conjunto de dashboards que permitissem ao time de negócios visualizar e entender a situação do negócio em relação à situação analisada, bem como tomar decisões a partir dos dados.

As principais conclusões sugerem que:

- É preciso investigar o que está levando anfitriões a deixarem seus imóveis indisponíveis, já que há um grande potencial de receita bruta que não está sendo explorado pela empresa.
- No mês de junho acontece um pico nas avaliações, indicando que é um mês com muitas locações. Ações específicas voltadas para clientes tirando férias podem ser adotadas.

### 7. Próximos passos

1. Reduzir o número de métricas após alinhamento com o time de negócios;
2. Obter mais informações para investigar o motivo dos imóveis indisponíveis estarem com esse status, por exemplo:
    1. Nota média de avaliações do imóvel
    2. Nota da última avaliação recebida
    3. Número de hospedagens recebidas pelo imóvel
