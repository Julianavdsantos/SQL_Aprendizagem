# SQL_Aprendizagem
"📚 Documentação de Aprendizado em SQL - Nível Básico a Intermediário 🚀


 
     


1 Cada linha representa um registro e cada coluna representa um atributo.
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

Como inserir um nono cliente:

INSERT INTO Clientes (Nome, Email, Telefone)
VALUES ('João Silva', 'joao@email.com', '(11) 1234-5678');


Restrições:
Restrições são regras aplicadas às tabelas para garantir a integridade dos dados. Algumas das principais restrições incluem:

* PRIMARY KEY: Garante que a coluna é única e não nula, geralmente usada para identificar exclusivamente cada registro.
* FOREIGN KEY: Estabelece uma relação entre duas tabelas, garantindo a integridade referencial.
Exemplo de criação de uma tabela com uma chave primária:


CREATE TABLE Pedidos (
    ID INT PRIMARY KEY,
    ClienteID INT,
    Valor DECIMAL(10, 2),
    FOREIGN KEY (ClienteID) REFERENCES Clientes(ID)
);


### 2.1 SELECT e FROM

O comando SELECT é utilizado para realizar consultas e recuperar dados de uma tabela. Em conjunto com a cláusula FROM, especificamos a tabela da qual desejamos obter dados. Por exemplo:

```sql
SELECT Nome, Email FROM Clientes;
```

Essa consulta retorna as colunas Nome e Email da tabela Clientes.

### 2.2 WHERE, ORDER BY e LIMIT

- **WHERE:** Utilizado para filtrar registros com base em condições específicas. Por exemplo, para recuperar apenas clientes com ID igual a 1:

  ```sql
  SELECT * FROM Clientes WHERE ID = 1;
  ```

- **ORDER BY:** Ordena os resultados com base em uma ou mais colunas, podendo ser em ordem ascendente (ASC) ou descendente (DESC):

  ```sql
  SELECT * FROM Clientes ORDER BY Nome ASC;
  ```

- **LIMIT:** Limita o número de registros retornados por uma consulta:

  ```sql
  SELECT * FROM Clientes LIMIT 10;
  ```

### 2.3 Inserção de Dados (INSERT)

O comando INSERT INTO é utilizado para adicionar novos registros a uma tabela. Por exemplo, para adicionar um novo cliente à tabela Clientes:

```sql
INSERT INTO Clientes (Nome, Email) VALUES ('João', 'joao@email.com');
```

### 2.4 Atualização de Dados (UPDATE)

O comando UPDATE é utilizado para modificar dados existentes em uma tabela. Por exemplo, para alterar o email do cliente com ID igual a 1:

```sql
UPDATE Clientes SET Email = 'novo@email.com' WHERE ID = 1;
```

### 2.5 Exclusão de Dados (DELETE)

O comando DELETE FROM é utilizado para remover registros de uma tabela com base em condições. Por exemplo, para excluir um cliente com ID igual a 1:

```sql
DELETE FROM Clientes WHERE ID = 1;
```

Estes são comandos fundamentais que permitem realizar operações de consulta, inserção, atualização e exclusão de dados em um banco de dados usando SQL.



## 3. Estrutura do Banco de Dados

### 3.1 Criação de Tabelas (CREATE TABLE)
Na criação de um banco de dados, a estrutura inicial é definida pelas tabelas. O comando `CREATE TABLE` é utilizado para criar uma nova tabela, especificando os nomes das colunas e os tipos de dados que elas conterão. Isso estabelece a base para armazenar e organizar informações de maneira estruturada.

Exemplo:
```sql
CREATE TABLE Clientes (
    ID INT PRIMARY KEY,
    Nome VARCHAR(50),
    Email VARCHAR(100)
);
```

### 3.2 Modificação de Tabelas (ALTER TABLE)
À medida que as necessidades do banco de dados evoluem, é comum realizar modificações na estrutura das tabelas. O comando `ALTER TABLE` é utilizado para adicionar, modificar ou excluir colunas de uma tabela existente, proporcionando flexibilidade na adaptação do esquema às demandas do sistema.

Exemplo:
```sql
ALTER TABLE Clientes
ADD Telefone VARCHAR(15);
```

### 3.3 Exclusão de Tabelas (DROP TABLE)
Quando uma tabela não é mais necessária, o comando `DROP TABLE` é utilizado para removê-la completamente do banco de dados. Essa ação é irreversível e deve ser realizada com cuidado, garantindo que dados importantes não sejam perdidos acidentalmente.

Exemplo:
```sql
DROP TABLE Clientes;
```

## 4. Consulta e Recuperação de Dados

### 4.1 Consultas Simples
Consultas simples envolvem a recuperação de todos os registros ou colunas específicas de uma tabela. O comando `SELECT` é fundamental nesse contexto, permitindo a obtenção de dados específicos sem a necessidade de recuperar informações desnecessárias.

Exemplo:
```sql
SELECT Nome, Email FROM Clientes;
```

### 4.2 Consultas com Condições (WHERE)
A cláusula `WHERE` é utilizada para filtrar os resultados de uma consulta com base em condições específicas. Isso permite a recuperação seletiva de registros que atendam a critérios predefinidos.

Exemplo:
```sql
SELECT * FROM Clientes WHERE ID = 1;
```

### 4.3 Consultas com Ordenação (ORDER BY)
A cláusula `ORDER BY` é empregada para ordenar os resultados da consulta com base em uma ou mais colunas, seja em ordem ascendente (ASC) ou descendente (DESC).

Exemplo:
```sql
SELECT * FROM Clientes ORDER BY Nome ASC;
```

### 4.4 Consultas com Agrupamento (GROUP BY)
A cláusula `GROUP BY` é utilizada para agrupar registros com base nos valores de uma ou mais colunas. Isso é frequentemente combinado com funções de agregação, como SUM, COUNT, AVG, etc.

Exemplo:
```sql
SELECT Departamento, COUNT(*) FROM Funcionarios GROUP BY Departamento;
```

## 5. Relacionamentos em SQL

### 5.1 Chaves Primárias e Estrangeiras
Chaves primárias (PRIMARY KEY) garantem unicidade e identificação exclusiva de registros em uma tabela. Chaves estrangeiras (FOREIGN KEY) estabelecem relacionamentos entre tabelas, assegurando a integridade referencial entre elas.

Exemplo:
```sql
CREATE TABLE Pedidos (
    ID INT PRIMARY KEY,
    ClienteID INT,
    Valor DECIMAL(10, 2),
    FOREIGN KEY (ClienteID) REFERENCES Clientes(ID)
);
```

### 5.2 JOINs - Combinando Dados de Múltiplas Tabelas
Operações JOIN são utilizadas para combinar dados de diferentes tabelas com base em colunas relacionadas. Os tipos comuns de JOIN incluem INNER JOIN, LEFT JOIN, RIGHT JOIN e FULL JOIN.

Exemplo:
```sql
SELECT Clientes.Nome, Pedidos.Valor
FROM Clientes
INNER JOIN Pedidos ON Clientes.ID = Pedidos.ClienteID;
```

### 5.3 Subconsultas - Consultas Aninhadas
Subconsultas são consultas incorporadas dentro de outras consultas. Elas podem ser usadas para realizar operações mais complexas, fornecendo resultados que são utilizados como critérios em consultas externas.

Exemplo:
```sql
SELECT Nome
FROM Clientes
WHERE ID IN (SELECT ClienteID FROM Pedidos WHERE Valor > 1000);
```

## 6. Restrições e Integridade de Dados

### 6.1 Definição de Restrições
Restrições são regras aplicadas a tabelas para garantir a integridade dos dados. Isso inclui a definição de chaves primárias, chaves estrangeiras, restrições UNIQUE, CHECK, etc.

Exemplo:
```sql
CREATE TABLE Produtos (
    ID INT PRIMARY KEY,
    Nome VARCHAR(50) UNIQUE,
    Estoque INT CHECK (Estoque >= 0)
);
```

### 6.2 Garantindo a Integridade Referencial
A integridade referencial é assegurada pela utilização de chaves estrangeiras. Isso significa que não é possível ter valores na chave estrangeira que não correspondam a valores na chave primária da tabela relacionada.

Exemplo:
```sql
CREATE TABLE Pedidos (
    ID INT PRIMARY KEY,
    ClienteID INT,
    Valor DECIMAL(10, 2),
    FOREIGN KEY (ClienteID) REFERENCES Clientes(ID)
);
```

## 7. Projetos Práticos

### 7.1 Desenvolvimento de um Sistema Simples
Projetos práticos envolvem a aplicação dos conceitos aprendidos na criação de sistemas reais. Desenvolver um sistema simples




