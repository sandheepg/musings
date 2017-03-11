---
layout: post
title: "Installing skype on ubuntu"
permalink: installing-skype-on-ubuntu
date: 2013-08-08 11:08:03
comments: true
description: "installing skype on ubuntu"
keywords: "installation, skype, voip"
categories: "ubuntu"

tags:

---

Skype is a Voice over IP (VoIP) that lets you make free calls over the internet. It allows people to communicate by messaging, voice and video calling. Millions of individuals and corporations use Skype to stay in touch and collaborate with each other. Skype is available for multiple platforms including ubuntu. Its increasingly used these days by developers / designers / managers / freelancers thanks to its additional features like Flie sharing, Screen sharing and Video conferencing.

To install Skype on ubuntu, open the terminal and run the following commands in it. Copy and paste to avoid typos.

{% highlight bash %}
wget -O skype http://download.skype.com/linux/skype-ubuntu-precise_4.1.0.20-1_i386.deb
sudo dpkg -i skype
sudo apt-get -f install && sudo rm skype
{% endhighlight %} 

After installing Skype, go to Ubuntu Dash and open it. Enter your Skype account credentials if you already have one. Else, you can either create a free account with Skype or login with your existing Microsoft account (Hotmail/Live/Outlook/XBox).

Happy Skyping !!
