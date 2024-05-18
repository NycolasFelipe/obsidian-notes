O comando `CREATE INDEX` é usado para **criar índices em tabelas**.

Os índices são usados para **recuperar dados do banco de dados mais rapidamente** do que de outra forma. Os usuários não podem ver os índices, eles apenas **servem para agilizar pesquisas/consultas**.

==**Observação**: Atualizar uma tabela com índices **leva mais tempo do que atualizar uma tabela sem** (porque os índices também precisam de atualização). Portanto, crie índices apenas em colunas que **serão pesquisadas com frequência**.==

# `CREATE INDEX`
A instrução SQL abaixo cria um índice chamado `idx_lastname` na coluna "LastName" da tabela "Persons":
```SQL
CREATE INDEX idx_lastname  
ON Persons (LastName);
```

Se quisermos criar um índice em uma combinação de colunas, podemos listar os nomes das colunas entre parênteses, separados por vírgulas:
```SQL
CREATE INDEX idx_pname  
ON Persons (LastName, FirstName);
```
# `DROP INDEX`
A instrução `DROP INDEX` é usada para **excluir um índice** em uma tabela.
```SQL
ALTER TABLE _table_name  
_DROP INDEX _index_name_;
```
