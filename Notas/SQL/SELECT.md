O comando `SELECT` é usado para **selecionar dados** de um banco de dados. Os dados retornados são salvos em uma tabela-resultado, chamada **result-set**.
## Sintaxe
```SQL
SELECT Coluna1, Coluna2, ...
FROM Tabela;
```

Essa seleção retorna nomes de campos da tabela. Para selecionar todos de uma vez só, usamos a seguinte sintaxe:
```SQL
SELECT * FROM Tabela; 
```
# SELECT DISTINCT
O comando `SELECT DISTINCT` é usado para retornar somente valores estritamente diferentes. Exemplo:
```SQL
SELECT DISTINCT Coluna1, Coluna2, ...
FROM Tabela
```
## Contagem de valores distintos
O comando SQL a seguir conta e retorna o número de valores diferentes em uma tabela:
```SQL
SELECT COUNT(DISTINCT Country) FROM Customers;
```

![[Pasted image 20240509163735.png]]

# WHERE Clause
A cláusula `WHERE` é usada para **filtrar a seleção de dados**. É utilizada para **extrair somente dados** que atendem à uma **condição específica**. Exemplo:
```SQL
SELECT Coluna1, Coluna2, ...
FROM Tabela
WHERE Condicao;
```
Obs.: A cláusula `WHERE` também é usada nos comandos `UPDATE`, `DELETE`, etc.
## Exemplo
### Testar para um valor do tipo `string`
```SQL
SELECT * FROM Tabela
WHERE Pais = 'Brasil';
```
### Testar para um valor numérico
```SQL
SELECT * FROM Tabela
WHERE ClienteId = 1;
```
# LIMIT Clause
A cláusula `LIMIT` é utilizada para **especificar o números de registros** a serem retornados. É útil para quando estamos lidando com uma **tabela muito grande**, e o número de registros pode afetar a **performance**.
## Exemplo

Selecionar os 3 primeiros registros de uma tabela:
```SQL
SELECT * FROM Customers  
LIMIT 3;
```

Selecionar os 3 primeiros registros a partir do 3º **(não incluso)**:
```SQL
SELECT * FROM Customers  
LIMIT 3 OFFSET 3;
```

Selecionar os 3 primeiros registros junto com uma cláusula `WHERE`:
```SQL
SELECT * FROM Customers  
WHERE Country='Germany'  
LIMIT 3;
```
# Operadores
Os seguintes operadores podem ser utilizados em uma cláusula `WHERE`:
- `=` Equal
- `>` Greater than
- `<` Less than
- `>=` Greater than or equal
- `<=` Less than or equal
- `<>` Not equal. **Nota:** Em algumas versões do SQL, esse operador será `!=`
- [`BETWEEN`](BETWEEN.md) Between certain range. Ex.: `WHERE Price BETWEEN 50 AND 60`
- [`LIKE`](LIKE.md) Search for a pattern. Ex.: `WHERE City LIKE 's%'`
- [`IN`](IN.md) To specify multiple possible values for a column `WHERE City IN ('Paris','London')`
- [`AND,OR,NOT`](AND,OR,NOT.md)

# ORDER BY
O termo-chave `ORDER BY` é usado para **ordernar uma tabela-resultado** em ordem **ascendente ou descendente**. Uma tabela-resultado é ordenada de forma **ascendente por padrão**; para ordená-la de outra forma, utilizamos o termo `DESC`.

Sintaxe - ordem ascendente, por padrão
```SQL
SELECT * FROM Customers  
ORDER BY Country;
```

Sintaxe - ordem descendente
```SQL
SELECT * FROM Customers  
ORDER BY Country DESC;
```
## Ordenar por mais de uma coluna

Ordena primeiramente pela coluna "Country", e se duas linhas tiverem o mesmo valor, ordena em seguida por "CustomerName"
```SQL
SELECT * FROM Customers  
ORDER BY Country, CustomerName;
```

Ordena pela primeira coluna de forma ascendente, e pela segunda de forma descendente
```SQL
SELECT * FROM Customers  
ORDER BY Country ASC, CustomerName DESC;
```

# MIN() and MAX() Functions
A função `MIN()` retorna o menor valor da coluna selecionada.
A função `MAX()` retorna o maior valor da coluna selecioanda.

Exemplo `MIN()`
```SQL
SELECT MIN(Price) AS SmallestPrice  
FROM Products;
```

Exemplo `MAX()`
```SQL
SELECT MAX(Price) AS LargestPrice  
FROM Products;
```

**Obs**.: **O termo "AS" no código** serve para **renomear o resultado da consulta**. Dessa forma, na saída da consulta a coluna que contém **o resultado aparecerá como "SmallestPrice"**, no primeiro caso, ou "LargestPrice", no segundo.

# COUNT(), AVG() and SUM() Functions
## COUNT()
A função `COUNT()` **retorna o número de registros** que correspondem a um critério específico.

Exemplo:
```SQL
SELECT COUNT(ProductID)  
FROM Products;
```

*Exemplo de output:*
![[Pasted image 20240510124828.png]]
## AVG()
A função `AVG` **retorna a média** de todos os valores encontrados.

Exemplo:
```SQL
SELECT AVG(Price)  
FROM Products;
```

*Exemplo de output:*
![[Pasted image 20240510125044.png]]
## SUM()
A função `SUM` **retorna a soma** de todos os valores encontrados.

Exemplo:
```SQL
SELECT SUM(Quantity)  
FROM OrderDetails;
```

*Exemplo de output:*
![[Pasted image 20240510125239.png]]
