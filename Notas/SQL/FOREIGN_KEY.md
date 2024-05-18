A restrição `FOREIGN KEY` é usada para **prevenir ações** que destruiriam **conexões entre tabelas**. Essa restrição é um campo (ou coleção de campos) em uma tabela, **que refere-se à uma [`PRIMARY KEY`](obsidian://open?vault=Notas&file=SQL%2FFOREIGN_KEY)** presente em outra tabela.

A tabela com a chave `FOREIGN KEY` é chamada de **Tabela Filha**, enquanto a tabela que contém a chave `PRIMARY KEY` é chamada **Tabela Pai**, ou **Tabela Referenciada**.
# Exemplo
Persons Table
![[Pasted image 20240518140935.png | 600]]

Orders Table
![[Pasted image 20240518140948.png | 300]]

- The *PersonID* column in the *Persons* table is the **`PRIMARY KEY`** in the *Persons* table.
- The *PersonID* column in the *Orders* table is a **`FOREIGN KEY`** in the *Orders* table.
# `FOREIGN KEY` on creating table

 ==**Observação**: Sempre preferir a segunda opção (múltiplas restrições), para caso seja necessário a remoção da restrição. **Restrições sem nome são muito mais complicadas de serem removidas.**== 

```SQL
CREATE TABLE Orders (  
    OrderID int NOT NULL,  
    OrderNumber int NOT NULL,  
    PersonID int,  
    PRIMARY KEY (OrderID),  
    FOREIGN KEY (PersonID) REFERENCES Persons(PersonID)  
);
```

Múltiplas restrições:
```SQL
CREATE TABLE Orders (  
    OrderID int NOT NULL,  
    OrderNumber int NOT NULL,  
    PersonID int,  
    PRIMARY KEY (OrderID),  
    CONSTRAINT FK_PersonOrder FOREIGN KEY (PersonID)  
    REFERENCES Persons(PersonID)  
);
```
# `FOREIGN KEY` on altering table

 ==**Observação**: Sempre preferir a segunda opção (múltiplas restrições), para caso seja necessário a remoção da restrição. **Restrições sem nome são muito mais complicadas de serem removidas.**== 

```SQL
ALTER TABLE Orders  
ADD FOREIGN KEY (PersonID) REFERENCES Persons(PersonID);
```

Múltiplas restrições:
```SQL
ALTER TABLE Orders  
ADD CONSTRAINT FK_PersonOrder  
FOREIGN KEY (PersonID) REFERENCES Persons(PersonID);
```
# `DROP` a `FOREIGN KEY`
```SQL
ALTER TABLE Orders  
DROP FOREIGN KEY FK_PersonOrder;
```
