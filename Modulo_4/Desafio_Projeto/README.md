# Projeto de Modelagem Dimensional para Análise de Dados dos Professores

## Descrição:
Este projeto teve como objetivo criar um esquema em estrela, conhecido como star schema, a partir de um diagrama relacional fornecido. O foco da modelagem foi a análise dos dados relacionados aos professores.

## Objetivo:
O objetivo principal foi construir um modelo dimensional que permitisse a análise multidimensional dos dados dos professores, cursos ministrados e departamentos.

## Tabela Fato:
A tabela fato é responsável por armazenar o contexto analisado, refletindo diversos dados sobre os professores, cursos ministrados e os departamentos aos quais estavam associados.

## Tabelas Dimensão:
Além da tabela fato, foram criadas tabelas dimensão que contém detalhes relacionados ao contexto. Essas tabelas incluem informações detalhadas sobre os professores, cursos e departamentos, permitindo uma análise mais granular e detalhada.

## Tabela Dimensão de Datas:
Para suportar análises temporais, foi adicionada uma tabela dimensão de datas. Como os dados de datas não estavam disponíveis no modelo relacional fornecido, foi necessário supor essas informações e criar os campos necessários para modelagem. Diferentes formatos e granularidades de datas foram utilizados para atender às necessidades analíticas do projeto.
