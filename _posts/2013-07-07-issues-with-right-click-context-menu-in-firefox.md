---
layout: post
title: "Issues with right click context menu in firefox"
permalink: issues-with-right-click-context-menu-in-firefox
date: 2013-07-07 11:01:24
comments: true
description: "issues with right click context menu in firefox"
keywords: "context, menu, right, click, mozilla, firefox"
categories: "browser, howto"

tags:

---

After updating Firefox browser to latest version (v20.0), the right click context menu is showing much more commands than before. Most of these commands are out of context and none of these seems to be working. After a little troubleshoot, i came to know that the issue is with incompatible version of the add-on Firebug.

Somehow, updating the Firebug add-on doesn’t seem to set things straight. So, i’ve uninstalled firebug and installed the latest version (1.11.2) which fixed the issue for me. If in case the issue still persists, try the following troubleshooting steps.


Back up all your bookmarks and other important information in your browser.

Go to Help  >> Troubleshooting Information

Click on Reset Firefox button in the top right box.

Click OK in the dialog box that appears.

This will also create a backup copy of your browser data on your desktop. (However its always advisable to have a copy of your own before starting troubleshooting)

This resets firefox with minimum defaults which should fix the issue in question.

Now try to install the required add-ons by clicking Tools >> Add-ons


