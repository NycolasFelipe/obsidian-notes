O comando `ALTER TABLE` serve para **adicionar**, **excluir**, ou **modificar** colunas em uma tabela. Também é utilizado para adicionar e remover diversas [**constraints**](obsidian://open?vault=Notas&file=SQL%2FCONSTRAINTS) (restrições) existentes em uma tabela.
# `ADD column`
O seguinte código SQL adiciona uma coluna "Email" à tabela "Customers":
```SQL
ALTER TABLE Customers
ADD Email varchar(255);
```
# `DROP COLUMN`
O seguinte código SQL exclui a coluna "Email" da tabela "Customers":
```SQL
ALTER TABLE Customers
DROP COLUMN Email;
```
# `MODIFY COLUMN`
Para mudar o tipo de dado de uma coluna, utilizamos a sintaxe:
```SQL
ALTER TABLE table_name
MODIFY COLUMN column_name datatype;
```
