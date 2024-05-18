A restrição `DEFAULT` é usada para **definir um valor padrão** para uma coluna.
# `DEFAULT` on creating table
```SQL
CREATE TABLE Persons (  
    ID int NOT NULL,  
    LastName varchar(255) NOT NULL,  
    FirstName varchar(255),  
    Age int,  
    City varchar(255) DEFAULT 'Sandnes'  
);
```

A restrição `DEFAULT` também pode ser usada para **inserir valores do sistema**, usando funções como [`CURRENT_DATE()`](https://www.w3schools.com/mysql/func_mysql_current_date.asp):
```SQL
CREATE TABLE Orders (  
    ID int NOT NULL,  
    OrderNumber int NOT NULL,  
    OrderDate date DEFAULT CURRENT_DATE()  
);
```
# `DEFAULT` on altering table
```SQL
ALTER TABLE Persons  
ALTER City SET DEFAULT 'Sandnes';
```
# `DROP` a `DEFAULT` constraint
```SQL
ALTER TABLE Persons  
ALTER City DROP DEFAULT;
```

