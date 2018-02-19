shake.js Fork
=======================================

This fork does not use event system, but rather use a classic handler.
We can now have as many Shake object as we want, and we also know which one fired.


Forked from
* Git: `git clone https://github.com/alexgibson/shake.js`

Installation
---------------------------------------
* Download: [zip](https://github.com/zouloux/shake.js/zipball/master)
* [NPM](https://www.npmjs.org/): `npm install @zouloux/shake`


Dependencies
---------------------------------------

Your web browser must support the `devicemotion` event for this plugin to work. Shake.js uses built-in feature detection to determine if it can run in your web browser. It will terminate silently on non-supporting browsers.

http://w3c.github.io/deviceorientation/spec-source-orientation.html

Setup
---------------------------------------

For CommonJS using NPM:

```
const Shake = require('@zouloux/shake');
```

For AMD module:

```
define(['./shake'], function(Shake) {
    // ...
});
```

In the browser:

```
<script src="shake.js"></script>
```

Next, create a new Shake instance:

```
const myShakeEvent = new Shake({
    threshold: 15, // optional shake strength threshold
    timeout: 1000, // optional, determines the frequency of event generation
    handler: () => // required, called when shake is detected
    {
    	console.log('Shake detected !');
    }
});
```

Start listening to device motion:

```
myShakeEvent.start();
```

To stop listening to device motion, you can call:

```
myShakeEvent.stop();
```

Supported web browsers/devices
---------------------------------------

- iOS Safari 4.2.1 (and above)
- Android 4.0.3 (default browser)
- Chrome 41+ for Android
- Opera Mobile (Android)
- BlackBerry PlayBook 2.0
- Firefox for Android
- FirefoxOS Devices
