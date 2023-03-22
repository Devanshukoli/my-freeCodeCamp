1. challenge: Meet the node console. => It was basically set up with nothing much, there was an `app.js` file and in which I would use express.js and here I want to console a "Hello world".

2. challenge: Start a working express server. => In the first two lines of the file myApp.js, you can see how easy it is to create an Express app object. This object has several methods, and you will learn many of them in these challenges. One fundamental method is app.listen(port). It tells your server to listen on a given port, putting it in a running state. For testing reasons, we need the app to be running in the background so we added this method in the server.js file for you.
	- Let’s serve our first string! In Express, routes take the following structure: app.METHOD(PATH, HANDLER). METHOD is an HTTP method in lowercase. PATH is a relative path on the server (it can be a string or even a regular expression). HANDLER is a function that Express calls when the route is matched. Handlers take the form function(req, res) {...}, where req is the request object, and res is the response object. For example, the handler
		function(req, res) {
 			 res.send('Response String');
		}
will serve the string 'Response String'. 
answer==> // created a response for printing "Hello Express" in the dom

let express = require('express');
let app = express();

app.get('/', (req, res) => {
	res.send("Hello Express")
})

3. challenge: Server an HTML file =>You can respond to requests with a file using the res.sendFile(path) method. You can put it inside the app.get('/', ...) route handler. Behind the scenes, this method will set the appropriate headers to instruct your browser on how to handle the file you want to send, according to its type. Then it will read and send the file. This method needs an absolute file path. We recommend you use the Node global variable __dirname to calculate the path like this:
		ex:absolutePath = __dirname + '/relativePath/file.ext'
	- Send the /views/index.html file as a response to GET requests to the / path. If you view your live app, you should see a big HTML heading (and a form that we will use later…), with no style applied.
answer==> //just change the response format,

app.get('/', (req, res) => {
	res.sendFile(__dirname + '/views/index.html')
})

4. challenge: Server static assets => An HTML server usually has one or more directories that are accessible by the user. You can place there the static assets needed by your application (stylesheets, scripts, images).
	- In Express, you can put in place this functionality using the middleware express.static(path), where the path parameter is the absolute path of the folder containing the assets.
	- If you don’t know what middleware is... don’t worry, we will discuss in detail later. Basically, middleware are functions that intercept route handlers, adding some kind of information. A middleware needs to be mounted using the method app.use(path, middlewareFunction). The first path argument is optional. If you don’t pass it, the middleware will be executed for all requests.
	- Mount the express.static() middleware to the path /public with app.use(). The absolute path to the assets folder is __dirname + /public.
answer==> // just add another app.use() in the myapp.js file

let express = require('experss')
let app = experss();

app.get('/', (req, res) => {
	res.sendFile(__dirname + '/vies/index.html')
})

app.use('/public', express.static(__dirname + "/public"))

5. challenge: Serve JSON on a Specific Route => While an HTML server serves HTML, an API serves data. A REST (REpresentational State Transfer) API allows data exchange in a simple way, without the need for clients to know any detail about the server. The client only needs to know where the resource is (the URL), and the action it wants to perform on it (the verb). The GET verb is used when you are fetching some information, without modifying anything. These days, the preferred data format for moving information around the web is JSON. Simply put, JSON is a convenient way to represent a JavaScript object as a string, so it can be easily transmitted.
	- Let's create a simple API by creating a route that responds with JSON at the path /json. You can do it, as usual, with the app.get() method. Inside the route handler, use the method res.json(), passing in an object as an argument. This method closes the request-response loop, returning the data. Behind the scenes, it converts a valid JavaScript object into a string, then sets the appropriate headers to tell your browser that you are serving JSON, and sends the data back. A valid object has the usual structure {key: data}. data can be a number, a string, a nested object, or an array. data can also be a variable or the result of a function call, in which case it will be evaluated before being converted into a string.
answer==> // using middleware function though it's inbuilt in express

app.use(express.json()) // This line of code initializes the middleware function for Express to parse incoming requests with JSON payloads. It allows Express to recognize the incoming request object as a JSON object.
app.get('/json', (req, res) => {
    res.json({"message": "Hello json"})
})

6. challenge: Use the .env file => The .env file is a hidden file that is used to pass environment variables to your application. This file is secret, no one but you can access it, and it can be used to store data that you want to keep private or hidden. For example, you can store API keys from external services or your database URI. You can also use it to store configuration options. By setting configuration options, you can change the behavior of your application, without the need to rewrite some code.
	- 


















































