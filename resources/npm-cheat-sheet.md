# NPM Cheat Sheet

## Concepts

### dependency (or package)

Somebody elses code your project depends on to work. e.g. JQuery

dependencies are installed inside the `./node_modules` folder.

### dev dependency

dependency only needed to build your project or 'dev' it locally. E.g. Webpack.

### Finding dependencies

Google "thing you want to do npm". It will tend to lead you to the [npm site which has a search function](https://www.npmjs.com/search?q=netlify) should you need it.

###version

Semantic versions go <major>.<minor>.<patch> e.g. version 3.1.2.

###the package.json file

`package.json` is the config file for npm for your project, it's in "json" format (same as javascript object format but left hand side has quotes too).

###global installs.

If you install a dependency 'globally' you can access it from anywhere on your command line. e.g. `netlify`.

To install something globally: `npm install -g <dependency_name>` `-g` is for global.


###not installing things globally.

It's generally a bad idea to install things globally. Instead do this:

`npm install netlify --save-dev`.

You can then find the thing you can run from the command line in `node_modules/.bin/netlify` (this will also work for the next person :smile:)

## Actions

### Initialize current project as npm project

`cd <directory code is in>`
`npm init`

### Install all the dependencies in `package.json`

`npm install`

### Add a new dependency to the `package.json` file

`npm install <package_name> --save`

### Add a new dev dependency to the `package.json` file

`npm install <package_name> --save-dev`

### Add a 'script' you can rerun

In the 'scripts' section of package.json

e.g

in `package.json`
```
"scripts": {
  "build": "webpack"
}
```

on command line: `npm run build` will run the `webpack` command.

