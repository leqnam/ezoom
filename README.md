# ezoom.js

![ezoom.js](https://img.shields.io/static/v1?label=ezoom.js&message=v0.1.0&color=yellow) ![GitHub](https://img.shields.io/github/license/leqnam/ezoom)

ezoom.js is a jQuery plugin for simple Image with zoom effect. 

This plugin in under development to support Next/Prev a gallery Images/SVG later.

You can find the repository at: [https://github.com/leqnam/ezoom](https://github.com/leqnam/ezoom) 
and demo here: [https://leqnam.github.io/ezoom/demo/](https://leqnam.github.io/ezoom/demo/)

## Table of contents
- [Installation](#Installation)
- [Usage](#Usage)
- [Options](#Options)
- [Usages](#Usages)
- [Methods](#Methods)
- [Events](#Events)
- [Versions](#Versions)
- [Acknowledgements](#Acknowledgements)
- [License](#License)


<hr>


## Installation

Set up the HTML:
```html
	<div id="imgDiv">
		<img src="images/may.png">
	</div>
```
and the javascript:

```javascript
	ezoom.onInit($('#imgDiv img'), {
		onClose: function (result) {
			alert(result);
		}
	});
```

<hr>

## Usage

The plugin can be use with method `onInit` as two ways:
- Expand an image HTML dom in a Zoom Modal to zoom in/out and rotate image. The element dom is passed on the query selector.

```javascript
	ezoom.onInit(domElement, {
		onClose: function (result) {
			alert(result);
		}
	});
```

- Expand an remote image with an URL in a Zoom Modal to zoom in/out adn rotate image, by passing the `src` option.

```javascript
	const src = 'some image url';
	ezoom.onInit(domElement, {
		src: src,
		onClose: function (result) {
			alert(result);
		}
	});
```

<hr>

## Options

At the initialize, only `src` and `hideControlBtn` is available.

Option | Value | Description
---|---|---
`domElement` | dom | HTML DOM querySelector
`src` | string | An Image remote URL
`hideControlBtn` | boolean | Hide the Rotate Left/Right

<br>
Ex: To hide the Rotate Left/Right:

```javascript
	ezoom.onInit($('#imgDiv img'), {
		hideControlBtn: true
	});
```

<hr>

## Methods

At the initialize, we only need the `onInit` to create the zoom-modal instance and listen on this instance.

<hr>

## Events

Event | Description
---|---
`onShow` | Fired when the Zoom modal is shown
`onClose` | Fired when the Zoom modal is closed
`onRotate` | Fired when rotating the image
`onMoveStarted` | Fired when starting to move the image
`onMovedCompleted` | Fired when finished moving by release the mouse
`onMoving` | Fired while moving the image

<br>
The events can be used look like:

```javascript
	ezoom.onInit(domElement, {
		onRotate: function(callback) {
			// some magic
		}
	});
```

<hr>

## Versions

* v0.1.0
	1. Single image
	2. Add event listeners and callback


<br>
<hr>

## Acknowledgements

This plugin has been developed to use in my internal project to replace panzoom (https://github.com/anvaka/panzoom) - that has some issues with rotate.

An blog has been released: 
- in English: https://nready.net/ezoom and https://leqnam.github.io/ezoom/

<br>
<hr>

## License

Licensed under the MIT license.

Nam Le, 2021,
leqnam@live.com,

http://nready.net