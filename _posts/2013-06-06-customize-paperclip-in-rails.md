---
layout: post
title: "Customize paperclip in rails"
permalink: customize-paperclip-in-rails
date: 2013-06-06 10:52:12
comments: true
description: "customize paperclip in rails"
keywords: "upload, imagemagick, resize, upload, image, gems"
categories: "rails"

tags:

---

In this post i would like to share various interesting paperclip options i’ve used so far to achieve upload functionality across multiple applications. For someone who doesn’t have any idea what Paperclip is about, Paperclip is an easy file attachment library for Active Record and is the most popular library in that category. More information about Paperclip can be found [here](https://github.com/thoughtbot/paperclip "Paperclip").

Ever wondered what does “#” and “>” signifies while specifying image dimensions using styles option ? Do you know that there are multiple other special characters that can be used ? “#” is an argument used by Paperclip to know whether or not you expect the pic to be cropped. The rest of the options are specified for Image geometry of Image magick which can be found [here](http://www.imagemagick.org/script/command-line-processing.php?ImageMagick=lj6pre8q2iautc3ch6nuph1fc2#geometry "image geometry options").

{% highlight bash %}
has_attached_file :logo, :styles => {:medium => ["400x400#", :jpg],
   :thumb => ["100x100#", :jpg],
   :slider => ["300x300#", :jpg]},
   :convert_options => { :medium => "-resize 135x135 -background white -gravity center -extent 135x135" },
:defaul_url => "/assets/default_logo.png"
{% endhighlight %}  

The nice thing is that the image will always be resized to fit in the given dimensions, without losing original aspect ratio, then it will fill the extra space (height or width depending on original aspect ratio) with a white background, all the while keeping the re-sized image in the centre of the final result.
