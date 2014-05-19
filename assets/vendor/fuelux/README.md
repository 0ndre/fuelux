**Please note this currently is a WIP. Bower does not point to version 3.0.0. The `dist` folder may not be versioned, nor up to date. Please build via grunt before using.** 

#FuelUX

FuelUX extends [Bootstrap 3](https://github.com/twbs/bootstrap) with additional lightweight [JavaScript controls](#javascript-controls). It is actively maintained by [members of ExactTarget, a salesforce.com company,](https://github.com/orgs/ExactTarget/members) with the support and involvement of the community.

All functionality is covered by the [live documentation](http://exacttarget.github.io/fuelux/) and [unit tests](#automated-testing-status).

#### Automated Testing Status
|TravisCI|SauceLabs|Node modules|Browser Support|
|:---|:---:|:---:|----:|
|[![Build Status](https://api.travis-ci.org/ExactTarget/fuelux.png?branch=master)](http://travis-ci.org/ExactTarget/fuelux) |[![Selenium Test Status](https://saucelabs.com/buildstatus/fuelux)](https://saucelabs.com/u/fuelux) |[![devDependency Status](https://david-dm.org/ExactTarget/fuelux/dev-status.svg)](https://david-dm.org/ExactTarget/fuelux#info=devDependencies)|[![Selenium Test Status](https://saucelabs.com/browser-matrix/fuelux.svg)](https://saucelabs.com/u/fuelux)|

## Table of contents

 * [Quick start](#quick-start)
 * [Documentation](#documentation)
 * [Bugs and feature requests](#bugs-and-feature-requests)
 * [Compiling CSS and JavaScript](#Customizing-and-building)
 * [Issues and feature requests](#issues-and-feature-requests)
 * [Contributing](#contributing)
 * [Philosophy and authors](#philosophy-and-authors)
 * [Copyright and license](#copyright-and-license)

## Quick start

1. Install with [Bower](https://github.com/bower/bower):

    ```
    bower install fuelux
    ```
1. Use AMD (such as [RequireJS](http://require.js.org)) to reference the FuelUX folder in your paths configuration, wherever it is located:

    ```javascript
    require.config({
        paths: {
            'fuelux': 'http://www.fuelcdn.com/fuelux/3.0.0/'
            //...
        }
    });
    ```
1. List any individual fuelux controls needed as dependencies within your application modules (eg. [checkbox](http://exacttarget.github.io/fuelux/#checkbox)):

    ```javascript
    define(function(require) {
        var checkbox = require('fuelux/checkbox');
        //...
    });
    ```
1. Use FuelUX in your HTML within the fuelux wrapper class (eg. [checkbox](http://exacttarget.github.io/fuelux/#checkbox)):

    ```html
    <body class="fuelux">
    	<!-- .... -->
        <div class="checkbox">
	    <label class="checkbox-custom">
	        <input id="chk1" checked="checked" class="checked" type="checkbox" value="">
		    Custom appearance checkbox checked at page load (#chk1)
	    </label>
        </div>
        <!-- .... -->
    </body>
    ```

## Documentation

### Live docs and demos

View [live documentation and demos](http://exacttarget.github.com/fuelux) on GitHub pages.

### Getting FuelUX
FuelUX can be obtained one of three ways:

1. **Best way:** Install with [Bower](https://github.com/bower/bower):

    ```
    bower install fuelux
    ```

   This ensures you get all the [dependencies](#dependencies). You can then use `bower update fuelux` to keep it up to date in the future. You're welcome.

1. **Another best way:** Install with [Volo](https://github.com/volojs/volo):

    ```
    volo add fuelux
    ```

   This ensures you get all the [dependencies](#dependencies). You can then use `volo add -f fuelux` to keep it up to date in the future.

2. **Another good way:** Clone the Git repository:
   ```
   git clone https://github.com/ExactTarget/fuelux/
   ```

   Cloning the repository ensures you can apply future updates to FuelUX easily, but requires to you manage its [dependencies](#dependencies) on your own.

3. **Least desirable way in the universe:** Download a .zip archive of the latest release **(needthis)** or request files from [the FuelUX CDN](http://www.fuelcdn.com/fuelux/).

   Grabbing FuelUX in this way may seem easist now, but it will make integrating future updates (bug fixes!) nearly impossible.

   Trust us, you do ***not*** want to do it this way.


### Dependencies
FuelUX is dependent upon [Bootstrap 3](https://github.com/twbs/bootstrap) and [jQuery](https://github.com/jquery/jquery). If you installed by cloning the repo or by downloading a .zip archive, you'll also want to grab these things, as, it just won't work without them.
- [jQuery](https://github.com/jquery/jquery)
- [Bootstrap 3](https://github.com/twbs/bootstrap)


### What's included

A download of FuelUX provides the following directories and files, which are grouped according to file type:
```
fuelux/
├── css/
│   ├── fuelux.css
│   ├── fuelux.min.css
├── js/
│   ├── fuelux.js
│   └── fuelux.min.js
└── fonts/
    ├── fuelux.eot
    ├── fuelux.svg
    ├── fuelux.ttf
    └── fuelux.woff
```
We provide compiled CSS and JS (like `fuelux.*`), as well as compiled and minified CSS and JS (like `fuelux.min.*`) in the `dist` folder.

### JavaScript Controls

* **[Checkbox](http://exacttarget.github.io/fuelux/#checkbox)** - consistent cross-browser cross-platform look and feel for checkbox elements
* **[Combobox](http://exacttarget.github.io/fuelux/#combobox)** - combines input and dropdown for flexible data selection
* **[Datepicker](http://exacttarget.github.io/fuelux/#datepicker)** - combines input and dropdown to select a date
* **[Infinite Scroll](http://exacttarget.github.io/fuelux/#infinite-scroll)** - Load content when reaching a set amount of content read or with a call to action
* **[Intelligent Dropdown](http://exacttarget.github.io/fuelux/#intelligent-dropdown)** - Dropdown that decide whether it should be placed above or below the clicked element as well as force position.
* **[Loader](http://exacttarget.github.io/fuelux/#loader)** - fully css-driven loading animation for visual indication of wait times
* **[Pillbox](http://exacttarget.github.io/fuelux/#pillbox)** - manage tags with color-coded text labels
* **[Radio](http://exacttarget.github.io/fuelux/#radio)** - consistent cross-browser cross-platform look and feel for radio elements
* **[Repeater](http://exacttarget.github.io/fuelux/#repeater)** - A scrollable, sortable, searchable interface for data (replaces datagrid)
* **[Repeater Views](http://exacttarget.github.io/fuelux/#repeater-views)** - Use the provided views to customize a list of data or write your own
* **[Scheduler](http://exacttarget.github.io/fuelux/#scheduler)** - composite form control to quickly schedule events with support for [moment.js](https://github.com/moment/moment)
* **[Search](http://exacttarget.github.io/fuelux/#search)** - input for integrated search
* **[Selectlist](http://exacttarget.github.io/fuelux/#selectlist)** - extends button dropdown with the ability to set and retrieve the selected item
* **[Spinbox](http://exacttarget.github.io/fuelux/#spinbox)** - provides convenient numeric input with increment and decrement buttons
* **[Tree](http://exacttarget.github.io/fuelux/#tree)** - renders data in a tree, supporting caching and optional multi-selection
* **[Wizard](http://exacttarget.github.io/fuelux/#wizard)** - displays a multi-step process to be completed in a specific order

### UMD/AMD Support

We recommend only loading the controls you need (eg `fuelux/checkbox`).

If using AMD (such as [RequireJS](http://require.js.org)), reference the FuelUX directory in your paths configuration, wherever it is located:
```javascript
require.config({
    paths: {
        'fuelux': 'http://www.fuelcdn.com/fuelux/3.0.0/'
        //...
    }
});
```
Then list any individual fuelux controls needed as dependencies within your application modules:
```javascript
define(function(require) {
    var spinbox = require('fuelux/spinbox');
    //...
});
```
For your convenience when you are using AMD, you can just use `fuelux/all` instead of listing each module individually, but this is not recommended.

FuelUX also supports placing components in their own `<script>` tags. Be sure to put modules in the correct order if loading them in this method (although this order is a secret known only to 29th level wizards/enchantresses and 11th degree JS ninjas).

## Bugs and feature requests

Have a bug or a feature request? Please first review the [open issues](https://github.com/ExactTarget/fuelux/issues), then search for existing and closed issues. If your problem or idea is not addressed yet, [please open a new issue](https://github.com/ExactTarget/fuelux/issues/new).

You can visit [questions tagged FuelUX](https://code.exacttarget.com/tag/fuel-ux) in the ExactTarget Developer Community and search [FuelUX tagged questions on StackOverflow](http://stackoverflow.com/questions/tagged/fuelux).

You can also visit [UserVoice community](https://fuelux.uservoice.com) and post a comment or suggest features. We will maintain of backlog of feature we are considering developing in a [backlog](https://github.com/ExactTarget/fuelux/blob/3.0.0-wip/BACKLOG.md).

### Previous releases


Documentation for v2.6.x has been made available for the time being at **(need link)** while folks transition to Bootstrap 3. Previous releases and their documentation are also available for download. **(need link)**

## Compiling CSS and JavaScript

FuelUX is lightweight to give you a fast dependable foundation to build upon. It uses [Grunt](http://gruntjs.com/) with convenient methods for working with the library. It's how we compile our code, run tests, and more. To use it, install the required dependencies as directed, and then run some Grunt tasks.

### Install Grunt

From the command line:

1. Install `grunt-cli` globally with `npm install -g grunt-cli`.
2. Navigate to the root `/bootstrap` directory, then run `npm install`. npm will look at [package.json](https://github.com/twbs/bootstrap/blob/master/package.json) and automatically install the necessary local dependencies listed there.

When completed, you'll be able to run the various Grunt commands provided from the command line.

**Unfamiliar with NPM? Don't have node installed?** NPM stands for [node packaged modules](http://npmjs.org/) and is a way to manage development dependencies through node.js. [Download and install node.js](http://nodejs.org/download/) before proceeding.

### Grunt Tasks

#### Build - `grunt`
Run `grunt` to run tests locally and compile the CSS and JavaScript into `dist`. Uses [Less](http://lesscss.org/) and [UglifyJS](http://lisperator.net/uglifyjs/).

#### Testing - `grunt test`
Runs [JSHint](http://jshint.com), [HTML validation](https://www.npmjs.org/package/grunt-html-validation), and [QUnit](http://qunitjs.com/) tests headlessly in [PhantomJS](http://phantomjs.org/). `grunt releasetest` uses multiple versions of jQuery. 

#### Watch - `grunt serve`
This is a convenience method for watching source files and automatically building them when you save. To compile only CSS without running unit tests, use `grunt servecss`.

_`grünt saucelabs` and `grunt trickysauce` can be run locally instead of through TravisCI, but require the FuelUX Saucelabs API key file which is not public at this time._

### Troubleshooting dependencies

Should you encounter problems with installing dependencies or running Grunt commands, uninstall all previous dependency versions (global and local). Then, rerun `npm install`.

## Contributing
Before writing code, we suggest you [search for issues](https://github.com/ExactTarget/fuelux/issues?state=open) or [create a new one](https://github.com/ExactTarget/fuelux/issues/new) to confirm where your contribution fits into
our roadmap.

In lieu of a formal style guide, take care to maintain the existing coding style: tabs, clarity over brevity, declarative markup, semicolons, etc. Be sure to add unit tests for any new or changed functionality. Lint and test your code using [grunt](https://github.com/cowboy/grunt).

Read more about [contributing to FuelUX](https://github.com/ExactTarget/fuelux/wiki/Contributing-to-Fuel-UX)

Please do not edit files in the `dist` directory as they are generated via grunt. You'll find source code in the respective `js`, `less`, and `fonts` directory.

While grunt can run the included unit tests via PhantomJS, this isn't a substitute for running tests across a variety of browsers and environments. Please be sure to view the test page at [http://localhost:8000/test/](http://localhost:8000/test/) in as many of the browsers listed in `sauce_browsers.yml` as you can before contributing.

##Philosophy and authors

### The FuelUX Philosophy
Our aim is to provide a suite of related but independent projects that help web developers integrate, manage, and customize quality libraries and utilities to more efficiently develop, maintain, test, and distribute their projects.  Any improvements or fixes we make to the open source projects, we use will be contributed upstream if they are useful to the rest of the community.

|Current Project Maintainers (a-z) | |
|:----|----:|
|Matt Beard |[![mbeard on Github](https://raw.githubusercontent.com/ExactTarget/fuelux/gh-pages/invertocat-sm.png)](http://github.com/mbeard) |
|Stephen James | [![tweetllama on Twitter](https://raw.githubusercontent.com/ExactTarget/fuelux/gh-pages/invertobird-sm.png)](http://twitter.com/tweetllama) [![interactivellama on Github](https://raw.githubusercontent.com/ExactTarget/fuelux/gh-pages/invertocat-sm.png)](http://github.com/interactivellama)|
|Christopher McCulloh | [![@cmcculloh on Twitter](https://raw.githubusercontent.com/ExactTarget/fuelux/gh-pages/invertobird-sm.png)](http://twitter.com/cmcculloh) [![cmcculloh on Github](https://raw.githubusercontent.com/ExactTarget/fuelux/gh-pages/invertocat-sm.png)](http://github.com/cmcculloh)|
|Kevin Parkerson  | [![kevinparkerson on Twitter](https://raw.githubusercontent.com/ExactTarget/fuelux/gh-pages/invertobird-sm.png)](http://twitter.com/kevinparkerson) [![kevinparkerson on Github](https://raw.githubusercontent.com/ExactTarget/fuelux/gh-pages/invertocat-sm.png)](http://github.com/kevinparkerson)|
|Alex Vernacchia | [![vernacchia on Twitter](https://raw.githubusercontent.com/ExactTarget/fuelux/gh-pages/invertobird-sm.png)](http://twitter.com/vernacchia) [![vernak2539 on Github](https://raw.githubusercontent.com/ExactTarget/fuelux/gh-pages/invertocat-sm.png)](http://github.com/vernak2539)|
|David Waltz | [![dwaltz on Github](https://raw.githubusercontent.com/ExactTarget/fuelux/gh-pages/invertocat-sm.png)](http://github.com/dwaltz)|

|Original Author&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; | |
|:----|----:|
|Adam Alexander |[![adamalex on Twitter](https://raw.githubusercontent.com/ExactTarget/fuelux/gh-pages/invertobird-sm.png)](http://twitter.com/adamalex) [![adamalex on Github](https://raw.githubusercontent.com/ExactTarget/fuelux/gh-pages/invertocat-sm.png)](http://github.com/adamalex) |

|Past Project Maintainers&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; | |
|:----|----:|
|Bryan Kohlmeier |[![bkohlmeier on Github](https://raw.githubusercontent.com/ExactTarget/fuelux/gh-pages/invertocat-sm.png)](http://github.com/bkohlmeier) |
|Dustin McCormick | [![djmccormick on Twitter](https://raw.githubusercontent.com/ExactTarget/fuelux/gh-pages/invertobird-sm.png)](http://twitter.com/djmccormick) [![djmccormick on Github](https://raw.githubusercontent.com/ExactTarget/fuelux/gh-pages/invertocat-sm.png)](http://github.com/djmccormick)|
|Scott Plumlee | [![scottplumlee on Twitter](https://raw.githubusercontent.com/ExactTarget/fuelux/gh-pages/invertobird-sm.png)](http://twitter.com/scottplumlee) [![plumlee on Github](https://raw.githubusercontent.com/ExactTarget/fuelux/gh-pages/invertocat-sm.png)](http://github.com/plumlee)|
|Marvin Pribble | [![marvinpribble on Github](https://raw.githubusercontent.com/ExactTarget/fuelux/gh-pages/invertocat-sm.png)](http://github.com/marvinpribble)|
|Ryan Moore | [![rbmoore on Github](https://raw.githubusercontent.com/ExactTarget/fuelux/gh-pages/invertocat-sm.png)](http://github.com/rbmoore)|
|Steven Rogers | [![soldoutactivist on Github](https://raw.githubusercontent.com/ExactTarget/fuelux/gh-pages/invertocat-sm.png)](http://github.com/soldoutactivist)| 

And thank you to all those that have submitted issues and contributed to this library.

## Copyright and license

Copyright &copy; 2014 ExactTarget.

Licensed under the MIT License (the "License");
you may not use this work except in compliance with the License.
You may obtain a copy of the License in the COPYING file.

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.

[![githalytics.com alpha](https://cruel-carlota.pagodabox.com/8b519d39e18063752f24876583a6526b "githalytics.com")](http://githalytics.com/ExactTarget/fuelux)
