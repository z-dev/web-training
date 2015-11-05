# HTTP API
# Outcome

You'll:

* Understand how people use HTTP to write remote APIS

# Advice

Initially HTTP was used only for websites. But then some bright spark decided to also use it for 'APIs'.

### WTF is API?

API is a horribly overriden term. It's quite general. Loosely it means: 'When i'm programming and do this. This will happen.'. It refers to a collection of local or remote function calls.

I found it really hard to define properly, so here are some examples.

* jQuery has an api. It's the desciption of all the functions jQuery has.
  * One part of that api would be: `$('my-class') #Will select all elements in the DOM which have .my-class and return all the HTML elements that match.`
* javascript doesn't have an api because it's not a library / framework, it's a programming language. I don't know why, but you wouldn't say 'javascript's api' to refer to the `+` operator. It's just part of the language. It's only things built on top of programming languages which have APIS. (1)
* http://ws.spotify.com/search/1/artist.json?q=kate%20bush is an api. Because it takes parameters and returns structured data.
* http://google.com is not an api, because it doesn't return computer readable structured data. (It does take parameters though! e.g. https://google.com/?q=hello+john)

So having thought about it more maybe: An API is a way of describing something which is conceptually like a 'function'. It takes parameters or data in and returns data out in a format a computer can easily understand.

Some of these APIs run locally e.g. jQuery. They execute all within your programming language and return data in your programming language e.g. an int or a string.

Some of these APIs run remotely e.g. http apis. You send a http message across the network to another process, which interprets the message. Runs a function and then sends a structured message back with the response.

###Why are remote API calls a good idea?

Cons:

* Unreliable? If network breaks, API breaks.
  * HTTP uses something called TCP. Which helps with little mini failures. (2)
* Slower, networks are 'IO' (Input Output). IO is always slowest bit.

Pros:

* Keeping things secret
  * If you've written some code which does something that other people find hard to program a solution to and is useful. Then you're probably a millionaire. Keeping it secret is useful :smile:.
  * When you host a HTTP api, you just open up one port e.g. port 80 for HTTP traffic. This does not allow people to see you code. They just know what they can do with the API and what it will return. They have no idea / access to how it works. It's a 'black box'.
* Powerful hardware
  * If someone loads an app on their smartphone and it tries to locally compute some really complex thing it's going to be slow. Instead you can query a http api and let a MASSIVE server do this for you :) .
* Scalability
  * You could host your HTTP API on a single Core 2 duo server with 4GB of ram. But when you have a lot of users you might face 1000 HTTP requests per minute. At some point, your server will not cope and the requests will take longer. At some point some people won't even get responses any more (a HTTP timeout).
  * With HTTP APIs you can host 2x Core 2 Duo server with 4GB of ram. You then put a very lightweight, industrial strength HTTP server at the front which simply diverts requests on to one of the two. This is called a load balancer. NGINX and HA-Proxy are the big ones.
* Keeping things REALLY seperate (and reusable)
  * If you put all your code all in one project it tends to grow and grow and eventually becomes a steaming mess. Some people think that splitting things out might help. (This is a hard topic.)
* Using various programming languages
  * Different programming languages have different strengths / weaknesses (3). You might wish to use a different language for a particular part of your app. You could split your http api over 3 languages.

When talking about HTTP APIs another word that's bounded around alot is REST. It's basically a convention on how to structure which HTTP verbs (GET, POST, PUT etc.) you use depending on what you're doing. It's probably a good idea to roughly follow rest. But realistically HTTP APIs are just a way of remote calling a function. It's a good idea that those APIS 'don't have state' and are predictable. It would be bad if you called a GET HTTP API once, and this affected the response of the second call.

###Why HTTP APIs though?

This has really kicked off in the last 5 years. The primary reason is that the web sandbox only allows you to call out to things using the HTTP protocol. Alot of technologies in the last 10 years became popular and then became standard because websites are very popular (obviously). And the restrictions of the web haven't really changed, so in the end people found ways to make these things good. E.g. Javascript (which was truly awful 10 years ago). And HTTP for APIs, which would have made you sound mad 10 years ago. Once the tools / online resources became available people then started using them where they didn't even need to (desktop apps / mobile apps).

###So what is standard?

Restful(ish) HTTP APIS which return JSON as the response format. You can also return XML but bother are machine readible but JSON is more human readable, which has made JSON popular.

#### When you might not use HTTP

You care about performance. Most games, torrents, skype. Are probably going to use something which operates using UDP. There is a new things I know nothing about called webrtc that I think does this for websites (appear.in uses it I think).

If you want asynchronous communications e.g. a push notification. Then HTTP has not got your back. Websockets is a relatively recent addition to browsers that can do it. For example when a hangout comes in and Gmail pops it open, that's probably websockets.

Async is more complicated to code and reason about than sync. So use sync unless you need async.

#### When might you not use JSON

You need to be super-careful about checking the format of data in or out. Banks are reknowned for using XML (which can have a 'schema' with it, which lays out rules for what is / isn't allowed). XML is just not great IMO. I'd rather use JSON and write some code to validate it's correct...

You care about the size of the data you're sending around. JSON is human readible, but it's not compressed at all. There are formats which compress it down to binary and back again in a repeatable way.

[BSON (binary JSON)](https://en.wikipedia.org/wiki/BSON)
[Profobuf (by google)](https://developers.google.com/protocol-buffers/?hl=en)
[Thrift (by twitter)](https://thrift.apache.org/)

But to use these, you need a library with can 'parse' and 'serialize' these formats.

# Learning materials

# Core

* [HTTP API Primer](http://code.tutsplus.com/tutorials/a-beginners-guide-to-http-and-rest--net-16340)


# Tasks

* Read the primer
* Read the advice.
* Compare [JSON api call](http://ws.spotify.com/search/1/artist.json?q=kate%20bush) to [XML api call](http://ws.spotify.com/search/1/artist?q=kate%20bush)

# Footnotes

(1) The `+` operator is really just a special function if you think about it. var + = function(a,b) { .... }. It's just that you don't say: `+(1, 2)` you say `1 + 2`.

Some languages (e.g. scala) let you write functions which can be used 'infix' like this. e.g. `infix var add = function(a,b) { a + b }; 1 add 2;` This allows you to write more mathematical operators and stuff. Mental.

(2)

[http://www.diffen.com/difference/TCP_vs_UDP](TCP vs UDP). TCP is slower and has more guarentees than UDP. UDP is faster as a result. You would always use something with TCP unless you had performance requirements. When you play DOTA, it will probably use TCP to find a match / manage you friends list, but when it's sending you information about hero movements, that's UDP. Skype will work with UDP.

(3)

Interestingly, no one language seems to have nailed everything. There is nearly always a trade off of some sort.

C and C++ are really fast, but super hard to understand as a human being.
Ruby on Rails is quick to program, but has pretty bad performance.
etc.

Whatsapp wrote their code in Erlang (which is super good at messagey stuff), they sold to Facebook for $18B with just ~20 devs on staff. Their success was probably largely based around picking the right programming language for the job :smile:.  Mental.
