O comando `ALTER DATABASE` serve para modificar um banco de dados de diversas formas, descritas [nesse link](https://learn.microsoft.com/en-us/sql/t-sql/statements/alter-database-transact-sql), dentre elas renomear o nome do banco de dados. Por exemplo:
```SQL
ALTER DATABASE testBD MODIFY NAME = newTestBD;
```

**Observação:** O uso do comando para renomear um banco de dados costuma gerar dor de cabeça, o mais recomendado nesse cenário seria:
- **Criar um novo banco de dados** com o nome correto, e então copiar todas as tabelas do antigo para o novo. Depois disso, apagar o banco de dados original.
- **Criar um dump do banco de dados** original, e depois importá-lo com um novo nome.

Após quaisquer uma das etapas, apagar o banco de dados original.