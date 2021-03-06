# uninspected

Replacement for util.inspect and the console object.

[![NPM version](https://badge.fury.io/js/messy.svg)](http://badge.fury.io/js/uninspected)
[![Build Status](https://travis-ci.org/unexpectedjs/uninspected.svg?branch=master)](https://travis-ci.org/unexpectedjs/uninspected)
[![Coverage Status](https://coveralls.io/repos/unexpectedjs/uninspected/badge.svg)](https://coveralls.io/r/unexpectedjs/uninspected)
[![Dependency Status](https://david-dm.org/unexpectedjs/uninspected.svg)](https://david-dm.org/unexpectedjs/uninspected)

```javascript
var uninspected = require('uninspected');

var str = uninspected.inspect({ foo: 'bar' }); // "{ foo: 'bar' }"

uninspected.log('foo', { bar: /hey/ }); // { bar: /hey/ }

// Or use this shorthand:
uninspected('foo', { bar: /hey/ }); // { bar: /hey/ }
```

The library also includes diffing support (powered by Unexpected's diffing engine):

```javascript
uninspected.diff({ foo: 'bar' }, { foo: 'baz' });
{
  foo: 'bar'; // should be 'baz'
  // -bar
  // +baz
}
```

You can also use it instead of the console object:

```javascript
var console = require('uninspected');

console.log('...');

console.trace();
```

In the Chrome console this will produce colored output using [this API](https://developer.chrome.com/devtools/docs/console#styling-console-output-with-css).

The `uninspected` npm package includes a bookmarklet for doing the above, ie. replacing the `console` object with uninspected, see `bookmarklet.html` at the root of the package. Unfortunately github doesn't permit putting it directly into this README.

## RELEASES

See the [changelog](CHANGELOG.md).
