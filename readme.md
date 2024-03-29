*This repository is a mirror of the [component](http://component.io) module [sindresorhus/is-png](http://github.com/sindresorhus/is-png). It has been modified to work with NPM+Browserify. You can install it using the command `npm install npmcomponent/sindresorhus-is-png`. Please do not open issues or send pull requests against this repo. If you have issues with this repo, report it to [npmcomponent](https://github.com/airportyh/npmcomponent).*
# is-png [![Build Status](https://travis-ci.org/sindresorhus/is-png.svg?branch=master)](https://travis-ci.org/sindresorhus/is-png)

> Check if a Buffer/Uint8Array is a [PNG](http://en.wikipedia.org/wiki/Portable_Network_Graphics) image

Used by [image-type](https://github.com/sindresorhus/image-type).


## Install

```sh
$ npm install --save is-png
```

```sh
$ bower install --save is-png
```

```sh
$ component install sindresorhus/is-png
```


## Usage

##### Node.js

```js
var readChunk = require('read-chunk'); // npm install read-chunk
var isPng = require('is-png');
var buffer = readChunk('unicorn.png', 0, 4);

isPng(buffer);
//=> true
```

##### Browser

```js
var xhr = new XMLHttpRequest();
xhr.open('GET', 'unicorn.png');
xhr.responseType = 'arraybuffer';

xhr.onload = function () {
	isPng(new Uint8Array(this.response));
	//=> true
};

xhr.send();
```


## API

### isPng(buffer)

Accepts a Buffer (Node.js) or Uint8Array.

It only needs the first 4 bytes.


## License

MIT © [Sindre Sorhus](http://sindresorhus.com)
