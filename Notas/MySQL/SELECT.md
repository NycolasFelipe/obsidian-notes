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
# Operadores
Os seguintes operadores podem ser utilizados em uma cláusula `WHERE`:
- `=` Equal
- `>` Greater than
- `<` Less than
- `>=` Greater than or equal
- `<=` Less than or equal
- `<>` Not equal. **Nota:** Em algumas versões do SQL, esse operador será `!=`
- `BETWEEN` Between certain range. Ex.: `WHERE Price BETWEEN 50 AND 60`
- `LIKE` Search for a pattern. Ex.: `WHERE City LIKE 's%'`
- `IN` To specify multiple possible values for a column `WHERE City IN ('Paris','London')`
## Operador LIKE
O operador `LIKE` é usado em uma cláusula `WHERE` para **procurar por um padrão específico** em uma coluna. Existem dois caracteres coringa (wildcard) comumente utilizados com esse operador:
- O sinal `%` representa zero, um ou múltiplos caracteres
- O sinal `_` represente um único caractere

Obs.: Os caracteres coringas valem para **letras maiúsculas e minúsculas**.
### Exemplos com `%`:

Retorna todos os clientes cujo nome começa com a letra "a" ou "b":
```SQL
SELECT * FROM Customers  
WHERE CustomerName LIKE 'a%' OR CustomerName LIKE 'b%';
```

Retorna todos os clientes cujo nome termina com a letra "a":
```SQL
SELECT * FROM Customers
WHERE CustomerName LIKE '%a';
```

Retorna todos os clientes cujo nome começa com a letra "b" e termina com "s":
```SQL
SELECT * FROM Customers
WHERE CustomerName LIKE 'b%s';
```

Para retornar um cliente cujo nome tenha uma letra ou frase específica, basta inserir o sinal `%` no início e no final do termo:
```SQL
SELECT * FROM Customers
WHERE CustomerName LIKE '%or%';
```
### Exemplos com `%` e `_`:

Retorna todos os clientes cujo nome começa com "a" e tem pelo menos 3 letras no total:
```SQL
SELECT * FROM Customers
WHERE CustomerName LIKE 'a__%';
```

Retorna todos os clientes cujo nome tem "r" na segunda posição:
```SQL
SELECT * FROM Customers
WHERE CustomerName LIKE '_r%';
```



## Operadores AND, OR e NOT
A cláusula `WHERE` pode ser combinada com os operadores `AND`, `OR` e `NOT`.
### Sintaxe AND
```SQL
SELECT * FROM Customers
WHERE Country = 'Germany' AND City = 'Berlin';
```
### Sintaxe OR
```SQL
SELECT * FROM Customers  
WHERE City = 'Berlin' OR City = 'Stuttgart';
```
### Sintaxe NOT
```SQL
SELECT * FROM Customers  
WHERE NOT Country = 'Germany';
```
### Sintaxe combinada
```SQL
SELECT * FROM Customers  
WHERE Country = 'Germany' AND (City = 'Berlin' OR City = 'Stuttgart');
```



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
