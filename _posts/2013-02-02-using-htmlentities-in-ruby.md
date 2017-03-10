---
layout: post
title: "Using htmlentities in ruby"
permalink: using-htmlentities-in-ruby
date: 2013-02-02 18:43:15
comments: true
description: "using htmlentities in ruby"
keywords: "html, entities"
categories: "ruby"

tags:

---

HTML character entities are used to display reserved characters in a web page. The entire list of character entity references can be found [here](http://en.wikipedia.org/wiki/List_of_XML_and_HTML_character_entity_references "wikipedia character entity reference"). Sometimes you may want to use HTML entities inside your ruby code. This is where gem [htmlentities](http://htmlentities.rubyforge.org/ "htmlentities") comes into picture. This is a simple library to facilitate encoding and decoding of character and numerical html entities in ruby. It works with only UTF-8 (or ASCII) strings only. make sure your system is set to display UTF-8 before using it.

You can install the gem by typing

{% highlight bash %}
gem install htmlentities
{% endhighlight %} 

##### Encoding

You can encode HTML entities by calling encode method on HTMLEntities class. This method takes variable number of options as parameters

{% highlight bash %}
require 'htmlentities'
coder = HTMLEntities.new
string = "<élan>"
coder.encode(string, &options)
{% endhighlight %} 

##### Decoding

You can decode HTML entities by calling decode method on HTMLEntities class.

{% highlight bash %}
require 'htmlentities'
coder = HTMLEntities.new
string = "&copy;"
coder.decode(string)
{% endhighlight %}

The various options and flavours in using the library can be found [here](http://htmlentities.rubyforge.org/ "htmlentities").

Happy coding 🙂