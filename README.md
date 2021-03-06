<!-- TITLE/ -->

# Feedr

<!-- /TITLE -->


<!-- BADGES/ -->

[![Build Status](http://img.shields.io/travis-ci/bevry/feedr.png?branch=master)](http://travis-ci.org/bevry/feedr "Check this project's build status on TravisCI")
[![NPM version](http://badge.fury.io/js/feedr.png)](https://npmjs.org/package/feedr "View this project on NPM")
[![Dependency Status](https://david-dm.org/bevry/feedr.png?theme=shields.io)](https://david-dm.org/bevry/feedr)
[![Development Dependency Status](https://david-dm.org/bevry/feedr/dev-status.png?theme=shields.io)](https://david-dm.org/bevry/feedr#info=devDependencies)<br/>
[![Gittip donate button](http://img.shields.io/gittip/bevry.png)](https://www.gittip.com/bevry/ "Donate weekly to this project using Gittip")
[![Flattr donate button](http://img.shields.io/flattr/donate.png?color=yellow)](http://flattr.com/thing/344188/balupton-on-Flattr "Donate monthly to this project using Flattr")
[![PayPayl donate button](http://img.shields.io/paypal/donate.png?color=yellow)](https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=QB8GQPZAH84N6 "Donate once-off to this project using Paypal")
[![BitCoin donate button](http://img.shields.io/bitcoin/donate.png?color=yellow)](https://coinbase.com/checkouts/9ef59f5479eec1d97d63382c9ebcb93a "Donate once-off to this project using BitCoin")

<!-- /BADGES -->


<!-- DESCRIPTION/ -->

Feedr takes in a remote feed (regardless of format type) and converts it into JSON data

<!-- /DESCRIPTION -->


<!-- INSTALL/ -->

## Install

### [Node](http://nodejs.org/)
- Use: `require('feedr')`
- Install: `npm install --save feedr`

<!-- /INSTALL -->


## Usage

``` javascript
// Prepare
var Feedr, feedr, feeds;

// Include the Feedr Class
Feedr = require('feedr').Feedr;

// Create our Feedr instance, we can pass optional configuration if we wanted
feedr = new Feedr();

// Prepare our feeds that we want read
feeds = {
	github: "https://github.com/bevry/feedr/commits/master.atom",
	twitter: "https://api.twitter.com/1/statuses/user_timeline.json?screen_name=balupton&count=20&include_entities=true&include_rts=true"
};

// Read a single feed
feedr.readFeed(feeds.github, {/* optional configuration*/}, function(err, data, headers){
	console.log(err, data, headers);
});

// Read all the feeds together
feedr.readFeeds(feeds, {/* optional configuration*/}, function(err, result){
	console.log(err, result.github, result.twitter);
});
```


## Configuration

Global configuration properties are:

- `log` defaults to `null`, log function to use
- `tmpPath` defaults to system tmp path, the tempory path to cache our feedr results to
- `cache` defaults to `true`, whether or not we should use the cache if it is valid
- `xml2jsOptions` defaults to `null`, the options to send to [xml2js](https://github.com/Leonidas-from-XIV/node-xml2js)
- `requestOptions` defaults to `null`, the options to send to [request](https://github.com/mikeal/request)

Feed configuration properties are:

- `url` required, the url to fetch
- `hash` defaults to hash of the url, the hashed url for caching
- `name` defaults to hash, the name of the feed for use in debugging
- `path` defaults to tmp feed path, the path to save the file to
- `parse` defaults to auto detection based on the extension of the url, whether or not to parse the data into a javascript object, can be set to `false`, `true`, `"xml"`, `"json"`, `"cson"`, `"yaml"`
- `checkResponse` defaults to `null`, a function accepting `response`, `data`, and `next` to check the response for errors
- `xml2jsOptions` defaults to global value, the options to send to [xml2js](https://github.com/Leonidas-from-XIV/node-xml2js)
- `requestOptions` defaults to global value, the options to send to [request](https://github.com/mikeal/request)


<!-- HISTORY/ -->

## History
[Discover the change history by heading on over to the `HISTORY.md` file.](https://github.com/bevry/feedr/blob/master/HISTORY.md#files)

<!-- /HISTORY -->


<!-- CONTRIBUTE/ -->

## Contribute

[Discover how you can contribute by heading on over to the `CONTRIBUTING.md` file.](https://github.com/bevry/feedr/blob/master/CONTRIBUTING.md#files)

<!-- /CONTRIBUTE -->


<!-- BACKERS/ -->

## Backers

### Maintainers

These amazing people are maintaining this project:

- Benjamin Lupton <b@lupton.cc> (https://github.com/balupton)

### Sponsors

No sponsors yet! Will you be the first?

[![Gittip donate button](http://img.shields.io/gittip/bevry.png)](https://www.gittip.com/bevry/ "Donate weekly to this project using Gittip")
[![Flattr donate button](http://img.shields.io/flattr/donate.png?color=yellow)](http://flattr.com/thing/344188/balupton-on-Flattr "Donate monthly to this project using Flattr")
[![PayPayl donate button](http://img.shields.io/paypal/donate.png?color=yellow)](https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=QB8GQPZAH84N6 "Donate once-off to this project using Paypal")
[![BitCoin donate button](http://img.shields.io/bitcoin/donate.png?color=yellow)](https://coinbase.com/checkouts/9ef59f5479eec1d97d63382c9ebcb93a "Donate once-off to this project using BitCoin")

### Contributors

These amazing people have contributed code to this project:

- [Benjamin Lupton](https://github.com/balupton) <b@lupton.cc> — [view contributions](https://github.com/bevry/feedr/commits?author=balupton)

[Become a contributor!](https://github.com/bevry/feedr/blob/master/CONTRIBUTING.md#files)

<!-- /BACKERS -->


<!-- LICENSE/ -->

## License

Licensed under the incredibly [permissive](http://en.wikipedia.org/wiki/Permissive_free_software_licence) [MIT license](http://creativecommons.org/licenses/MIT/)

Copyright &copy; 2012+ Bevry Pty Ltd <us@bevry.me> (http://bevry.me)

<!-- /LICENSE -->


