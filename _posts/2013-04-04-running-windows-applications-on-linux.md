---
layout: post
title: "Running windows applications on linux"
permalink: running-windows-applications-on-linux
date: 2013-04-04 18:58:16
comments: true
description: "running windows applications on linux"
keywords: "wine, linux"
categories: "ubuntu, windows"

tags:

---

When i started transitioning from windows to linux a few years ago, i used to have many doubts in my mind. I used to wonder what software to use for common tasks. Then i came across [osalt](http://www.osalt.com/ "os alternative") which answered most of my questions.In that site, you can enter the name of the windows application and it will list all the open source alternatives that provide similar functionality. If you cannot find a suitable open source alternative or you are obsessed with a specific windows software, then installing windows application on linux is the only option you are left with.Yes, i know using VM ware / Virtual Machine is also an alternative but in most cases its considered as an overkill. There are many softwares available online, most of them free, which enables to run windows applications on linux. [Wine](http://www.winehq.org/ "wine software") is one such software that stands out tall.

Wine is an open source implementation of the Windows API in unix. You can consider wine as a compatibility layer for running windows programs. Installing wine software on linux is documented in detail in its [website](http://www.winehq.org/ "wine software"). If you are running ubuntu wine can be installed by running the following commands.

{% highlight bash %}
sudo add-apt-repository ppa:ubuntu-wine/ppa
sudo apt-get update
sudo apt-get install wine
{% endhighlight %} 

Once wine is installed successfully, download the setup file for the windows software of your choice and right click on the file to open with “Wine Windows Program Loader“. Run the wizard and the software will be installed in your machine. Once you have wine on your machine, you can access your favorite windows applications right from your linux machine. But then, you are forced to download setup installers for all the softwares you wanted to install on wine. To overcome this, you can look at [Playonlinux](http://www.playonlinux.com/en/ "play on linux").

Playonlinux is a piece of software which lets you to easily install numerous apps designed to run with windows. Playonlinux mainly relies on Wine. You can install Playonlinux using the instructions specified in this blog [post](http://www.n00bsonubuntu.net/content/how-to-install-playonlinux-on-ubuntu-12-04/ "install play on linux"). In case you are using ubuntu, you can install Playonlinux from Ubuntu software centre. Once installed, you can search for your desired software in Playonlinux and mark it for install.

> “The only source of knowledge is experience – Albert Einstein”
