### Non-null assertion operator
Ao selecionar um elemento por sua tag HTML, o TypeScript automaticamente detecta o tipo de elemento. Porém, não é possível identificar antes da execução se o elemento de fato existe no DOM. 

Para evitar uma verificação desnecessária, é possível usar o operador **! (non-null assertion operator)** para garantir ao compilador que o elemento de fato existe:

```ts
const anchor = document.querySelector("a");
//HTMLAnchorElement | null

const anchorB = document.querySelector("a")!;
//HTMLAnchorElement
```
### Type Casting
Selecionando um elemento por sua identificação (classe ou id), é impossível detectar seu tipo antes do tempo de execução. 

Porém, se for possível garantir a existência do elemento, é possível realizar um type casting para ter acesso à todos os métodos do elemento e evitar tratamento para caso null.

```ts
const form = document.querySelector("form");
//HTMLFormElement | null

const formB = document.querySelector(".form");
//HTMLElement | null

const formC = document.querySelector(".form") as HTMLFormElement;
//HTMLFormElement
```

### Render an HTML Template
[[Render an HTML Template]]