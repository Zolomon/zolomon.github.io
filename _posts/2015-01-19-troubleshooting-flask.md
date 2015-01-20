---
layout: post
title: "Troubleshooting Flask+uWSGI+NGINX"
date:  2015-01-20 12:29:00
comments: true
categories: development,flask
---

Obstacles I met and climbed over while trying to deploy a simple Flask application with uWSGI & NGINX.

*  `strace` was very helpful in debugging both `nginx` and `uwsgi`:

    ```sudo strace `pidof nginx | sed 's/\([0-9]*\)/-p \1/g'` ``` for example will start a single strace for multiple processes with the same name.
*  Prefer to use `.ini` files for uwsgi, instead of `xml`.

    `.ini` seems to be a lot more common than `.xml`.
*  Permissions are important to get right!

    Create a new user for your front-end stuff and ensure that it only has access to the front-end server etc.
