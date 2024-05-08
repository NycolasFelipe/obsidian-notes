- Communicate with a server by making a http request
- No need to reload the page
- Stands for *Asynchronous JavaScript And XML*

### Vanilla Asynchronous Request

```js
window.onload = function() {
	let http = new XMLHttpRequest();
	
	http.onreadystatechange = function() {
		if (http.readyState === 4 && http.status === 200) {
			/*  READY STATES
				0 - request not initialized
				1 - request has been set up
				2 - request has been sent
				3 - request is in process
				4 - request is complete
			*/  
			let response = JSON.parse(http.response);
			console.log(response);
		}
	}
	
	http.open("GET", "data.json", true);
	http.send();
}
```

### Jquery Request
[Perform an asynchronous HTTP (Ajax) request.](https://api.jquery.com/jQuery.ajax/)

```js
	$.get("data.json", function(data) {
		console.log(data);
	});
```

