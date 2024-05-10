# O que é um valor NULL?
Um campo com valor NULL é um **campo com nenhum valor atribuído**.

*Nota*: Um campo com valor NULL é um campo **diferente do valor zero ou de um campo que só possui espaços**. Um campo NULL é um campo vazio **criado durante a criação do registro**.
## Como testar valores NULL?
Não é possível testar valores NULL com operadores. Para isso, precisamos utilizar os operadores especiais `IS NULL` e `IS NOT NULL`.
### Sintaxe IS NULL
```SQL
SELECT CustomerName, ContactName, Address  
FROM Customers  
WHERE Address IS NULL;
```
### Sintaxe IS NOT NULL
```SQL
SELECT CustomerName, ContactName, Address  
FROM Customers  
WHERE Address IS NOT NULL;
```
