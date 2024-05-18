O comando `DELETE` é usado para **excluir registros** em uma tabela.

==**Observação**: **É extremamente importante prestar atenção** ao excluir os registros de uma tabela. **A cláusula `WHERE` é praticamente obrigatória**, pois sem ela **TODOS os registros** da tabela serão **apagados**.==
## Sintaxe
```SQL
DELETE FROM Customers WHERE CustomerName='Alfreds Futterkiste';
```
## Apagar todos os registros
```
DELETE FROM Customers;
```

No último comando, **todos os registros da tabela "Customers" foram apagados**, mas não a tabela. Isso significa que a **estrutura da tabela, atributos e índexes permanecerão inalterados.**
