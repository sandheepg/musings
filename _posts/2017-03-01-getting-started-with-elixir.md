---
layout: post
title: "Getting started with Elixir"
permalink: getting-started-with-elixir
date: 2017-03-01 20:46:44
comments: true
description: "getting started with elixir"
keywords: "elixir, erlang, installation, mac, linux, homebrew"
categories: "installation"

tags:

---

Elixir is a dynamic, functional, concurrent programming language that is built on top of Erlang and runs on its VM. You can get more details about Elixir [here](https://en.wikipedia.org/wiki/Elixir_(programming_language) "Wikipedia") and [here](http://elixir-lang.org "Official site")

In order to install Elixir, you must have Erlang installed. The following instructions will guide you on how to install Elixir on different OS.

For Mac OSX users

{% highlight bash %}
# update brew packages before installing Erlang.
brew update
# OSX 10.7 and later might need autoconf. Check for its presence by running
which autoconf 
# if not installed, run
brew install autoconf

# install Erlang
brew install erlang
# confirm its installed in the correct location by running
which erl
# start Erlang from your terminal with
erl

#install Elixir
brew install elixir

{% endhighlight %} 

For Linux users

{% highlight bash %}
# update packages and install required dependencies.
sudo apt-get update
sudo apt-get install build-essential autoconf libncurses5-dev openssl libssl-dev fop xsltproc unixodbc-dev git

# download Basho's patched version of Erlang and compile
wget http://s3.amazonaws.com/downloads.basho.com/erlang/otp_src_R16B02-basho10.tar.gz
tar zxvf otp_src_R16B02-basho10.tar.gz
cd OTP_R16B02_basho10
./otp_build autoconf
./configure && make && sudo make install

# confirm its installed in the correct location by running
which erl
# start Erlang from your terminal with
erl

#install Elixir
sudo apt-get install elixir


{% endhighlight %} 

