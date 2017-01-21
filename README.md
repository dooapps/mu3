mu3
==========

mu3 is a node module with an express template engine function for the [mu2](https://github.com/raycmorgan/Mu) mustache render module.

Example:

```javascript
var mu3 = require("mu3");
var express = require("express");
var app = express();
app.engine('html', mu3.engine);
app.set('view engine', 'mustache');
app.set('views', __dirname + '/views');

app.get('/', function(req, res) {
	//Renders the views/index.html file with the view {'name': 'Marco Miller'} using the mu2 engine
	res.render('index', {
		'name' : 'Marco Miller');
	});
app.listen(8080);
```