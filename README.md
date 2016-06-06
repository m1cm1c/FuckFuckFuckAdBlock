FuckFuckFuckAdBlock (v3.2.1)
===========

* Fork of FuckAdblock

You can detect nasty ad blockers, and block fuckfuckadblock.
Online example: http://sitexw.fr/fuckadblock/

(There is also a project, [BlockAdBlock](https://github.com/sitexw/BlockAdBlock), with a more convenient name)

*Come and see the future of FuckAdBlock: [V4 Beta](https://github.com/sitexw/FuckAdBlock/tree/v4.x)*


Valid on
---------------------
- Google Chrome
- Mozilla Firefox
- Internet Explorer (8+)
- Safari
- Opera

Install via
---------------------
Manual:
```
Download "fuckfuckfuckadblock.js" and add it to your website.
```


Code example
---------------------
```javascript
// Function called if AdBlock is not detected
function adBlockNotDetected() {
	alert('AdBlock is not enabled');
}
// Function called if AdBlock is detected
function adBlockDetected() {
	alert('AdBlock is enabled');
}

// Recommended audit because AdBlock lock the file 'fuckadblock.js' 
// If the file is not called, the variable does not exist 'fuckAdBlock'
// This means that AdBlock is present
if(typeof fuckfuckfuckAdBlock === 'undefined') {
	adBlockDetected();
} else {
	fuckfuckfuckAdBlock.onDetected(adBlockDetected);
	fuckfuckfuckAdBlock.onNotDetected(adBlockNotDetected);
	// and|or
	fuckfuckfuckAdBlock.on(true, adBlockDetected);
	fuckfuckfuckAdBlock.on(false, adBlockNotDetected);
	// and|or
	fuckfuckfuckAdBlock.on(true, adBlockDetected).onNotDetected(adBlockNotDetected);
}

// Change the options
fuckfuckfuckAdBlock.setOption('checkOnLoad', false);
// and|or
fuckfuckfuckAdBlock.setOption({
	debug: true,
	checkOnLoad: false,
	resetOnEnd: false
});
```

Default options
---------------------
```javascript
// At launch, check if AdBlock is enabled
// Uses the method fuckfuckfuckAdBlock.check()
checkOnLoad: true

// At the end of the check, is that it removes all events added ?
resetOnEnd: true

// The number of milliseconds between each check
loopCheckTime: 50

// The number of negative checks after which there is considered that AdBlock is not enabled
// Time (ms) = 50*(5-1) = 200ms (per default)
loopMaxNumber: 5

// CSS class used by the bait caught AdBlock
baitClass: 'pub_300x250 pub_300x250m pub_728x90 text-ad textAd text_ad text_ads text-ads text-ad-links'

// CSS style used to hide the bait of the users
baitStyle: 'width: 1px !important; height: 1px !important; position: absolute !important; left: -10000px !important; top: -1000px !important;'

// Displays the debug in the console (available only from version 3.2 and more)
debug: false
```

Method available
---------------------
```javascript
// Allows to set options
// #options: string|object
// #value:   string
fuckfuckfuckAdBlock.setOption(options, value);

// Allows to check if AdBlock is enabled
// The parameter 'loop' allows checking without loop several times according to the value of 'loopMaxNumber'
// Example: loop=true  => time~=200ms (time varies depending on the configuration)
//          loop=false => time~=1ms
// #loop: boolean (default: true)
fuckfuckfuckAdBlock.check(loop);

// Allows to manually simulate the presence of AdBlock or not
// #detected: boolean (AdBlock is detected ?)
fuckfuckfuckAdBlock.emitEvent(detected);

// Allows to clear all events added via methods 'on', 'onDetected' and 'onNotDetected'
fuckfuckfuckAdBlock.clearEvent();

// Allows to add an event if AdBlock is detected
// #detected: boolean (true: detected, false: not detected)
// #fn:       function
fuckfuckfuckAdBlock.on(detected, fn);

// Similar to fuckfuckfuckAdBlock.on(true|false, fn)
fuckfuckfuckAdBlock.onDetected(fn);
fuckfuckfuckAdBlock.onNotDetected(fn);
```

Instance
---------------------
*(Available only from version 3.1 and more)*
By default, FuckAdBlock is instantiated automatically.
To block this automatic instantiation, simply create a variable "fuckfuckfuckAdBlock" with a value (null, false, ...) before importing the script.
```html
<script>var fuckfuckfuckAdBlock = false;</script>
<script src="./fuckfuckfuckadblock.js"></script>
```
After that, you are free to create your own instances:
```javascript
fuckfuckfuckAdBlock = new FuckFuckFuckAdBlock;
// and|or
myFuckFuckFuckAdBlock = new FuckFuckFuckAdBlock({
	checkOnLoad: true,
	resetOnEnd: true
});
```
