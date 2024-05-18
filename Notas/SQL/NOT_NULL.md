**Por padrão**, uma coluna pode guardar valores `NULL`. A restrição `NOT NULL` **impõe que uma coluna não pode aceitar valores nulos**.
# `NOT NULL` on creating a table
```SQL
CREATE TABLE Persons(
	ID int NOT NULL,
	LastName varchar(255) NOT NULL,
	FirstName varchar(255) NOT NULL,
	Age int
);
```

Este comando SQL impõe que as colunas *ID*, *LastName* e *FirstName* não aceitarão valores nulos.
# `NOT NULL` on altering table
Para criar uma restrição `NOT NULL` na coluna *Age*, podemos utilizar o seguinte comando SQL:
```SQL
ALTER TABLE Persons
MODIFY COLUMN Age int NOT NULL;
```
