A restrição `CHECK` é usada para **limitar o intervalo de valores** que pode ser colocado em uma coluna. Se definirmos uma restrição `CHECK` em uma coluna, ela **permitirá apenas determinados valores**.

Se definirmos uma restrição `CHECK` em uma tabela, ela **limitará os valores em determinadas colunas** com base nos valores de outras colunas da linha.
# `CHECK` on creating table

 ==**Observação**: Sempre preferir a segunda opção (múltiplas restrições), para caso seja necessário a remoção da restrição. **Restrições sem nome são muito mais complicadas de serem removidas.**== 

A restrição `CHECK` garante que a idade de uma pessoa deve ser 18 anos ou mais.
```SQL
CREATE TABLE Persons (  
	ID int NOT NULL,  
	LastName varchar(255) NOT NULL,  
	FirstName varchar(255),  
	Age int,  
	CHECK (Age>=18)  
);
```

Múltiplas restrições:
```SQL
CREATE TABLE Persons (  
	ID int NOT NULL,  
	LastName varchar(255) NOT NULL,  
	FirstName varchar(255),  
	Age int,  
	City varchar(255),  
	CONSTRAINT CHK_Person CHECK (Age>=18 AND City='Sandnes')  
);
```
# `CHECK` on altering table

 ==**Observação**: Sempre preferir a segunda opção (múltiplas restrições), para caso seja necessário a remoção da restrição. **Restrições sem nome são muito mais complicadas de serem removidas.**== 

```SQL
ALTER TABLE Persons  
ADD CHECK (Age>=18);
```

Múltiplas restrições:
```SQL
ALTER TABLE Persons  
ADD CONSTRAINT CHK_PersonAge CHECK (Age>=18 AND City='Sandnes');
```
# `DROP` a `CHECK` constraint
```SQL
ALTER TABLE Persons  
DROP CHECK CHK_PersonAge;
```
