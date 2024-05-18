O incremento automático permite que um **número único seja gerado automaticamente** quando **um novo registro é inserido** em uma tabela. **Frequentemente, este é o campo de chave primária** que gostaríamos que fosse criado automaticamente sempre que um novo registro fosse inserido.

Por padrão, o **valor inicial para `AUTO_INCREMENT` é 1** e será incrementado em 1 para cada novo registro.

Exemplo de uso na criação de uma tabela:
```SQL
CREATE TABLE Persons (  
    PersonID int NOT NULL AUTO_INCREMENT,  
    LastName varchar(255) NOT NULL,  
    FirstName varchar(255),  
    Age int,  
    PRIMARY KEY (PersonID)  
);
```

Para permitir que a sequência `AUTO_INCREMENT` comece com outro valor, podemos utilizar o seguinte comando SQL:
```SQL
ALTER TABLE Persons AUTO_INCREMENT=100;
```

Quando inserimos um novo registro na tabela, **NÃO precisamos especificar um valor** para a coluna “PersonID” (um valor único será adicionado automaticamente), por exemplo:
```SQL
INSERT INTO Persons (FirstName,LastName)  
VALUES ('Lars','Monsen');
```
