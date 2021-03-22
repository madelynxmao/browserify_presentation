# browserify_presentation

## Mini nodejs explanation
The Node.js run-time environment includes everything you need to execute a program written in JavaScript.

Node.js came into existence when the original developers of JavaScript extended it from something you could only run in the browser to something you could run on your machine as a standalone application.

## What is browserify?
Browserify lets you require('modules') in the browser by bundling up all of your dependencies.
A dependency is another program than you need some input from or it does something that your program requires
browserify is a tool for compiling node-flavored commonjs modules for the browser.

## Why do we use Browserify?
Browsers don't have the require method defined, but Node.js does. With Browserify you can write code that uses require in the same way that you would use it in Node.

## Who made browserify?
Browserify is an open source software, with 187 contributors on github, made under MIT License, written mainly in javascript.

## How does Browserify work?
https://benclinkinbeard.com/posts/how-browserify-works/

## Demonstration
Install node with $ npm install -g npm
Install Browserify with $ npm install --global browserify
Execute with $ browserify source.js -o target.js

Make script1.js file
var msg= "Hello";
module.exports=msg;

Make script2.js file
var msgFromScript1=require("./script1");
var fullMsg=msgFromScript1+ ' ' + "World";
console.log(fullMsg)

Execute to show it works $node script2.js

Make index.html

<!doctype html>
 
<html lang="en">
<head>
 <meta charset="utf-8">
 <title>Title</title>
 <script src= "script2.js"></script>
</head>
<body>
</body>
</html>

Open in browser, to do this from terminal, you can use open ./index.html and get the link. There should be an error : require is not defined

Install browserify $sudo npm install -g browserify

Open a new terminal

Run $browserify script2.js -o bundle.js
	Creates a bundle.js file

Go to index.html
<!doctype html>
 
<html lang="en">
<head>
 <meta charset="utf-8">
 <title>Title</title>
 <script src= "bundle.js"></script>
</head>
<body>
</body>
</html>

Reload the page, should work now. Browserify resolves all the require clauses and puts it in bundle.js.

# What other applications are similar to Browserify?
webpack - does pretty much the same thing as Browserify, which is processing code to be used in a target environment by translating such code to a form that environment (usually a browser) is able to execute
Bower - package manager that download the dependencies and don’t know how to build projects on their own


Sources
https://www.freecodecamp.org/news/what-exactly-is-node-js-ae36e97449f5/

