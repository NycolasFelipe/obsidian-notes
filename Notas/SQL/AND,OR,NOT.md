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
