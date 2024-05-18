**Constraints** são usadas para especificar regras para dados em uma tabela. Elas garantem a **precisão e confiabilidade dos dados** na tabela, e podem ser a **nível de coluna ou de tabela**.
# Constraints (restrições) mais comuns:
- [`NOT NULL`](NOT_NULL.md) - ensures that a column cannot have a NULL value
- [`UNIQUE`](UNIQUE.md) - ensures that all values in a column are different
- [`PRIMARY KEY`](PRIMARY_KEY.md) - a combination of a `NOT NULL` and `UNIQUE`. Uniquely identifies each row in a table
- [`FOREIGN KEY`](FOREIGN_KEY.md) - Prevents actions that would destroy links between tables
- [`CHECK`](CHECK.md) - Ensures that the values in a column satisfies a specific condition
- [`DEFAULT`](DEFAULT.md) - Sets a default value for a column if no value is specified
