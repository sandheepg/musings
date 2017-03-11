---
layout: post
title: "Installing apache php mysql on ubuntu"
permalink: installing-apache-php-mysql-on-ubuntu
date: 2013-09-09 11:12:22
comments: true
description: "installing apache php mysql on ubuntu"
keywords: "installation, lamp, mysql, apache, php"
categories: "ubuntu"

tags:

---

In this article, i will guide you through the steps for installing apache, mysql and php on ubuntu and kick start some php development. These  are the individual software in the ubiquitous LAMP stack. More on this can be found [here](http://en.wikipedia.org/wiki/LAMP_(software_bundle) "LAMP software bundle").

MySQL is the most used open source RDBMS. To install MySQL, go to Ubuntu Software Center and search for MySQL. You can see MySQL Server and MySQL Client in the search results. Click on install against MySQL Server. It prompts for password for the default root user. Give the desired password and click on Ok. This installs the server and configures the same. Once done, click install against MySQL Client. You can now check MySQL installation by typing the following

{% highlight bash %}
which mysql # /usr/bin/mysql
mysql -u root -p<root-password> # login to mysql terminal
{% endhighlight %} 

Alternatively, to install MySQL using apt-get type the following

{% highlight bash %}
sudo apt-get install mysql-server mysql-client
{% endhighlight %} 

Apache is a web server software which is widely used in the industry. Apache2 is available as a Ubuntu package. You can install apache by running the following command.

{% highlight bash %}
sudo apt-get install apache2
{% endhighlight %} 

This installs apache with default modules. Once the installation is done, test Apache by typing [http://localhost](http://localhost) in your browser. You should see Apache default page which reads It Works !

Now its time to install Php software on your machine. To install Php and its Apache module type the following

{% highlight bash %}
sudo apt-get install php5 libapache2-mod-php5 php5-mysql
/etc/init.d/apache2 restart # to restart apache server
{% endhighlight %} 

The Document root of the default website is /var/www. To test Php installation, create a file called info.php using sudo touch var/www/info.php and paste the below content in it.

{% highlight bash %}
<?php echo phpinfo(); ?>
{% endhighlight %} 

When you call the page in browser using [http://localhost/info.php](http://localhost/info.php) it displays information regarding the php installation. Finally, to install PhpMyAdmin, a web interface to manage MySQL, type

{% highlight bash %}
sudo apt-get install phpmyadmin
# select apache2 as server and option "No" when prompted to configure default database during installation.
{% endhighlight %} 

Once installed, you can access it using the url [http://localhost/phpmyadmin](http://localhost/phpmyadmin)

In case you find any trouble accessing PhpMyAdmin using the above url troubleshoot using the commands below

{% highlight bash %}
# open apache configuration file
sudo vim /etc/apache2/apache2.conf
# add the below line somewhere
Include /etc/phpmyadmin/apache.conf
{% endhighlight %} 

Restart Apache once the changes are done.

{% highlight bash %}
sudo service apache2 restart
{% endhighlight %} 

And now you are all set to kick start your Php development.

Quick Tip : In case you need other modules for your Php development use the below commands to locate and install

{% highlight bash %}
sudo apt-cache search php5 # lists all available php5 modules
sudo apt-get install <module 1> <module 2> .. # install desired modules
sudo /etc/init.d/apache2 restart # restart apache
{% endhighlight %} 

Happy Coding 🙂