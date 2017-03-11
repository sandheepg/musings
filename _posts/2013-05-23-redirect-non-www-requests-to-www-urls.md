---
layout: post
title: "Redirect non www requests to www urls"
permalink: redirect-non-www-requests-to-www-urls
date: 2013-05-23 19:05:34
comments: true
description: "redirect non www requests to www urls"
keywords: "www, server, htaccess, redirect"
categories: "apache"

tags:

---

In one of my recent projects, i’ve faced a situation where i need to redirect non-www traffic to a canonical www. For someone who don’t understand the issue, i want my users who type [http://foo.bar](http://foo.bar) in their browsers to be redirected to [http://www.foo.bar](http://www.foo.bar). The tried and tested way to achieve this redirect is through server configuration.

I am using Apache as my web server with Passenger module installed for the website in question. Here is the step-by-step procedure on how i did it.

Locate your apache configuration file. Usually it can be located at /etc/httpd/conf/httpd.conf (YMMV !) 

Ensure that mod_rewrite is installed (which is the case with most hosting providers).

Open the file using VI / VIM editor and switch to insert mode.

Locate the VirtualHost directive specified for the website in question.

Type the following rewrite rules inside the directive. 

{% highlight bash %}
<IfModule mod_rewrite.c>
  Options +FollowSymlinks
  RewriteEngine On
  RewriteCond %{HTTPS} !=on
  RewriteCond %{HTTP_HOST} !^www\..+$ [NC]
  RewriteRule ^ http://www.%{HTTP_HOST}%{REQUEST_URI} [R=301,L]
</IfModule>
{% endhighlight %} 

Restart apache and you are done.

Alternatively, you can create a .htaccess file at the root of your hosting and include the above rewrite rules in it.

The powerful Router in Rails 3 and above makes this trivial.

{% highlight rails %}
Foobar::Application.routes.draw do
  constraints(host: /^(?!www\.)/i) do
    match '(*any)' => redirect { |params, request|
      URI.parse(request.url).tap { |uri| uri.host = "www.#{uri.host}" }.to_s
    }
  end
 
  resource :foo_bar
  root :to => redirect('/foo_bar')
end
{% endhighlight %} 

{% highlight rails %}
Foobar::Application.routes.draw do
  constraints(host: /^www\./i) do
    match '(*any)' => redirect { |params, request|
      URI.parse(request.url).tap { |uri| uri.host.sub!(/^www\./i, '') }.to_s
    }
  end
 
  resource :foo_bar
  root :to => redirect('/foo_bar')
end
{% endhighlight %} 

