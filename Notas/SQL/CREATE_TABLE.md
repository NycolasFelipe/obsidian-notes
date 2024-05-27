# Create table
O comando `CREATE TABLE` é usado para **criar uma nova tabela** em um banco de dados. Por exemplo:
```SQL
CREATE TABLE Persons(
	PersonID int,
	LastName varchar(255),
	FirstName varchar(255),
	Address varchar(255),
	City varchar(255)
);
```

Agora a tabela **Persons** pode ser preenchida com dados utilizando o comando SQL [`INSERT INTO`](obsidian://open?vault=Notas&file=SQL%2FINSERT).
# Create table from another table
## `CREATE TABLE AS SELECT`
Considere a seguinte tabela chamada `product` que contém as colunas `id` (primary key), `name`, `category` e `price`
![[Pasted image 20240518125115.png|400]]

Vamos criar uma nova tabela chamada `florist`, que irá guardar as colunas `id`, `name` e `price`, mas somente onde a linha tiver categoria igual a *flower*. O código SQL é o seguinte:
```SQL
CREATE TABLE florist
AS SELECT *
FROM product
WHERE category = 'flower';
```

A nova tabela `florist` será da seguinte forma:
![[Pasted image 20240518125509.png | 400]]
# `SELECT INTO`
Outra solução é usar `SELECT INTO`. Esta é uma sintaxe **non-standard SQL**, mas é suportada em muitos banco de dados populares. O comando seria:
```SQL
SELECT
	id,
	name,
	price
INTO florist
FROM product
WHERE category = 'flower';
```
# Copy structure only
Para copiar somente a estrutura de uma tabela, podemos utilizar o comando SQL:
```SQL
SELECT TOP 0 *
INTO newTable
FROM originalTable;
```
