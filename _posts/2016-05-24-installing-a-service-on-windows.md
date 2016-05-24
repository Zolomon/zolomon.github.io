---
layout: post
title:  "Installing a Service on Windows"
date:   2016-05-24 09:00:00
comments: true
categories: development, windows, .NET
---

To install a service written in *.NET* on the local machine do the following:

* `sc delete <service-name>`

* `sc create <service-name> binPath= <absolute path to service file.exe>`

Sometimes you might need to close `ProcessExplorer.exe` or the `Services` processes in order to be able to delete. Do this if you get error codes like `1072` during deletion.
