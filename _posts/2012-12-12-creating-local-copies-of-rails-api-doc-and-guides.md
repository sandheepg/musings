---
layout: post
title: "Creating local copies of rails api doc and guides"
permalink: creating-local-copies-of-rails-api-doc-and-guides
date: 2012-12-12 18:17:32
comments: true
description: "creating local copies of rails api doc and guides"
keywords: "api, documentation, docs"
categories: "rails"

tags:

---

If you are a programmer, am sure you know the importance of API documentation no matter what language you are using and what level of expertise you have. I personally have API documentation bookmarks of all the technologies i use for my quick reference. Still i prefer to have a local copy of the same and believe many of you would also find it useful.

Being a Rails programmer, i always prefer to have local copies of official Ruby on Rails API documentation and Rails Guides for well known reasons. Rails Guides tops the list of authentic Rails resources on any given day. In this article i will show you how to create local copies for them.

##### Rails API doc

Make sure you have Ruby and rails installed on your machine. If you don’t have bundler gem installed already, install it using the below command.

{% highlight bash %}
gem install bundler
{% endhighlight %} 

Next step is to clone Rails git repository to your machine as follows (assuming you have git installed already)

{% highlight bash %}
git clone http://github.com/rails/rails.git
{% endhighlight %} 

Enter into the directory and run

{% highlight bash %}
bundle install --without db
{% endhighlight %} 

The above command will install necessary ruby gems. Now run the following command to generate API doc under the doc folder.

{% highlight bash %}
bundle exec rake rdoc
{% endhighlight %} 

##### Rails Guides

Create a new rails project. Rails guides depends on a gem called RedCloth. Add it to the Gemfile. Once that is done run the following commands to generate rails guides under the doc folder.

{% highlight bash %}
bundle install
rake doc:guides
{% endhighlight %} 

You can also create local copy of rails guides by following the below steps.

{% highlight bash %}
git clone git://github.com/rails/rails.git
cd rails
git checkout origin/3-0-stable -b 3-0-stable
cd railties/guides
ruby rails_guides.rb
{% endhighlight %} 

This generates rails guides documentation under output folder. There are other blogs which have PDF versions of Rails Guides, one for every section. They might not have the latest versions but can be given a try. (I haven’t checked them .. YMMV !!). You can find them [here](http://www.cs.kyoto-wu.ac.jp/~konami/documents/Rails/RailsGuides/) and [here](http://veerasundaravel.wordpress.com/2011/01/07/pdf-documents-from-ruby-on-rails-guides/)

##### Gem docs

A little known feature that comes with gem is the ability to serve RDoc info for all gems installed on your system. In the terminal, run

{% highlight bash %}
gem server
{% endhighlight %} 

You will get output like

{% highlight bash %}
server started on http://localhost:8808
{% endhighlight %} 

Just visit it and you will find a list of gems, click on any one to go through the RDoc!

Happy Coding :) 





