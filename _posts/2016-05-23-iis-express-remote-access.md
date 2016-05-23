---
layout: post
title:  "Setting up IIS Express for Remote Access"
date:   2016-05-23 09:00:00
comments: true
categories: development, windows, umbraco
---

In order to setup *IIS Express* for remote access over LAN I followed the instructions here:

[http://johan.driessen.se/posts/Accessing-an-IIS-Express-site-from-a-remote-computer](http://johan.driessen.se/posts/Accessing-an-IIS-Express-site-from-a-remote-computer)


Then I figured out that I had to use the group "alla" since my OS locale was Swedish:

[http://stackoverflow.com/questions/18855607/create-sddl-failed-error-1332#comment33133168_18856394](http://stackoverflow.com/questions/18855607/create-sddl-failed-error-1332#comment33133168_18856394)


Since I use Visual Studio I had to use `iisexpress-proxy` as a last step:

[https://github.com/icflorescu/iisexpress-proxy](https://github.com/icflorescu/iisexpress-proxy)

Here is an example:

`iisexpress-proxy 64764 to 81`.

This is also how I managed to get `Umbraco` running in `development`, `staging` and `production` separated environments due to `Umbraco Courier 2` not being very well designed.
