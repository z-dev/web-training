# HTTP APIs in Javascript
# Outcome

You'll:

* Understand how to grab data from HTP apis in javascript code

# Advice

### How this works

User opens your website. HTML, CSS and Javascript is downloaded. Javascript starts executing. You javascript code then makes what some people call an 'AJAX' request to get data from a HTTP API.

There are low level functions to do this in the browser: `XMLHttpRequest`. They're quite horrible.

### How we do it
Instead we'll use a library. The nicest library for doing this IMO is [SuperAgent](http://visionmedia.github.io/superagent/). Super agent uses a [fluid interface](https://en.wikipedia.org/wiki/Fluent_interface). Where you chain loads and loads of methods together to make everything very readible.

### JSON deserializing / serializing

With any data format (json, xml, etc.) there are two common operations we can do them.

####Serialize (marshal, stringify, to_string)

Converts an object into a string.

```
JSON.stringify({a: 1})

=> '{"a": 1}'
```

####Parse (unmarshal, deserialize)

Converts a string into an object.

```
JSON.parse('{"a": 1}')

=> {a: 1}
```

Data goes across the network in serialized (string) form. So each time we get some data across the wire it would come in raw (string) and need deserializing. (Some libraries do this automatically (SuperAgent does))

# Learning materials

# Core

* [SuperAgent](http://visionmedia.github.io/superagent/)

# Tasks

* Skim through the Super Agent docs
* Query the spotify api in code and display the results on the page using jQuery: http://ws.spotify.com/search/1/artist.json?q=kate%20bush
