---
layout: post
title: "Installing wkhtmltopdf on centos"
permalink: installing-wkhtmltopdf-on-centos
date: 2012-11-11 18:07:53
comments: true
description: "installing wkhtmltopdf on centos"
keywords: "centos"
categories: "ubuntu, linux"

tags:

---

Wkhtmltopdf is s simple shell utility to convert html to pdf using the webkit rendering engine. You can find the official documentation [here](http://http//code.google.com/p/wkhtmltopdf/ "wkhtmltopdf"). This is one of the important dependencies for software related to PDFs. In this article i will show you how to install this utility on a CentOS machine.

Grab the installer from the website by running the command below. 

{% highlight bash %}
wget http://wkhtmltopdf.googlecode.com/files/wkhtmltopdf-0.10.0_rc1-static-amd64.tar.lzma
{% endhighlight %} 

Once downloaded, unzip the folder. 

{% highlight bash %}
xz -d wkhtmltopdf-0.10.0_rc1-static-amd64.tar.lzma
tar -xvf wkhtmltopdf-0.10.0_rc1-static-amd64.tar
{% endhighlight %} 

Copy the extracted folder to /usr/local/bin      

{% highlight bash %}
cp wkhtmltopdf-amd64 /usr/local/bin/wkhtmltopdf
{% endhighlight %} 

Check if the installation is successful by typing the following commands. 

{% highlight bash %}
which wkhtmltopdf
wkhtmltopdf --help
{% endhighlight %} 

You can test the utility by converting a HTML page to a PDF. 
 
{% highlight bash %}
wkhtmltopdf www.google.com mysearchengine.pdf
{% endhighlight %} 

You can also refer documentation [here](http://www.tecmint.com/install-wkhtmltopdf-html-page-to-pdf-converter-in-rhel-centos-fedora/) and [here](http://linuxdrops.com/install-snorby-for-snort-and-sagan/) for installation.

In case you want to install the utility on an Ubuntu machine run

{% highlight bash %}
sudo apt-get install wkhtmltopdf
{% endhighlight %} 

Happy coding !! 



 

