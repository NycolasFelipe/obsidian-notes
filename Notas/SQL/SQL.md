# O que é SQL?
SQL is the **standard language for dealing with Relational Databases**. SQL is used to insert, **search, update, and delete database records.**
# Como usar SQL?
The following SQL statement selects all the records in the "Customers" table:
```SQL
SELECT * FROM Customers;
```
## Observação
- SQL keywords are NOT case sensitive: `select` is the same as `SELECT`
# Ponto e vírgula
**Semicolon is the standard way to separate each SQL statement** in database systems that allow more than one SQL statement to be executed in the same call to the server.
# Comandos SQL mais importantes
- [`SELECT`](SELECT.md) - extracts data from a database  
- [`UPDATE`](UPDATE.md) - updates data in a database
- [`DELETE`](DELETE.md) - deletes data from a database
- [`INSERT INTO`](INSERT.md) - inserts new data into a database
- `CREATE DATABASE` - creates a new database
- `ALTER DATABASE` - modifies a database
- `CREATE TABLE` - creates a new table
- `ALTER TABLE` - modifies a table
- `DROP TABLE` - deletes a table
- `CREATE INDEX` - creates an index (search key)
- `DROP INDEX` - deletes an index
## Outros comandos SQL
- [`NULL`](NULL.md) - a field with a NULL value is a field with no value
