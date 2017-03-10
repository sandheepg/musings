---
layout: post
title: "Simplify dropdowns using chosen in rails"
permalink: simplify-dropdowns-using-chosen-in-rails
date: 2012-06-10 16:24:43
comments: true
description: "simplify dropdowns using chosen in rails"
keywords: "chosen, dropdown"
categories: "rails"

tags:

---

Did you ever thought that selecting one from a long list of options in a dropdown is a pain ? Did you ever thought that dropdowns are less user-friendly ? With the magic of [JQuery](http://jquery.com/ "Jquery") using dropdowns in your web pages is going to be fun again. [Chosen](http://harvesthq.github.com/chosen/ "Chosen") is a Javascript library that makes long dropdowns (select boxes) more user friendly.

In one of my recent projects, i need to implement a dropdown for my end user to select a product from a long list of products. Using a select tag just serves the purpose but i wanted to enhance its ease of use. I tried googling on this and zeroed in on the library Chosen. Below are a few good things about Chosen, i’ve considered before using it.
	
** Its incredibly simple to use. Just add a few lines of code to your webpages and you can breathe life into dropdowns.

** Chosen just replaces normal HTML fields, which means you don’t need to fight with it to make it work in the pages or to handle the data on the back end. Every thing works normally as you want them to.

** Chosen by default supports multiple select, optgroups, selected state and browser tab order.

** Chosen is fairly simple to customize. With out of the box support to most of the features, i didn’t see the need for much customization except for the styles as i see them fit.

** Chosen has support even for Prototype which means i can use the same for my other projects which uses Prototype library.

Chosen is available as a [gem](https://github.com/tsechingho/chosen-rails "Chosen") for Ruby on Rails which fits well with Asset Pipeline. Include Chosen gem in your Gemfile.

{% highlight bash %}
gem 'chosen-rails'
{% endhighlight %} 

and then run

{% highlight bash %}
bundle install
{% endhighlight %} 

Alternatively, you can install the gem by running

{% highlight bash %}
gem install chosen-rails
{% endhighlight %} 

Once the gem is installed, include chosen javascript assets to your manifest file. If you are using JQuery

{% highlight bash %}
//= require chosen-jquery
{% endhighlight %} 

In case of Prototype

{% highlight bash %}
//= require chosen-prototype
{% endhighlight %} 

Then, include Chosen stylesheet assets to your manifest file.

{% highlight bash %}
*= require chosen
{% endhighlight %} 

Specify **.chzn-select** as a class to dropdowns in your view. Activate the plugin for Jquery as

{% highlight bash %}
$(".chzn-select").chosen();
{% endhighlight %} 

In case of Prototype

{% highlight bash %}
new Chosen(some_form_element);
{% endhighlight %} 

That is it .. you have a nice user friendly dropdown on your website which your users love to use. Happy Coding!

