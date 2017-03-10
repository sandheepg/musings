---
layout: post
title: "Setting up rails in ubuntu 12.04"
permalink: setting-up-rails-in-ubuntu-1204
date: 2012-05-12 10:05:19
comments: true
description: "setting up rails in ubuntu 12.04"
keywords: "installation"
categories: "ruby, rails, ubuntu"

tags:

---

Ubuntu 12.04 LTS, code named as Precise Pangolin is the latest release from Ubuntu getting rave reviews from both users and critics. There are many reasons to love this version be it thousands of free apps, free upgrades for life, enhanced security, features like HUD, Video lens and above all Unity interface replacing traditional GNOME. You can download Precise Pangolin from the ubuntu website [here](http://http//www.ubuntu.com/download "Ubuntu").

Once ubuntu is installed on your machine, you can go ahead and update your software using the Update manager tool. After this run the following commands to make sure everything is updated.

{% highlight bash %}
sudo apt-get update && sudo apt-get upgrade
{% endhighlight %} 

Once the software is updated, browse through lot of free apps using Ubuntu Software Centre and install apps of your choice. You might as well want to start with Restricted Extras which installs dvd-codecs, flash, MS core fonts etc. which are licensed by third parties and can’t be shipped with ubuntu. Create a directory setup-installers in your home to save any installers downloaded from internet. Follow the instructions given below to get start with programming in Rails on Ubuntu.

The following commands are necessary to open, compile, install any downloaded packages. Open the terminal now and type the  commands. Copy and paste to minimize typos.

{% highlight bash %}
sudo apt-get install libreadline-dev
sudo apt-get install openssl libssl-dev
sudo apt-get install zlib1g-dev
sudo apt-get install libmysqlclient-dev
sudo apt-get install g++
{% endhighlight %} 

Ruby, Ruby gems or any Ruby related packages must not be installed using apt-get as it leads to unwanted headaches. The best way to install Ruby is installing from source. Alternatively you can use RVM and install Ruby as explained [here](https://sandheepg.github.io/musings/setup-rails-on-ubuntu-using-rvm "use rvm to set up rails on ubuntu"). Find stable version of Ruby [here](ftp://ftp.ruby-lang.org/pub/ruby/1.9/ "Ruby")  and download it to setup-installers directory.

Extract the tar.gz file using the command

{% highlight bash %}
tar zxpvf file_name
{% endhighlight %} 


This extracts contents from the archive into a directory.

Go to the extracted directory from the terminal and run the following commands to compile and install Ruby.

{% highlight bash %}
./configure --prefix=/usr
make
make install
{% endhighlight %} 

Run *ruby -v*  to make sure Ruby is installed and to know its version.

Gems are Ruby Package managers. You can download them [here](http://rubygems.org/pages/download).

Extract the files using *tar zxpvf file_name* and run setup.rb file using the following command.

{% highlight bash %}
sudo ruby setup.rb
{% endhighlight %} 

Run *gem -v*  to know the version of Ruby gems installed. Run gem list to list all the gems installed locally.

Ruby on rails, the web application framework built using Ruby is available as a Ruby gem. Run sudo gem install rails to install the latest version of rails. In case you want to install a specific version of rails, use -v prefix like *sudo gem install rails -v=3.1.2*

To install MySQL, go to Ubuntu Software center, Search for MySQL and install MySQL server and client. Follow the wizards to configure the root user password for MySQL.

MySQL connector for Ruby is available as a gem which can be installed using the command sudo gem install mysql2

NodeJS can be installed using the commands below.

{% highlight bash %}
sudo apt-get install python libssl-dev -y
cd /usr/local/src
sudo mkdir node
cd node
sudo wget http://nodejs.org/dist/v0.10.4/node-v0.10.4.tar.gz
sudo tar -xzvf node-v0.10.4.tar.gz
cd node-v0.6.17
sudo ./configure
sudo make
sudo make install
{% endhighlight %} 

To install npm, a package manager for node run the following command in the terminal.

{% highlight bash %}
curl http://npmjs.org/install.sh | sudo sh
{% endhighlight %} 

To install Coffescript, run    

{% highlight bash %}
sudo npm install -g coffee-script
{% endhighlight %} 

This marks the end of this post. Hope this is helpful. Love to hear more from you in the comments section.

