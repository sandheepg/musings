---
layout: post
title: "Send html emails in php using gmail smtp"
permalink: send-html-emails-in-php-using-gmail-smtp
date: 2017-03-05 00:44:08
comments: true
description: "send html emails in php using gmail smtp"
keywords: "email, php, html, contact, gmail"
categories: "utilities, productive"

tags:

---

Here is a simple one page Contact form example written in PHP

{% highlight php %}
<?php

require_once('class.phpmailer.php');

#  Functions to filter user inputs
function filterName($field){
    $field = filter_var(trim($field), FILTER_SANITIZE_STRING);
        if(filter_var($field, FILTER_VALIDATE_REGEXP, array("options"=>array("regexp"=>"/^[a-zA-Z\s]+/")))){
        return $field;
    }else{
        return FALSE;
    }
}    
{% endhighlight %} 
