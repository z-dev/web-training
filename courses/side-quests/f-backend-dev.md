#Backend Node

# Outcome

You'll be able to backend dev.

# Advice

## You already know it.

You already know javascript. Now it's time to backend it up.

Node is a javascript environment which runs outside the browser, instead it runs on the command line. The technologies you already know are linked heavily to node:

Came from Node in the first place:

* npm
* requiring modules


Work fine with Node:

* Babel (and hence es6 / es7)
* eslint
* Any npm package

Don't work / can't be used with Node:

* Webpack (webpack, kind of simulates node (deals with requiring things))

## Extra capabilities

There are some things you can do in node that you can't do inside a browser:

* Access things your operating system knows about
  * local filesystem
  * running processes
  * launch a program
  * anything you can do on a command line
* Communicate over protocols other than http / websockets / webRTC (which are the only things you can do in a browser)
  * Run a http backend


There are lots of npm packages to help you with all of this stuff. We'll run through a few now.


# Learning materials

* [File System API](https://nodejs.org/api/fs.html)
* [Express](http://expressjs.com/) http server.

# Tasks

* Get our [node-seed](https://github.com/z-dev/node-seed) up and running.
* Create a new directory on the filesystem
* Create a file called hello.txt which contains the text: 'hello'
* Make a HTTP get service which returns "hello" using [Express](http://expressjs.com/)
* Make a HTTP get service which returns the JSON `{"hello": "<name>"}` and takes a param `name="john"`.
* Make a HTTP post service which takes JSON {"hello": "john"} and returns that same json.
* Redo the lodash task in node

