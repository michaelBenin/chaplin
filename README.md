![Chaplin](http://s3.amazonaws.com/imgly_production/3401027/original.png)

# An Application Architecture Using Backbone.js

## Introduction

Chaplin is an architecture for JavaScript applications using the [Backbone.js](http://documentcloud.github.com/backbone/) library.

* [Support and Help](#support-and-help)
* [Commercial Support and Training](#commercial-support-and-training)
* [Key Features](#key-features)
* [Motivation](#motivation)
* [Dependencies](#dependencies)
* [Downloading Chaplin](#downloading-chaplin)
* [Building Chaplin](#building-chaplin)
* [Running the Tests](#running-the-tests)
* [Boilerplate](#boilerplate)
* [Examples](#examples)
* [Documentation](#documentation)
* [The Cast](https://github.com/chaplinjs/chaplin/blob/master/AUTHORS.md#the-cast)
* [The Producers](https://github.com/chaplinjs/chaplin/blob/master/AUTHORS.md#the-producers)

## Documentation and Support

* We’re working on a [comprehensive documentation and class reference](https://github.com/chaplinjs/chaplin/tree/master/docs) on Github.
* For general support and discussion, there’s a [Google Group](https://groups.google.com/forum/?hl=en&fromgroups#!forum/chaplin-js), a [forum on ost.io](http://ost.io/chaplinjs/chaplin) and an IRC channel `#chaplinjs` on [Freenode](http://webchat.freenode.net?channels=chaplinjs).
* If you’d like to report a bug or propose a feature, please use the [Github issues](https://github.com/chaplinjs/chaplin/issues). The issue tracker can also be used for general questions and task management.
* [Follow Chaplin.js on Twitter](https://twitter.com/chaplinjs) to get updates on new versions, major changes and the ongoing development.

## Commercial Support and Training

[9elements](http://9elements.com/), one of the creators of Chaplin, is offering commercial support and training for Chaplin and Backbone-based JavaScript applications. 9elements is a software and design agency located in Berlin and Bochum, Germany. Send us a mail for more information: [contact@9elements.com](mailto:contact@9elements.com).

---

## Key Features

* CoffeeScript class hierarchies as well as object composition
* Module encapsulation and lazy-loading using AMD modules
* Cross-module communication using the Mediator and Publish/Subscribe patterns
* Introducing Controllers that represent UI screens
* Rails-style declarative routes that map URLs to controller actions
* A route dispatcher and a top-level view manager
* Extended model, view and collection classes to avoid repetition and enforce conventions
* Strict memory management and object disposal
* A collection view for easy and intelligent list rendering

## Motivation

![Modern Times](http://s3.amazonaws.com/imgly_production/3359809/original.jpg)

While developing several web applications using Backbone.js, we felt the need for conventions on how to structure such applications. Backbone is an easy starting point, but provides only basic, low-level patterns. Especially, Backbone provides little to structure an actual application. For example, the famous “[Todo list example](http://todomvc.com/)” is not an application in the strict sense nor does it teach best practices how to structure Backbone code.

Backbone doesn’t intend to be an all-round [framework](http://stackoverflow.com/questions/148747/what-is-the-difference-between-a-framework-and-a-library) so it’s not appropriate to blame Backbone for these deliberate limitations. Nonetheless, most Backbone use cases need a sophisticated application architecture.

This is where Chaplin enters the stage. Chaplin is derived from the codebase of [moviepilot.com](http://moviepilot.com/), a real-world single-page application. It draws attention to the top-level architecture: everything above simple routing, individual models, views and their binding.

## Dependencies

Chaplin depends on the following libraries:

* [Backbone](http://documentcloud.github.com/backbone/) (> 0.9.2)
* [Underscore](http://documentcloud.github.com/underscore/) (> 1.4.2) or [lodash](http://lodash.com/) (> 0.8.2)
* [jQuery](http://jquery.com/) (> 1.8.2) or [Zepto](http://zeptojs.com) (> 1.0rc1)

If you’ll be using AMD version, you will also need an AMD module loader like [RequireJS](http://requirejs.org/), [Almond](https://github.com/jrburke/almond) or [curl](https://github.com/cujojs/curl) to load Chaplin and lazy-module application modules

## Downloading Chaplin

[Download the latest release on Chaplinjs.org](http://chaplinjs.org/#downloads). See above on how to compile from source manually.

## Building Chaplin

The Chaplin source files are originally written in the [CoffeeScript](http://coffeescript.org/) meta-language. However, the Chaplin library file is a compiled JavaScript file which defines the `chaplin` module.

Our build script compiles the CoffeeScripts and bundles them into one file. To run the script, follow these steps:

1. Download and install [Node.js](http://nodejs.org/).
2. Open a shell (aka terminal aka command prompt) and type in the commands in the following steps.
3. Install the Node packages for CoffeeScript and UglifierJS globally.

   ```
   sudo npm install -g coffee-script
   sudo npm install -g uglify-js
   ```

   On Windows, you can omit the `sudo` command at the beginning.

4. Install the Node package ShellJS normally.

   ```
   npm install shelljs
   ```

5. Start the build:

   ```
   cake build
   ```

This creates two directories:

* `./build/amd/` with a build using the AMD module style
* `./build/commonjs/` with a build using the CommonJS module style

These directories contain four files each:

* `chaplin-VERSION.coffee` – The Chaplin library as a CoffeeScript file.
* `chaplin-VERSION.js` – The library as a compiled JavaScript file.
* `chaplin-VERSION-min.js` – Minified. For production use you should pick this.
* `chaplin-VERSION-min.js.gz` – Minified and GZip-compressed.

## Running the Tests

Chaplin aims to be fully unit-tested. At the moment most of the modules are covered by Mocha tests.

How to run the tests:

1. Download and install [Node.js](http://nodejs.org/).
2. Open a shell (aka terminal aka command prompt) and type in the commands in the following steps.
3. Install the Node package for CoffeeScript  globally.
   ```
   sudo npm install -g coffee-script
   ```
   On Windows, you can omit the `sudo` command at the beginning.
4. Install the Node package for the Bower package manager.
   ```
   sudo npm install bower -g
   ```
5. Change into the Chaplin root directory.
6. Run `bower install` to download all third-party libraries the tests are using (Backbone, jQuery, Mocha etc.).
7. Run `cake test` to compile the CoffeeScripts to JavaScripts.
8. Open the test runner `test/index.html` in a browser.

## Boilerplate
[Chaplin Boilerplate](https://github.com/chaplinjs/chaplin-boilerplate) is a base application project for Chaplin. You can use it freely as a skeleton for your chaplin project.

If you’re not a CoffeeScript user, there’s also a plain JavaScript boilerplate: [Chaplin Boilerplate-Plain](https://github.com/chaplinjs/chaplin-boilerplate-plain)

[Boilerplate Rails Application with Backbone, Chaplin and Require.js](https://github.com/chaplinjs/chaplin-rails)

### Brunch with Chaplin
[github.com/paulmillr/brunch-with-chaplin](https://github.com/paulmillr/brunch-with-chaplin)

Brunch with Chaplin is a skeleton application, where [brunch](http://brunch.io) is used for assembling files & assets. It has ready-to-use classes for session management, html5boilerplate and stylus / handlebars.js as app languages.

## Examples

Several example applications are available today:

### Facebook Like Browser
[github.com/chaplinjs/facebook-example](https://github.com/chaplinjs/facebook-example)

This example uses Facebook client-side authentication to display the user’s Likes.

### Ost.io
[github.com/paulmillr/ostio](https://github.com/paulmillr/ostio) is a forum for GitHub projects and a modern replacement for mailing lists.

Ost.io serves as a good example of a fast service-based application, using *Ruby on Rails* as a lightweight backend [(which is open-sourced too)](https://github.com/paulmillr/ostio-api/) that only handles authentication / server-side logic & talks JSON to clients. In this way, frontend is completely decoupled from the backend which gives the ability to work on both projects in parallel and increases scalability, speed & mainbtability quite a lot.

### Tweet your Brunch
[github.com/brunch/twitter](https://github.com/brunch/twitter) is a simple twitter client. It uses Twitter client-side authentication to display user’s feed and to create new tweets.

## Documentation
All docs are located in [docs/](https://github.com/chaplinjs/chaplin/tree/master/docs) subdirectory.

![Ending](http://s3.amazonaws.com/imgly_production/3362023/original.jpg)

## [The Cast](https://github.com/chaplinjs/chaplin/blob/master/AUTHORS.md#the-cast)

## [The Producers](https://github.com/chaplinjs/chaplin/blob/master/AUTHORS.md#the-producers)
