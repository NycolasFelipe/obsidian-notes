O método `get()` da interface [`URLSearchParams`](https://developer.mozilla.org/en-US/docs/Web/API/URLSearchParams) retorna o primeiro valor associado ao parâmetro de busca fornecido.
##### Exemplo:
Se a URL da sua página é `https://example.com/?name=Jonathan&age=18` você pode obter o parâmetro 'name' e 'age' usando:
```js
let params = new URLSearchParams(document.location.search.substring(1));
let name = params.get("name"); // retorna a string "Jonathan"
let age = parseInt(params.get("age"), 10); // retorna o número 18
```

Buscar um parâmetro que não esteja presente na string de pesquisa, retornará **`null`**:
```js
let address = params.get("address"); // null
```
