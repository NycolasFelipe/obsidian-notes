O operador `BETWEEN` **seleciona valores em um intervalo específico**. Esses intervalos **podem ser números, texto, ou datas.** O operador é inclusivo, isto é, os valores **iniciais e finais são inclusos.**

Exemplos:
```SQL
SELECT * FROM Products  
WHERE Price BETWEEN 10 AND 20;
```

```SQL
SELECT * FROM Products  
WHERE Price NOT BETWEEN 10 AND 20;
```

Exemplo `BETWEEN` e `IN`:
```SQL
SELECT * FROM Products  
WHERE Price BETWEEN 10 AND 20  
AND CategoryID NOT IN (1,2,3);
```

Exemplo `BETWEEN` text values:
```SQL
SELECT * FROM Products  
WHERE ProductName BETWEEN 'Carnarvon Tigers' AND 'Mozzarella di Giovanni'  
ORDER BY ProductName;
```

Esse comando irá retornar todos os valores que estão entre os valores "Carnarvon Tigers" e "Mozzarella di Giovanni", isto é, valores que iniciam com "C, D, E, F... etc" até a letra "M". **O mesmo poderia ser feito somente com "C" e "M".**

Exemplo `NOT BETWEEN`:
```SQL
SELECT * FROM Products  
WHERE ProductName NOT BETWEEN 'Carnarvon Tigers' AND 'Mozzarella di Giovanni'  
ORDER BY ProductName;
```

Exemplo `BETWEEN` dates:
```SQL
SELECT * FROM Orders  
WHERE OrderDate BETWEEN '1996-07-01' AND '1996-07-31';
```
