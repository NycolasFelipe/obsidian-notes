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
