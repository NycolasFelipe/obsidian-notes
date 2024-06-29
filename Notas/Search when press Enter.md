```js
const searchOnEnter = (e) => {
	if (e.key === "Enter") {
		search(term);
		e.target.blur();
	}
}
```

```html
<input
	type="text"
	name="searchBox"
	id="searchBox"
	placeholder="Procure um produto..."
	autoComplete="off"
	onChange="(e) => setSearch(e.target.value)"
	onKeyUp="(e) => searchOnEnter(e)"
/>
```
