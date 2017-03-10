---
layout: post
title: "Using custom fonts in your website"
permalink: using-custom-fonts-in-your-website
date: 2012-05-15 15:44:59
comments: true
description: "using custom fonts in your website"
keywords: "fonts, typography, css"
categories: "howto"

tags:

---

For years, web designers struggled with having custom fonts on the web pages. They don’t have much options rather using limited web safe fonts. The only way they can do it that time is by using flash or by converting the text into image which is far from perfect solution. Web Typography is pretty simple now thanks to the popularity of CSS3. Now a days increasing number of browsers are supporting CSS3 which made web typography finally a reality.

Currently there are multiple services online like [Typekit](http://typekit.com/ "Typekit") which provides designers with wide options of fonts and customization. Typekit is from [Adobe](http://www.adobe.com/ "Adobe") and they offer these services with a near perfect pricing model. There are other free services like [Google web fonts](http://www.google.com/webfonts "Google web fonts"), [Font squirrel](http://www.fontsquirrel.com/ "Font Squirrel"), [Fonts.com](http://www.fonts.com/web-fonts "Web fonts") which allow the users to quickly find the fonts they want and integrate them into websites.

The CSS3 property that helps designers in implementing custom web typography is @fontface. Its not only amazing but is incredibly simple to use. Learn more about this [here](http://www.w3.org/TR/css3-webfonts/#font-descriptions).

Heading to the implementation, select the font to use from one of the services above. Download the font and specify the font in the stylesheet using @font-face. Now use the font in your stylesheet as normal as you use any other web safe font. Your custom font works like a charm now.

Due to average @font-face font file sizes and to keep load time to a minimum, its recommend to use it to the minimum (utmost 5 fonts).

You can also specify the @font-face declarations in a css file and import the same in your main css file in case you want to be more modular.

For full cross browser compatibility with @font-face, make sure you use each of the web font formats – .eot, .woff, .ttf, and .svg. The file formats required for @font-face can be generated on FontSquirrel.com’s @font-face generator. 

{% highlight bash %}
@font-face {
font-family: 'GeosansLightRegular';
src: url('geosanslight_1-webfont.eot');
src: url('geosanslight_1-webfont.eot?#iefix') format('embedded-opentype'),
url('geosanslight_1-webfont.woff') format('woff'),
url('geosanslight_1-webfont.ttf') format('truetype'),
url('geosanslight_1-webfont.svg#GeosansLightRegular') format('svg');
font-weight: normal;
font-style: normal;
}
 
p {
font-family: "GeosansLightRegular", sans-serif;
font-size: 12px;
}
{% endhighlight %} 

Hope this helps. Happy web pages 😉