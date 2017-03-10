---
layout: post
title: "Issues with broadcom wireless in ubuntu 12.10"
permalink: issues-with-broadcom-wireless-in-ubuntu-1210
date: 2012-10-10 16:56:22
comments: true
description: "issues with broadcom wireless in ubuntu 12.10"
keywords: "wireless, broadcom"
categories: "ubuntu"

tags:

---

Canonical have launched Ubuntu 12.10 with the slogan “Avoid The Pain of Windows 8“. This latest version sports many cool upgrades like Unity Previews, Theme tweaks, and Unity Webapps to name a few. You can download it from the [Ubuntu](http://www.ubuntu.com/ "Ubuntu") website as usual. In case you want to upgrade from Ubuntu 12.04 to 12.10 run your Software Updater. This should prompt you for a upgrade to 12.10. In case you still unable to see it, check the updates tab and select *Any New version* in the last drop down. Re-launch the Software updater and you should now see prompt to upgrade to 12.10.

Make sure you are connected to internet with decent speed. Its always recommended to take a backup of your existing data before proceeding for an update. Click on the upgrade button and grab a coffee. It will take around 30-45 minutes for the upgrade to finish (YMMV). Reboot the system and you are greeted with brand new version of your favourite OS.

Take a quick tour and am sure you will love the features. If you find something is breaking .. no issues the os is backed with a community who posts regular fixes and tweaks which should fix your issues in no time.

I had my share of problems when updated to Ubuntu 12.10 from 12.04. My wireless stopped working. I couldn’t connect to any of the wireless networks. I’ve ran apt-get update without much luck. With quick googling i’ve found the fix. Follow the below steps to fix the issue with the Broadcom wireless driver.


** Uninstall all wireless drivers. Use Synaptic Package Manager to do it for you.

** If not already installed, you can install Synaptic by running
{% highlight bash %}
sudo apt-get install synaptic
{% endhighlight %} 

** In Synaptic, do a search for bcm. All boxes with a green box next to them select for complete removal.

** Then mark __firmware-b43-lpphy-installer__ and accept the recommended for installation.

** Click on Apply.

** Reboot the system once done.

You should have a working wireless now.
Cheeers 😉


