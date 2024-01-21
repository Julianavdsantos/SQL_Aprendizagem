# SQL_Aprendizagem
"📚 Documentação de Aprendizado em SQL - Nível Básico a Intermediário 🚀


Sumário 
1 Introdução ao SQL
1.1 Definição e Origens
1.2 Características Principais
1.3 Componentes Básicos


 Cada linha representa um registro e cada coluna representa um atributo.
A criação de tabelas é realizada com o comando  CREATE TABLE.

CREATE TABLE Clientes (
    ID INT PRIMARY KEY,
    Nome VARCHAR(50),
    Email VARCHAR(100)
);


Consultas(Queries)

As consultas são utilizadas para recuperar dados de uma ou mais tabelas. A cláusula SELECT é fundamental para construir consultas eficientes.

ELECT * FROM Clientes;


Esta consulta retorna todas as colunas (*) da tabela Clientes. Podemos também especificar colunas específicas, como:


SELECT Nome, Email FROM Clientes;

CREATE TABLE: Cria uma nova tabela.
ALTER TABLE: Modifica a estrutura de uma tabela existente.
DROP TABLE: Exclui uma tabela.



ALTER TABLE Clientes
ADD Telefone VARCHAR(15);


Comandos DML (Data Manipulation Language)
Comandos DML são usados para manipular dados armazenados em tabelas. Alguns dos principais comandos incluem:

* INSERT INTO: Adiciona novos registros a uma tabela.
* UPDATE: Modifica registros existentes em uma tabela.
* DELETE FROM: Remove registros de uma tabela.






