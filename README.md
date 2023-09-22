# vidometry-scene v2.0.1

## vidometer-scene-demo

# API

## vidometry-scene

***Callbacks:***

***onLoading(progress)*** - throws when sources are loading, (form 0 to 1);

***onLoaded()*** - throws when all sources are loaded and experience ready to start;

***onStarted()*** - throws when experience is started;

***onStopped()*** - throws when experience is stopped (uses for the **vitracker** experience when the target isn’t detected; uses for the **detnn** experience when the object isn’t detected);

```jsx
<vidometry-scene>
	...
</vidometry-scene>
```

## Objects

### vidometry-gltf

**Attributes:**

***src*** - model source, we recommend to use *.glb files;

***scale*** - “sx sy sz”, object scaling on the scene;

***position*** - “x y z”, object position on the scene, in meters;

***rotation*** - ”rx ry rz”, objects rotation on the scene, in degrees;

**Methods:**

***show()*** - shows the scene;

***hide()*** - hides the scene;

***showObject(name)*** - shows the object on the scene with certain name; 

***hideObject(name)*** - hides the object on the scene with certain name;

***playAllAnimations()*** - plays all animations on the scene;

***stopAllAnimations()*** - stops all animations on the scene;

***playAnimation(name, loop, clampWhenFinished)*** - plays animations with certain name;

*loop* - (optional, default false) true of false, loops animation;

*clampWhenFinished* - (optional, default false) if **clampWhenFinished** is set to true the animation will automatically be paused on its last frame;

***stopAnimation(name)*** - stops animations with certain name;

```jsx
<vidometry-scene>
	...
	<vidometry-gltf 
		src="./assets/scene.glb" 
		scale="1 1 1"
		position="0 0 0"
		rotation="0 0 0">
	</vidometry-gltf>
	...
</vidometry-scene>
```

### vidometry-video

**Attributes:**

***src*** - video source, you can use *.mp4 files;

***height*** - height of video object on the scene, in meters;

***position*** - “x y z”, object position on the scene, in meters;

**Methods:**

***show()*** - shows the scene;

***hide()*** - hides the scene;

***mute()*** - mutes the video;

***unmute()*** - unmutes the video;

```jsx
<vidometry-scene>
	...
	<vidometry-video 
		src="./assets/video.mp4" 
		height="1.5"
		position="0 0 0">
	</vidometry-video>
	...
</vidometry-scene>
```

### vidometry-image

**Attributes:**

***src*** - image source;

***size*** - size on the scene, in meters;

***position*** - “x y z”, position object on the scene, in meters;

**Methods:**

***show()*** - shows the scene;

***hide()*** - hides the scene;

```jsx
<vidometry-scene>
	...
	<vidometry-image 
		src="./assets/video.mp4" 
		size="1 1"
		position="0 0 0">
	</vidometry-image>
	...
</vidometry-scene>
```

## Lights

### vidometry-ambient-light

**Attributes:**

***color*** - hex color of light;

***intensity*** - light intensity;

```jsx
<vidometry-scene id="scene">
	...
	<vidometry-ambient-light color="#ffeeb1" intensity="1"></vidometry-ambient-light>
	...
</vidometry-scene>
```

### vidometry-point-light

**Attributes:**

***color*** - hex color of light;

***intensity*** - light intensity;

***position*** - “x y z”, position object on the scene, in meters

```jsx
<vidometry-scene id="scene">
	...
	<vidometry-point-light color="#ffffff" intensity="1" position="2 5 2"></vidometry-point-light>
	...
</vidometry-scene>
```

## Managers

You can add one of the following managers on the scene:

### vidometry-vidometer

Callbacks**:**

***onKeyframe(result)*** - throws when user is trying to in experience by tapping on the screen; result = true if keyframe is added, result = false if keyframe isn’t added (not enough features or wrong orientation of the camera);

```jsx
<vidometry-scene id="scene">
	...
	<vidometry-vidometer preview></vidometry-vidometer>
	...
</vidometry-scene>
```

[Vidometer demo](https://bettar.life/vidometer-scene/)

### vidometry-viewer (under development)

```tsx
<vidometry-scene>
	...
	<vidometry-viewer></vidometry-viewer>
	...
<vidometry-scene>
```

You can use Viewer for the development. Each axis on the scene is approximately 1.5m. 

### vidometry-vitracker (under development)

Attributes:

***target*** - the source of the image target (*.jpg);

```jsx
<vidometry-scene id="scene">
	...
	<vidometry-vitracker target="./assets/target.jpg"></vidometry-vitracker>
	...
</vidometry-scene>
```

### detnn-face

Face detection. In the future, we plan to add detection and tracking of different parts of the face.

```jsx
<vidometry-scene id="scene">
	...
	<detnn-face></detnn-face>
	...
</vidometry-scene>
```

[DetnnFace demo](https://bettar.life/detnn-scene/)

### detnn-hand (under development)

Hand detection and tracking.

```jsx
<vidometry-scene id="scene">
	...
	<detnn-hand></detnn-hand>
	...
</vidometry-scene>
```

### detnn-foot (under development)

Foot detection and tracking.

```jsx
<vidometry-scene id="scene">
	...
	<detnn-foot></detnn-foot>
	...
</vidometry-scene>
```

### detnn-body (under development)

Full body detection and tracking.

```jsx
<vidometry-scene id="scene">
	...
	<detnn-body></detnn-body>
	...
</vidometry-scene>
```

## Demos

[Vidometer demo](https://bettar.life/vidometer-scene/)

[DetnnFace demo](https://bettar.life/detnn-scene/)