---
layout: post
title: "Displaying indian rupee sign in rails views"
permalink: displaying-indian-rupee-sign-in-rails-views
date: 2013-01-01 18:36:42
comments: true
description: "displaying indian rupee sign in rails views"
keywords: "rupee, currency, inr"
categories: "rails"

tags:

---

The Indian Rupee sign (₹) is the currency sign for India. Though its relatively new, its been widely used to display indian currency on web. Various solutions facilitate the usage of this new symbol on web such as [Webrupee](http://webrupee.com/ "webrupee") trying to make it  first class citizen in the currency world. The Unicode technical committee accepted the proposed code position U+20B9 for the currency sign. To use the sign in your rails views and for that matter any HTML page, use the below HTML entity code.

{% highlight bash %}
& #8377;
{% endhighlight %} 

Alternatively, here is the tried and tested way to display the sign using @font-face rule of CSS3. Add the below code to your CSS file.

{% highlight css %}
@font-face {
font-family: "WebRupee";
font-style: normal;
font-weight: normal;
src: local("WebRupee"), url("http://cdn.webrupee.com/WebRupee.V2.0.ttf") format("truetype"), url("http://cdn.webrupee.com/WebRupee.V2.0.woff") format("woff"), url("http://cdn.webrupee.com/WebRupee.V2.0.svg") format("svg");
}
.WebRupee {
font-family: 'WebRupee';
}
{% endhighlight %} 

Create a helper method to convert any number to indian currency.

{% highlight ruby %}
def number_to_indian_currency(number, html=>true)
txt = html ? content_tag(:span, 'Rs.', :class => :WebRupee) : 'Rs.'
"#{txt} #{number.to_s.gsub(/(\d+?)(?=(\d\d)+(\d)(?!\d))(\.\d+)?/, "\\1,")}"
end
{% endhighlight %} 

To display indian currency in your views, simply call the above helper method.

{% highlight rails %}
<%= raw number_to_indian_currency (number) %>
{% endhighlight %} 

Happy coding 🙂







