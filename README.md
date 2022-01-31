# Introduction_A-frame

Code for a creative coding class on A-Frame for designers. (AR focused)

## Contents





## The tools

We use three tools :
- a library for content : [A-Frame](https://aframe.io/)
- a library for marker detections in augmented reality : [ARjs](https://ar-js-org.github.io/AR.js-Docs/) 
- a webhosting plateform to write our code and host our projects : [Glitch](https://glitch.com/)

### What is A-Frame ?
[A-Frame](https://aframe.io/docs/1.2.0/introduction/) is a free and open-source framework supported by the mozilla foundation aiming at easing the creation of 3D / VR / AR experiences in the browser. 

With this this tool it's pretty easy to use the html syntax to create 3D scenes that can then be used in any of the contexts mentionned above.

For instance this code :

```html
<html>
  <head>
    <script src="https://aframe.io/releases/1.2.0/aframe.min.js"></script>
  </head>
  <body>
    <a-scene>
      <a-box position="-1 0.5 -3" rotation="0 45 0" color="#4CC3D9"></a-box>
      <a-sphere position="0 1.25 -5" radius="1.25" color="#EF2D5E"></a-sphere>
      <a-cylinder position="1 0.75 -3" radius="0.5" height="1.5" color="#FFC65D"></a-cylinder>
      <a-plane position="0 0 -4" rotation="-90 0 0" width="4" height="4" color="#7BC8A4"></a-plane>
      <a-sky color="#ECECEC"></a-sky>
    </a-scene>
  </body>
</html>

```

Creates a scene with a sky, a floor (or plane) and 3 3D primitives (a box, a sphere and a cylinder); each element has **attributes** to specify their *position*, *rotation*, *color* etc.

<img src="assets/aframe_starter.png" width="640" height="360" /><br>


The live result can be seen here : https://glitch.com/~aframe

Notice that by *clicking and dragging the mouse around* you can change your point of view, and you can even move around using you keyboard with the keys QZSD. Everything is handle behind the scenes for you.

FYI the rendering engine behind A-Frame is [Threejs](https://threejs.org/), and for advanced usage you can have access to it through code.

[**home**](#Contents)

### What is AR ?

AR is a technology that allows you to overlay digital / interactive content on a real world image in real-time. The idea is to augment our vision of the physical world with new information, graphics etc.

Well to be clear the AR world is globally a mess, in this course we choose to focus on web technologies that do work both on desktop, iOS and android to simplify the overall process and experimentations - and we also use free and open source tools.

To do that several method are use to pin / anchor the content :
- **markers detection** : you need to use a specific image to detect its position in a video feed and place content onto it.
- **image detection** : you can train a specific image of your choice to be a marker. You'll need to take a few steps though to make your program recognize your image; be aware that tracking quality will be dependent on the image you choose.
- **marker less detection** : you can detect planes in your environment that is to say : the floor, the ceilling and the walls. Though this technology is not really easily available with free and open source web technologies yet.
- **gps coordinates** : you can pin some contents to a specific gps position, but this is highly experimental at the moment and tracking is a bit shaky.


ARjs is a javascript library to create AR application, it allows you to track the position of markers / images and even gps coordinates.

While ARjs is the library we will use for markers and gps coordinates that is to say most use cases - we will use another one for natural images detection [mindARjs](https://hiukim.github.io/mind-ar-js-doc/quick-start/overview/)


Do keep in mind that tracking is really performant when you use markers, like this one - **hiro** :

<img src="markers/hiro.png" width="480" height="480" /><br>

Tracking images is more challenging and you need to train an algorithm to do it and the tracking quality highly depends on the image you choose.

But just to give you an idea on how we will do all this, it's still pretty easy - check out this code :

```html
<script src="https://aframe.io/releases/0.8.0/aframe.min.js"></script>
<script src="https://cdn.rawgit.com/jeromeetienne/AR.js/1.6.0/aframe/build/aframe-ar.js"></script>
<body style='margin : 0px; overflow: hidden;'>
	<a-scene embedded arjs='sourceType: webcam;'>
		<a-box position='0 0.5 0' material='opacity: 0.5;'></a-box>
		<a-marker-camera preset='hiro'></a-marker-camera>
	</a-scene>
</body>
```

from this [article](https://medium.com/arjs/augmented-reality-in-10-lines-of-html-4e193ea9fdbf)

Try opening this qr code with your phone and show it the hiro marker above.

<img src="qrcodes/00_qr_base_example_arjs.png" width="240" height="240" /><br>

[**home**](#Contents)


### What is Glitch ?


## Getting started with glitch

## Several kinds of contents
### Basic shapes
### Texts
### 3d models
### images
### videos
### p5js sketches

## Several kinds of detections
### Hiro Kanji
### Barcode markers
### Custom marker 
### Images as marker (mind-arjs)

## QR-markers








## Links and references

https://medium.com/arjs/augmented-reality-in-10-lines-of-html-4e193ea9fdbf


https://medium.com/samsung-internet-dev/use-new-augmented-reality-features-with-just-a-few-lines-of-code-with-webxr-and-aframe-c6f3f5789345
