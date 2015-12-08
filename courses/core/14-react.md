# React
# Outcome

You'll:

* Understand what react is and be able to make interactive web apps with it.
* Understand what JSX is.
* Why you learned everything else :) (Webpack, ES6, Lodash, SuperAgent) (Cos they work amazingly with React)

# Advice

##JSX

JSX is important with React. We'll always use it. JSX is another transpiled language (like we do for ES6 -> ES5 code). JSX lets you write HTML directly in javascript. That's it.

```
var someHtml = <div>Hi Buddy</div>
```

We'll use webpack to do the transpilation.

JSX doesn't quite generate a string. I think it generates DOM javascript 'objects'. You can check for yourself in the debugger.

### Differences from normal HTML

#### Attribute names are different

They're camel cased by convention (instead of dashed). Sometimes they're a tiny bit different, but React normally just tells you the problem and the fix in the console :). [Read more](https://facebook.github.io/react/docs/tags-and-attributes.html)

`<button class="btn btn-primary">Click Me</button>` -> `<button className="btn btn-primary">Click Me</button>`

#### You can write Javascript inside your HTML.

JSX works just like normal HTML unless you do one thing. If you put `{}` then inside the brackets you go back to javascript.

```
var x = 1
var someHtml = <div>{x + 1}</div>
```

```
var buttonClass = 'btn btn-primary'
var button  = <button className={buttonClass}>Click Me</button>
```

*Exception*
It's quite rare to use it though.
```
var elementType = 'div'
var someHtml = <elementType></elementType>
```

##React

React is a javascript library which helps build more complex interactive UIs. It helps you build 'views' (User Interfaces) which change as inputs come in (e.g. data from a http api, or a user clicking things).

It provides about 5 important APIs, that you need to understand well. And a bunch of less important things you can learn as you go.

Important APIs:

###React.render

```
React.render(<p>Hello</p>, document.getElementById('content'));
```
In the order javascript evalulates it:

* `<p>Hello</p>` is JSX for the html `"<p>Hello</p>"`
* `document.getElementById('content')`  is equivalent to `$('#content')` in jquery. But without jQuery cos you probably wouldn't mix up your react and jQuery.
* So this whole thing is pretty much like: `$('#content').replace(<p>Hello</p>)`


###React.createClass (React Components)

`React.createClass` is how you define a 'component'. Components is the only idea in React. They can have [different functions defined inside them](https://facebook.github.io/react/docs/component-specs.html): e.g. `render`, `componentWillMount`.

Components are 'defined' (once), 'created' (0 or more times). Once a component is 'created' it 'lives' for a period of time (whilst the user has the website open?).

The functions inside the component definition are called at certain points in a components life.

####Defining a component
```
var myComponent = React.createClass({
  render: function() {
    return (
      <a className="btn btn-default">I am a button! Click me!</a>
    );
  }
})
```
We will be putting each component in it's own file (and `module.export`ing it for use else where.)
####Creating (instantiating) a component
You can then write: `<myComponent />`. So you can basically define your own html tags. E.g. `<hero />` which would render a dota hero. You can reuse it anywhere.

###render

`render` is a function which returns JSX. The component will call the render function whenever it wants to know: 'What does this component currently look like at this point in its life.'. It will take the output of the `render` function and put it into the browser (it updates the DOM automatically every time it calls the render function).

Every component *Must* have a `render` function.

###Props (properties -> could be called 'arguments' really)

Props are properties that get 'passed in' to the component when it's created.

Props are *immutable* - they can never change.

####Passing props in

`<hero name='Puck' />`

Here we pass a prop called `name` into the hero with the value `'Puck'`.

####Talking about props inside the component

Inside any of the functions we pass into `createClass` e.g. `render`.  We can access the prop using `this.props.name`.

`this.props` is an object with all the props in. e.g. `{name: 'Puck'}`
```
var hero = React.createClass({
  render: function() {
    return (
      <div>{this.props.name}</div>
    );
  }
})
```
I'm aware that `this` has just randomly just popped up on you :p . This is because components are conceptially a 'Class' and we're straying into Object Oriented Programming (OOP), which is quite famous / popular. This is a tricky concept which we will cover fully later, I think you can program React without really understanding it fully. (I know not understanding stuff fully kind of sucks though :( )

###State

State very similar to props, except for it's not immutable - so they can change over time.

You should favour props where possible. Cos things not changing is easier to reason about in a programmers mind.


####Setting state

#####getInitialState function

```
var hero = React.createClass({
  getInitialState: function() {
    return {name: 'unknown'}
  },

  render: function() {
    return (
      <div>{this.state.name}</div>
    );
  }
})
```
#####setState function
In any of the functions inside the component. You can say `this.setState({name: 'Danger Mouse'})`.

Any time you change the state of a component React will call the `render` function again and update the component automatically on the screen.

Do not set state like this: `this.state = {name: 'Danger Mouse'}`. It won't call the `render` function, and might just completely break everything.

####Talking about state inside the component

Inside any of the functions we pass into `createClass` e.g. `render`.  We can access the state (which is also an object like props) using `this.state`.

###componentWillMount

`componentWillMount` is a function you define inside your component. It gets called when you create your component. Use it to do stuff before your component is shown on the screen.

###componentDidMount
`componentDidMount` is a function you define inside your component. It gets called a little after `componentWillMount`. Use it to do stuff before your component is shown on the screen.


##How to think about React

* React is a library which lets you create new HTML tags (components) e.g: `<hero name='Puck'/>`.
* React components are essentially: `props` (immutable) + `state` (can change) and a `render` function which probably talks about `props` and `state`.
  * Think of react as: `function render(props, state) { return(<div>{this.props.name} {this.state.somethingElse}) }`
  * This function gets called every time state changes and will automatically update the DOM.

# Learning materials

# Core

* [React Primer](https://github.com/mikechau/react-primer-draft)
* [React Frontend Masters](https://frontendmasters.com/courses/react/)
* [Official Docs](https://facebook.github.io/react/docs/getting-started.html) bit crap in my opinion. They're good once you understand React enough to get stuff done, but not amazing for learning IMO.

# Tasks

Do it like throwing Spaghetti at wall. Feel free to jump backwards, re-read, re-watch, play around until you get it.

* Read my Advice.
* Skim the Primer.
* Watch frontend masters react course.
* Do the [tasks](https://docs.google.com/document/d/1GfyOXSaBuvjIsNMh31gKfED_q7H-_3muY9xuRgStjQY/edit?usp=sharing)
