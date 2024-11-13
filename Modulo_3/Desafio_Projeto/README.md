# Processamento de Dados Simplificado com Power BI
Este repositório contém os arquivos e instruções relacionados ao desafio do módulo 3, "Processamento de Dados Simplificado com Power BI". O desafio consiste em realizar diversas etapas de processamento e transformação de dados utilizando o Power BI, Azure e MySQL.

## Etapas Realizadas
As seguintes etapas foram realizadas com sucesso durante o desafio:

1. Criação de uma instância na Azure para MySQL.
2. Criação do banco de dados com base nos dados disponíveis no GitHub.
3. Integração do Power BI com o MySQL na Azure.
4. Verificação de problemas na base de dados a fim de realizar a transformação dos dados.

## Diretrizes para Transformação dos Dados
1. Verificação dos cabeçalhos e tipos de dados.
2. Modificação dos valores monetários para o tipo de precisão dupla.
3. Verificação da existência de nulos e análise da remoção.
4. Identificação dos funcionários sem gerente.
5. Identificação de departamentos sem gerente.
6. Preenchimento de lacunas nos departamentos sem gerente.
7. Verificação do número de horas dos projetos.
8. Separação de colunas complexas.
9. Mescla de consultas employee e department para criar uma tabela employee com os nomes dos departamentos associados aos colaboradores.
10. Eliminação de colunas desnecessárias.
11. Junção dos colaboradores e respectivos nomes dos gerentes.
12. Mescla das colunas de Nome e Sobrenome para ter apenas uma coluna definindo os nomes dos colaboradores.
13. Mescla dos nomes de departamentos e localização.
14. Explicação sobre a utilização da mescla em vez do atributo em um caso específico.
15. Agrupamento dos dados para saber quantos colaboradores existem por gerente.
16. Eliminação das colunas desnecessárias de cada tabela.

## O que é mesclar consulta no Power Query?
É a combinação de duas consultas com base em uma coluna comum, semelhante a uma operação de junção em bancos de dados. Você pode criar uma única tabela combinando informações de duas tabelas diferentes.

## O que é acrescentar consulta no Power Query?
Simplesmente adicionar os resultados de uma consulta ao final de outra consulta, sem combinar os dados com base em uma chave específica.

Em resumo, "Mesclar Consultas" é útil quando você precisa combinar dados com base em uma chave comum, enquanto "Acrescentar Consultas" é útil quando deseja simplesmente adicionar os resultados de uma consulta ao final de outra consulta.

## Mesclar Consulta vs. Acrescentar Consulta no Power Query: Tabela Comparativa

| Funcionalidade | Descrição | Tipo de Junção | Cenários de Uso |
|---|---|---|---|
| **Mesclar Consultas** | Combina dados de duas consultas com base em colunas correspondentes. | Interna, externa esquerda, externa direita, cruzada | Tabelas relacionadas, dados com colunas em comum |
| **Acrescentar Consultas** | Combina dados de várias consultas, uma após a outra, em uma única consulta. | Sem junção | Tabelas sem colunas em comum, dados de diferentes períodos/categorias |

## Instruções de Uso
Para reproduzir ou entender melhor as etapas realizadas, siga as instruções contidas nos arquivos deste repositório.
