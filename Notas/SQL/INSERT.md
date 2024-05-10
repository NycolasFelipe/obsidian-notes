O comando `INSERT INTO` é utilizado para **inserir novos registros em uma tabela**. É possível utilizar o comando de duas formas:

Especificando os nomes das colunas e seus valores respectivos:
```SQL
INSERT INTO Customers (CustomerName, ContactName, Address)  
VALUES ('Cardinal', 'Tom B. Erichsen', 'Skagen 21');
```

Especificando somente os valores, mas seguindo a ordem das colunas na tabela:
```SQL
INSERT INTO Customers 
VALUES ('Cardinal', 'Stavanger', 'Norway');
```
## Inserindo dados somente em colunas específicas
Somente o valor da coluna "CustomerName" será alterado:
```SQL
INSERT INTO Customers (CustomerName)  
VALUES ('Cardinal');
```
