A restrição `UNIQUE` impõe que **todos os valores** sob uma coluna **devem ser diferentes**. Além disso, por garantir a **unicidade de valore**s, a restrição [`PRIMARY KEY`](obsidian://open?vault=Notas&file=SQL%2FPRIMARY_KEY) automaticamente contém a restrição `UNIQUE`.

Entretanto, podemos **ter diversas restrições `UNIQUE`** por tabela, e **somente uma restrição `PRIMARY KEY`**.
# `UNIQUE` constraint on creating table

 ==**Observação**: Sempre preferir a segunda opção (múltiplas restrições), para caso seja necessário a remoção da restrição. **Restrições sem nome são muito mais complicadas de serem removidas.**== 

O seguinte comando SQL cria uma restrição única para a coluna *ID* quando a tabela é criada:
```SQL
CREATE TABLE Persons(
	ID int NOT NULL,
	LastName varchar(255) NOT NULL,
	FirstName varchar(255),
	Age int,
	UNIQUE(ID)
);
```

Nomear uma restrição e/ou definir múltiplas restrições:
```SQL
CREATE TABLE Persons (  
	ID int NOT NULL,  
	LastName varchar(255) NOT NULL,  
	FirstName varchar(255),  
	Age int,  
	CONSTRAINT UC_Person UNIQUE (ID,LastName)  
);
```
# `UNIQUE` constraint on altering table

 ==**Observação**: Sempre preferir a segunda opção (múltiplas restrições), para caso seja necessário a remoção da restrição. **Restrições sem nome são muito mais complicadas de serem removidas.**== 

Para criar uma restrição `UNIQUE` na coluna *ID* quando a tabela já existe, podemos utilizar o seguinte comando SQL:
```SQL
ALTER TABLE Persons
ADD UNIQUE(ID);
```

Nomear e definir múltiplas restrições:
```SQL
ALTER TABLE Persons
ADD CONSTRAINT UC_Person UNIQUE(ID, LastName);
```
# `DROP` an `UNIQUE` constraint
```SQL
ALTER TABLE Persons
DROP INDEX UC_Person;
```

