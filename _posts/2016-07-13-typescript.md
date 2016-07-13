---
layout: post
title:  "TypeScript"
date:   2016-07-13 07:00:00
comments: true
categories: development, typescript, NodeJs
---

Here is the general toolchain I use for my current TS (TypeScript) projects:

* [TypeScript][typescript] - The TypeScript compiler
* [typings][typings] - Type definition manager
* [Type Doc][typedoc] - Documentation generator
* [Require.js][requirejs] - AMD style module manager, used to cope with
  dependencies inside the browser

Browser front-end:

* [Angular.js][angular.js] - Single page application framework

Optional when working with a larger team:

* [TSLint][tslint] - Style convention verifier

For [Node.JS][nodejs] projects we use:

* [npm][npm] - package manager for JS libraries with accompanying
  [package.json][package.json] configuration of projects. `"scripts"` is
  used for build tasks instead of gulp.

Real-time communication:

* [socket.io][socket.io] - Similar to SignalR for .NET, provides a near
  real-time network solution over TCP. High productivity.


[typescript]:     http://www.typescriptlang.org/
[typings]:        https://github.com/typings/typings
[typedoc]:        http://typedoc.io/
[requirejs]:      http://requirejs.org/
[tslint]:         https://github.com/palantir/tslint
[nodejs]:         https://nodejs.org/en/
[npm]:            https://www.npmjs.com/
[package.json]:   https://docs.npmjs.com/files/package.json
[socket.io]:      http://socket.io/
[angular.js]:     https://angularjs.org/
