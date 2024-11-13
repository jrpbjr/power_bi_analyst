# Projeto de Modelagem de Dados
Este projeto visa criar um modelo de dados baseado em star schema a partir da tabela única de Financial Sample. O modelo resultante será utilizado para análise e geração de relatórios sobre as vendas.

## Estrutura do Projeto
O projeto encontra-se dentro da pasta Projeto_2 da seguinte forma:

- **Modelo.xlsx**: Arquivo original contendo as informações para a elaboração do projeto.
- **Imagem**: Imagem relacionada ao projeto final.
- **Modelo.pbix**: Arquivo principal do Power BI contendo o modelo de dados final.

## Imagem do projeto finalizado:
![projeto_starschema_tbvendas](https://github.com/alexlaudiano/power_bi_analyst/blob/main/Modulo_4/Desafio_Projeto/Projeto_2/starschema_vendas.png)

## Processo de Construção do Diagrama
O processo de construção do diagrama seguiu as seguintes etapas:
- **Análise dos Dados**: Iniciamos analisando a estrutura e os tipos de dados presentes na tabela original de Financial Sample.
- **Criação das Tabelas Dimensão e Fato**: Utilizamos consultas e transformações de dados para criar as tabelas dimensão e fato do modelo baseado em star schema.
- **Seleção de Colunas**: Selecionamos as colunas relevantes da tabela original para compor cada tabela dimensão e fato, garantindo a integridade e consistência dos dados.
- **Modelagem do Esquema em Estrela**: Utilizamos o Power BI para modelar o esquema em estrela, relacionando as tabelas dimensão à tabela fato através de chaves primárias e estrangeiras.
- **Criação da Dimensão de Calendário**: Utilizamos a função DAX calendar() para criar a dimensão de calendário, permitindo análises temporais das vendas.

## Funcionalidades e Funções DAX Utilizadas
Durante o processo de construção do modelo, utilizamos funcionalidades e funções DAX para realizar transformações e cálculos nos dados. Alguns exemplos incluem:

- Este código DAX cria uma tabela de calendário chamada d_Calendario.
```
d_Calendario = 
var dataminima = DATE(YEAR(MIN(f_Vendas[Date])),1,1)
var datamaxima = DATE(YEAR(MAX(f_Vendas[Date])),12,31)
return
CALENDAR(dataminima, datamaxima)
```
Vamos analisar cada parte:

1.`var dataminima = DATE(YEAR(MIN(f_Vendas[Date])),1,1)`: Esta linha define uma variável chamada **dataminima**. Ela utiliza a função MIN para encontrar a data mínima presente na coluna [Date] da tabela f_Vendas. Em seguida, a função YEAR extrai o ano dessa data mínima. A função DATE então cria uma nova data no primeiro dia do ano encontrado, ou seja, em 1 de janeiro, utilizando o ano extraído e o mês e o dia especificados manualmente como 1.

2.`var datamaxima = DATE(YEAR(MAX(f_Vendas[Date])),12,31)`: Similar à linha anterior, esta define uma variável chamada **datamaxima**. No entanto, ela utiliza a função MAX para encontrar a data máxima na coluna [Date] da tabela f_Vendas. Em seguida, a função YEAR extrai o ano dessa data máxima. A função DATE então cria uma nova data no último dia do ano encontrado, ou seja, em 31 de dezembro, utilizando o ano extraído e o mês e o dia especificados manualmente como 12.

3.`return CALENDAR(dataminima, datamaxima)`: Esta linha cria a tabela de calendário propriamente dita, utilizando a função CALENDAR. Esta função gera uma tabela com todas as datas dentro do intervalo especificado (de dataminima a datamaxima). Essa tabela é retornada como resultado da expressão DAX.

- Esse código DAX cria uma medida chamada "Ano" que extrai o ano da coluna "Data" da tabela de calendário "d_Calendario".
```
Ano = YEAR(d_Calendario[Data])
```
Vamos analisar a expressão:

1.`d_Calendario[Data]`: Esta parte da expressão refere-se à coluna "Data" da tabela de calendário "d_Calendario". Isso significa que estamos acessando a coluna que contém as datas na tabela de calendário.

2.`YEAR(...)`: Esta função DAX extrai o ano de uma data. Neste caso, ela está sendo aplicada à coluna "Data" da tabela de calendário para extrair o ano de cada data presente nessa coluna.

Portanto, o resultado dessa medida será uma lista de anos correspondentes às datas presentes na coluna "Data" da tabela de calendário. Essa medida pode ser utilizada para análises e visualizações que envolvam agrupamento ou filtro por ano.

- Esse código DAX cria uma medida chamada "Mês" que extrai o número do mês da coluna "MonthNo" da tabela de calendário "d_Calendario"
```
Mês = d_Calendario[Data].[MonthNo]
```
Vamos analisar a expressão:

1.`d_Calendario[Data].[MonthNo]`: Esta parte da expressão refere-se à coluna "MonthNo" da tabela de calendário "d_Calendario". Esta coluna contém o número do mês para cada data na tabela de calendário.

Portanto, o resultado dessa medida será uma lista de números representando o mês para cada data presente na coluna "Data" da tabela de calendário. Essa medida pode ser utilizada para análises e visualizações que envolvam agrupamento ou filtro por mês.

- Esse código DAX cria uma medida chamada "Nome_Mês" que extrai o nome do mês da coluna "Mês" da tabela de calendário "d_Calendario"
```
Nome_Mês = d_Calendario[Data].[Mês]
```
Vamos analisar a expressão:

1.`d_Calendario[Data].[Mês]`: Esta parte da expressão refere-se à coluna "Mês" da tabela de calendário "d_Calendario". Esta coluna contém o nome do mês para cada data na tabela de calendário.

Portanto, o resultado dessa medida será uma lista de nomes de meses correspondentes às datas presentes na coluna "Data" da tabela de calendário. Essa medida pode ser utilizada para análises e visualizações que envolvam o nome do mês.

## Resultados
O modelo de dados final está disponível no arquivo starschema_tbvendas.pbix e pode ser explorado utilizando o Power BI. O esquema em estrela resultante permite análises flexíveis e eficientes das vendas, fornecendo insights valiosos para a tomada de decisões.
