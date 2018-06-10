---
layout: post
title:  "Creating NPM packages for Ionic plugins"
date:   2018-04-19 08:00:00
comments: true
categories: development, rxjs, reactive programming
---

The other day I had to figure out how to create private NPM packages for plugins, some of them used in Ionic 3/4 projects, hosted using a private Nexus server. 

Here are some of the information that ended up learning quite a bit from.

* Use [ng-packagr][ng-packagr] to create a plugin
    * Might be an [issue][ng-packagr-issue] for Ionic
* Scoped [NPM][npm-scope] packages
* [Nexus private registry][nexus-registry] setup
* How to make [Angular libraries][angular-libs] like a pro
* [Angular Package Format][apf]
* Peer dependencies[1][peer-1][2][peer-2] in NPM
* [semantic-release][semantic-release] with [CLI][semantic-release-cli] vs [standard][standard-version]

# Modules in Angular
* [Feature modules][feature-module] in Angular
    * Use `forRoot()` to make singleton services from inside modules.
[feature-module]: https://angular-2-training-book.rangle.io/handout/modules/feature-modules.html


[ng-packagr]: https://medium.com/@nikolasleblanc/building-an-angular-4-component-library-with-the-angular-cli-and-ng-packagr-53b2ade0701e
[ng-packagr-issue]: https://github.com/dherges/ng-packagr/issues/434
[nexus-registry]: https://blog.sonatype.com/using-nexus-3-as-your-repository-part-2-npm-packages
[npm-scope]: https://docs.npmjs.com/misc/scope#associating-a-scope-with-a-registry
[angular-libs]: https://www.youtube.com/watch?v=K4YMmwxGKjY
[apf]: https://docs.google.com/document/d/1CZC2rcpxffTDfRDs6p1cfbmKNLA6x5O-NtkJglDaBVs/edit
[peer-1]: https://stackoverflow.com/questions/18875674/whats-the-difference-between-dependencies-devdependencies-and-peerdependencies
[peer-2]: https://nodejs.org/en/blog/npm/peer-dependencies/
[semantic-release]: https://github.com/semantic-release/semantic-release
[semantic-release-cli]: https://github.com/semantic-release/cli
[standard-version]: https://github.com/conventional-changelog/standard-version/