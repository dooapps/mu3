# mu3
mu3 is a node module with an express template engine function for the mustache like jade/Pug architecture.

# Features

* All [Mustache ](http://mustache.github.io) features
* Express 3.x/4.x support
* Architecture [Jade/Pug ](https://pugjs.org/api/getting-started.html)

# Samples

* creating your main.js demo

	```javascript
	var mu3 = require("mu3");
    var express = require("express");
    var app = express();
    
    app.engine('html', mu3.engine);
    app.set('view engine', 'html');
    app.set("view options", {layout: true});
    app.set('views', __dirname + '/views');

    
	app.get("/CustomLayout", function(req, res) {
		res.render("index", {
			name: "Marco",
			layout: "CustomLayout"
		});
	});
	app.get("/withoutLayout", function(req, res) {
		res.render("index", {
			name: "Marco",
			layout: false
		});
	});
	app.get("/DefaultLayout", function(req, res) {
		res.render("index", {
			name: "Marco"
		});
	});
	app.get("/withoutvariable", function(req, res) {
		res.render("index");
	});
	```

