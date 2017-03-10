---
layout: post
title: "Setup rails on ubuntu using rvm"
permalink: setup-rails-on-ubuntu-using-rvm
date: 2012-05-23 15:57:02
comments: true
description: "Setup rails on ubuntu using rvm"
keywords: "installation, rvm"
categories: "ruby, rails, ubuntu"

tags:

---

In my previous [post](https://sandheepg.github.io/musings/setting-up-rails-in-ubuntu-1204) i’ve explained how to setup the ecosystem for Ruby on Rails on ubuntu 12.10. That includes installing Ruby, Rails, Gems and other necessary packages which lessen the pain while working with Ruby. The Ruby ecosystem is very dynamic and you will come across latest versions of the software every now and then which makes managing different versions a pain. Thankfully, there are awesome tools which takes the pain off our shoulders. One such tool is Ruby Version Manager ([RVM](https://rvm.io/)). Sometimes you might want to work on a project that require an older version of Ruby while you want the newer version for your latest project. RVM allows you to easily install, manage, and work with multiple ruby environments (multiple versions) on your machine. This tutorials helps you understand how to install RVM and installing Ruby 1.9.3 and Rails 3.2.6 using RVM.

Before installing RVM make sure you have necessary packages installed by running the following commands

{% highlight bash %}
sudo apt-get update
sudo apt-get install build-essential git-core curl
{% endhighlight %} 

Now we are ready to install RVM. Install the latest stable release version by running the following command.

{% highlight bash %}
curl -L get.rvm.io | bash -s stable
{% endhighlight %} 

This installs RVM in your home directory successfully. The following command adds a line at the very end of your bash profile instructed by RVM installation documentation which will load RVM.

{% highlight bash %}
echo '[[ -s "$HOME/.rvm/scripts/rvm" ]] && source "$HOME/.rvm/scripts/rvm"' >> ~/.bashrc
{% endhighlight %} 

Then you need to reload bashrc file with this small command.

{% highlight bash %}
. ~/.bashrc
{% endhighlight %} 

Now that RVM is installed and configured, we now need to install necessary packages before installing Ruby.These packages provide necessary support for working with Ruby. They can be installed at once by running this single long command in the terminal.

{% highlight bash %}
sudo apt-get install build-essential openssl libreadline6 libreadline6-dev curl git-core zlib1g zlib1g-dev libssl-dev libyaml-dev libsqlite3-dev sqlite3 libxml2-dev libxslt-dev autoconf libc6-dev ncurses-dev automake libtool bison libmysqlclient-dev libpq-dev
{% endhighlight %} 

Know the list of rubies RVM can install by running the command

{% highlight bash %}
rvm list known
rvm list # to know the list of rubies installed locally
{% endhighlight %} 

With RVM you can install Ruby interpreter on the fly with a simple command

{% highlight bash %}
rvm install 1.9.3
rvm install 1.9.3-p194 # you can even mention patch number
{% endhighlight %} 

UPDATE : Once you run the above command, particularly when installing latest versions of RVM, you might come across a message like the one below. Is it broken ? Need not worry. Its just a change in the RVM configuration. All you have to do is run the command rvm autolibs enable and leave the rest to RVM.

{% highlight bash %}
Searching for binary rubies, this might take some time.
Installing requirements for ubuntu, might require sudo password.
Skipping `apt-get update` make sure your system is up to date.
RVM autolibs is now configured with mode '2' => 'check and stop if missing',
please run `rvm autolibs enable` to let RVM do its job or run and read `rvm autolibs [help]`
or visit <a href="https://rvm.io/rvm/autolibs" target="_blank">https://rvm.io/rvm/autolibs</a> for more information.
Missing required packages: libgdbm-dev, libffi-dev.
RVM autolibs is now configured with mode '2' => 'check and stop if missing',
please run `rvm autolibs enable` to let RVM do its job or run and read `rvm autolibs [help]`
or visit <a href="https://rvm.io/rvm/autolibs" target="_blank">https://rvm.io/rvm/autolibs</a> for more information.
{% endhighlight %} 

Once Ruby runtime is installed you can instruct RVM to use it by running

{% highlight bash %}
rvm use 1.9.3
{% endhighlight %} 

Running **ruby -v** or **which ruby** will give the path of Ruby executable installed under RVM.

To make a Ruby version default run

{% highlight bash %}
rvm --default use 1.9.3-p194
{% endhighlight %} 

To use system installed Ruby, run

{% highlight bash %}
rvm use system
{% endhighlight %} 

Now running **which ruby** shows the path of Ruby executable installed outside RVM.

Gems are package managers in Ruby. As we’ve just installed Ruby using RVM the gems installed in the system (if they are already) are not available to RVM. You need to again install them using the following commands. Make sure you don’t use **sudo** before the command as RVM is installed in your home directory.

{% highlight bash %}
gem install rails -v 3.2.3
gem install mysql2
gem install pg
{% endhighlight %} 

There is another interesting feature in RVM called gemsets which helps to manage separate gemsets for each of your rails applications. Using this feature you can have separate independent ruby setups. To give a use case, if you need to check different versions of the same gem in a application, you can create two gemsets and install the gem with different versions in each gemset. Then load the gemset and test it on your application. The following steps gives you a heads up in creating and using gemsets. More can be found in RVM website.

{% highlight bash %}
rvm 1.9.3 # short cut for rvm use 1.9.3. Load the ruby library first.
rvm gemset create <gemset name>
rvm gemset use <gemset name>
gem install <gem name> # installs the gem in the current gemset
rvm gemset name # gives the name of current gemset
rvm gemset list # lists gemsets under the current ruby interpreter
{% endhighlight %} 

This marks the end of tutorial. Happy Coding !!










