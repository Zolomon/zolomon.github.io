---
layout: post
title: "Emacs on Windows 7"
date: 2015-03-25 23:00:00
comments: true
categories: development,emacs
---

# Links during my adventures to configure Emacs for Windows 7

The goal is the make emacs a more comfortable experience than VS2013 on Windows 7.

* [Prelude](http://github.com/bbatsov/prelude): Starter pack
* [Omnisharp](http://www.omnisharp.net/): for C# & .NET
* [Omnisharp-server](https://github.com/OmniSharp/omnisharp-server): Server for omnisharp
* [fsharpbinding](https://github.com/fsharp/fsharpbinding): F# language support for open editors

Found solutions to problems that arose: 

* When using `C-c C-c` to compile, there were some problems with the paths.
    * First I had to setup PATH variables for `MSBuild.exe` and `Fsc.exe`, and then figure out how 
   `emacs` [prefers paths](http://stackoverflow.com/questions/3981850/running-process-that-has-space-characters-in-its-path-name-with-emacs-on-windows) with spaces in Windows.
