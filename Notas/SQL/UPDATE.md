O comando `UPDATE` é usado para modificar registros em uma tabela.

==**Observação**: **É extremamente importante prestar atenção** ao atualizar os registros de uma tabela. **A cláusula `WHERE` é praticamente obrigatória**, pois sem ela **TODOS os registros** da tabela serão **atualizados**.==
# Sintaxe

Atualizar um único registro:
```SQL
UPDATE Customers  
SET ContactName = 'Alfred Schmidt', City = 'Frankfurt'  
WHERE CustomerID = 1;
```

Atualizar múltiplos registros:
```SQL
UPDATE Customers  
SET PostalCode = 00000  
WHERE Country = 'Mexico';
```

Nesse último caso, o campo "PostalCode" **será atualizado em TODOS os registros** que possuírem o campo "Country" com o valor "Mexico".