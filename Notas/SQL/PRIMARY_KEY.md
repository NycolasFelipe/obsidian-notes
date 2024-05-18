A restrição `PRIMARY KEY` identifica um **registro único** em uma tabela. **É obrigatório** que contenha valores com **restrição `UNIQUE`**, e **não pode conter valores nulos**.
# `PRIMARY KEY` on creating table
```SQL
CREATE TABLE Persons (  
	ID int NOT NULL,  
	LastName varchar(255) NOT NULL,  
	FirstName varchar(255),  
	Age int,  
	PRIMARY KEY(ID)  
);
```

Restrição `PRIMARY KEY` em múltiplas colunas:
```SQL
CREATE TABLE Persons (  
	ID int NOT NULL,  
	LastName varchar(255) NOT NULL,  
	FirstName varchar(255),  
	Age int,  
	CONSTRAINT PK_Person PRIMARY KEY(ID, LastName)  
);
```

**Nota importante:** No exemplo acima, existe somente **UMA** `PRIMARY KEY` - *PK_Person*. Entretanto, o valor desta chave-primária **é composto por duas colunas** (*ID* e *LastName*).
# `PRIMARY KEY` on altering table
```SQL
ALTER TABLE Persons  
ADD PRIMARY KEY(ID);
```

Restrição em múltiplas colunas:
```SQL
ALTER TABLE Persons  
ADD CONSTRAINT PK_Person PRIMARY KEY(ID, LastName);
```
# `DROP` a `PRIMARY KEY` 
```SQL
ALTER TABLE Persons  
DROP PRIMARY KEY;
```
