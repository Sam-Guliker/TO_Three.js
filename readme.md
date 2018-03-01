# Playing around with Three.js
with Three.js u can make 3d objects in the webrowser and even animate them.:open_mouth: :hearth_eyes:

## Creating a scene.
To create anything with [three.js](https://threejs.org/) We need three things.  
A scene, camera and renderer, so we can render the scene with the camera.:eyes:

```Javascript
var scene = new Three.Scene();
var camera = new THREE.PerspectiveCamera(75, window.innerWidth/window.innerHeight, 0.1, 1000)

var renderer = new Three.WebGLRenderer()
renderer.setSize(window.innerWidth, window.innerHeight)
document.body.appendChild(renderer.domElement)
```

Mhmmm:thinking:  
Whats going on!?  

```Javascript

var scene = new Three.Scene();
var camera = new THREE.PerspectiveCamera(75, window.innerWidth/window.innerHeight, 0.1, 1000)

```
There are different camera's in three.js but Im using `PerspectiveCamera`
the first attribute is the `Field Of View` which is 75.  FoV is the extent of the scene that is seen on the   display at any given moment. The value is in degrees.

The second value is the aspect ratio. You always want to use the width  of the element devided by the height.
or you'll get the  same result as when you play old movies on a widescreen TV  - the image looks squished.

The next two attributes are the near and far clipping plane.  What that means, is that objects further away from the camera than  the value of far or closer than near won't be rendered.  

Now the renderer :innocent:  
```Javascript

var renderer = new Three.WebGLRenderer()
renderer.setSize(window.innerWidth, window.innerHeight)
document.body.appendChild(renderer.domElement)

```
Time for magic :sparkles: :grinning:  
We are using `WebGLRenderer` which is made by [WebGL](https://get.webgl.org/)  Three.js comes with a few others, it is used for fallbacks  for users with an older browser who don't have WebGL suported.  

In order to set the renderer instance, we need to set the size which we want it to render it to.  
I'm using full screen but for some app's it maybe usefull to make a smaller size.  
you can dostuff like 
```Javascript 
setSize(window.innerWidth/2, window.innerHeight/2, false)
```  
This will render it at half size.
And for the last part we append the renderer to our HTML document.  
This is a `<canvas>` element.  


