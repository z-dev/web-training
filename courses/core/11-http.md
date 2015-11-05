# HTTP
# Outcome

You'll:

* Understand some of the finer points of HTTP

# Advice

HTTP is the 'protocol' used to load webpages. It's a standard agreed by a bunch of people with neck beards come up with, developers who do httpy stuff (Firefox / Chrome developers etc.) then follow those standards.

It's worth noting that HTTP is [Synchronous](http://stackoverflow.com/questions/748175/asynchronous-vs-synchronous-execution-what-does-it-really-mean), so when you fire off a HTTP request, you wait for the response, there is a persistent connection. If your internet is disrupted in the mean time, you'll most likely get an error.

HTTP calls can return data in many any file format.
e.g:

* http://google.com will return HTML which your browser understands and does stuff with.
* http://textfiles.com/100/914bbs.txt is a text file.
* https://upload.wikimedia.org/wikipedia/commons/e/e9/Felis_silvestris_silvestris_small_gradual_decrease_of_quality.png is a png file.

You can invoke HTTP over the command line. The two most popular are `curl` and `wget`. Curl is a pain to use: [this helps me](https://curlbuilder.com/). Try `curl -XGET 'http://www.google.co.uk'`.

Redirection is quite important, it's very common to do these redirects
* http -> https (secure is good :smile:).
* http://google.com -> http://www.google.com.

# Learning materials

# Core

* [HTTP primer](http://code.tutsplus.com/tutorials/http-the-protocol-every-web-developer-must-know-part-1--net-31177)


# Tasks

* Read the primer but stop at the section: Request and Response Message Formats
* Questions (answers on a postcard!)
  * Draw a sample url from memory and label each bit.
  * What happens if you specify no port on your url? e.g. http://google.com
  * Do me two query parameters: name which should be "john" and age which should be 20.
  * What verbs are there?
  * Which verb does a web browser when you load a page?
  * What goes into a request?
  * What is in a response?

