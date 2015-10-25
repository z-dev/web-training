#Webpack

# Outcome

You'll:

* Have a basic understanding of what webpack is and what it's used for.
* Be able to use webpack using our seed project.

# Prerequisites

* SASS and ES6 help.

# Advice

Webpack is a tool which helps you 'build' code. (Take things which won't quite run in the browser e.g. .scss or ES6 Javascript and convert them to vanilla HTML, CSS and JS (transpile them))

It's the new hotness and it's quite easy to setup.

What will webpack do for us:

* Run a server so you can access your site like this: http://localhost:8000
  * This is good because it's closer to the real deal (as opposed to file://myfile.html, i've seen webpages which worked on a server but not as a file.)
* Transpile SCSS into CSS
* Let you use the `require` syntax to require one of your `.js` files from another. (This solves the global var problem in javascript)
  * This works by 'bundling' many files into one giant file. (So it's also a sort of transpile)
  * You can also require libraries you got using NPM. e.g. `var $ = require('jQuery')`. `$` will then only be defined in your current file.
* Transpile ES6 (latest) Javascript into ES5 (current version which all browsers support) Javascript
* Watch for your files to change, and automatically redo the above transpiles and refresh your browser automatically.

# Learning materials

# Core

* [Webpack Cookbook](https://christianalfoni.github.io/react-webpack-cookbook/index.html) Sections: Intro, 1, 3, skim 4 (skim everything a bit I think)

# Tasks

* *Skim* through the cookbook.
* Checkout the [sample webpack project](https://github.com/richardgill/webpack-seed).
  * Read the readme for the commands you can run
  * Modify some SCSS and check it compiles to CSS and you can see it in chrome
  * Modify some javascript and look at the output in chrome
  * Do some javascript `require`s and look at the output in chrome
  * Look at how javascript's ES6's features are being 'compiled' in Chrome
