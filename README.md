# device-orientation

It is a custom element that allows capture the current device orientation using just one tag and a little bit JS.
With this element is also possible to set the frequency of motion events using the <code>interval</code> attribute.
The accuracy can also be set using the <code>digit</code> attribute.

By default, the element will fire the motion event at any time, and motion information will come without decimal digits.
In the examples below shows how it is possible set attributes to customize the data.

## Install

Install the component using [Bower](http://bower.io/):

```sh
$ bower install device-orientation --save
```

Or [download as ZIP](https://github.com/guilhermefarias/device-orientation/archive/v1.0.0.zip).

## Usage

Import Web Components' polyfill:
```html
<script src="//cdnjs.cloudflare.com/ajax/libs/polymer/0.2.3/platform.js"></script>
```

Import Custom Element:
```html
<link rel="import" href="bower_components/device-orientation/src/device-orientation.html">
```

Start using it!
```html
<device-orientation></device-orientation>
```

```javascript
var orientation = document.querySelector('device-orientation');
orientation.addEventListener('motion', function() {
	console.log(this.gamma);
	console.log(this.beta);
	console.log(this.alpha);
});
```

## What is gamma, beta and alpha?

The device orientation is described about any given axis in terms of the number of degrees of difference between the device's coordinate and the Earth coordinate and is measured in degrees.

### Alpha
The alpha angle is 0° when top of the device is pointed directly toward the Earth's north pole, and increases as the device is rotated toward the left.

### Beta
The beta angle is 0° when the device's top and bottom are the same distance from the Earth's surface, and increases toward 180° as the device is tipped forward and decreases toward -180° as the device is tipped backward.

### Gamma
The gamma angle is 0° when the device's left and right sides are the same distance from the surface of the Earth, and increases toward 90° as the device is tipped toward the right, and toward -90° as the device is tipped toward the left.

![Orientation Axis](http://i58.tinypic.com/ampljd.png)


## Examples
### Example of motion fired every 1 second
```html
<device-orientation interval="1000"></device-orientation>
```

### Example of motion data with 5 digits of accuracy
```html
<device-orientation digit="5"></device-orientation>
```

### Example of motion fired every 1 second with 2 digits of accuracy
```html
<device-orientation interval="2000" digit="2"></device-orientation>
```

## About

#### Who?
Created by [Guilherme Farias](http://guilhermefarias.com/), a web developer from Brazil.

#### License?
This element is released under the terms of the [MIT license](https://github.com/guilhermefarias/device-orientation/blob/master/MIT-LICENSE).
