# SQL_Aprendizagem
📚 Documentação do meu Aprendizado em SQL - 🚀

## 1. Fundamentos do SQL

Cada linha representa um registro, e cada coluna representa um atributo. A criação de tabelas é realizada com o comando `CREATE TABLE`.

```sql
CREATE TABLE Clientes (
    ID INT PRIMARY KEY,
    Nome VARCHAR(50),
    Email VARCHAR(100)
);
```

## 2. Consultas e Manipulação de Dados

### 2.1 Consultas Simples
O comando `SELECT` é fundamental para realizar consultas e recuperar dados de uma tabela. Podemos recuperar todas as colunas da tabela Clientes usando:

```sql
SELECT * FROM Clientes;
```

### 2.2 Consultas com Condições (WHERE), Ordenação (ORDER BY) e Limitação (LIMIT)
- **WHERE:** Filtra registros com base em condições específicas.

  ```sql
  SELECT * FROM Clientes WHERE ID = 1;
  ```

- **ORDER BY:** Ordena os resultados com base em uma ou mais colunas.

  ```sql
  SELECT * FROM Clientes ORDER BY Nome ASC;
  ```

- **LIMIT:** Limita o número de registros retornados por uma consulta.

  ```sql
  SELECT * FROM Clientes LIMIT 10;
  ```

### 2.3 Inserção, Atualização e Exclusão de Dados
- **INSERT INTO:** Adiciona novos registros à tabela.

  ```sql
  INSERT INTO Clientes (Nome, Email) VALUES ('João', 'joao@email.com');
  ```

- **UPDATE:** Modifica registros existentes.

  ```sql
  UPDATE Clientes SET Email = 'novo@email.com' WHERE ID = 1;
  ```

- **DELETE FROM:** Remove registros da tabela.

  ```sql
  DELETE FROM Clientes WHERE ID = 1;
  ```

## 3. Estrutura do Banco de Dados

### 3.1 Criação de Tabelas (CREATE TABLE)
O comando `CREATE TABLE` é utilizado para criar novas tabelas, definindo os nomes das colunas e os tipos de dados.

```sql
CREATE TABLE Clientes (
    ID INT PRIMARY KEY,
    Nome VARCHAR(50),
    Email VARCHAR(100)
);
```

### 3.2 Modificação de Tabelas (ALTER TABLE)
O comando `ALTER TABLE` permite modificar a estrutura de tabelas existentes.

```sql
ALTER TABLE Clientes ADD Telefone VARCHAR(15);
```

### 3.3 Exclusão de Tabelas (DROP TABLE)
Para remover completamente uma tabela do banco de dados, utiliza-se o comando `DROP TABLE`.

```sql
DROP TABLE Clientes;
```

## 4. Consulta e Recuperação de Dados

### 4.1 Consultas Simples
Consultas simples envolvem a recuperação de registros ou colunas específicas sem a necessidade de dados desnecessários.

```sql
SELECT Nome, Email FROM Clientes;
```

### 4.2 Consultas com Condições (WHERE)
A cláusula `WHERE` filtra resultados com base em condições específicas.

```sql
SELECT * FROM Clientes WHERE ID = 1;
```

### 4.3 Consultas com Ordenação (ORDER BY)
A cláusula `ORDER BY` é usada para ordenar os resultados da consulta.

```sql
SELECT * FROM Clientes ORDER BY Nome ASC;
```

### 4.4 Consultas com Agrupamento (GROUP BY)
A cláusula `GROUP BY` agrupa registros com base nos valores de uma ou mais colunas.

```sql
SELECT Departamento, COUNT(*) FROM Funcionarios GROUP BY Departamento;
```

## 5. Relacionamentos em SQL

### 5.1 Chaves Primárias e Estrangeiras
Chaves primárias (`PRIMARY KEY`) garantem unicidade e identificação exclusiva de registros. Chaves estrangeiras (`FOREIGN KEY`) estabelecem relacionamentos entre tabelas.

```sql
CREATE TABLE Pedidos (
    ID INT PRIMARY KEY,
    ClienteID INT,
    Valor DECIMAL(10, 2),
    FOREIGN KEY (ClienteID) REFERENCES Clientes(ID)
);
```

### 5.2 JOINs - Combinando Dados de Múltiplas Tabelas
Operações JOIN combinam dados de diferentes tabelas com base em colunas relacionadas.

```sql
SELECT Clientes.Nome, Pedidos.Valor
FROM Clientes
INNER JOIN Pedidos ON Clientes.ID = Pedidos.ClienteID;
```

### 5.3 Subconsultas - Consultas Aninhadas
Subconsultas são consultas incorporadas dentro de outras consultas, permitindo operações mais complexas.

```sql
SELECT Nome
FROM Clientes
WHERE ID IN (SELECT ClienteID FROM Pedidos WHERE Valor > 1000);
```

## 6. Restrições e Integridade de Dados

### 6.1 Definição de Restrições
Restrições são regras aplicadas a tabelas para garantir a integridade dos dados.

```sql
CREATE TABLE Produtos (
    ID INT PRIMARY KEY,
    Nome VARCHAR(50
