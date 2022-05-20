# vidometry-scene v1.0.7

## vidometer-scene-demo

### Installation

Execute the following command in order to install dependencies:

```tsx
npm i
```

or

```tsx
yarn install
```

### Development

Execute the following command in order to run the application in development mode:

start:gltf - runs vidometer example with gltf object;

start:video - runs vidometer example with video;

start:image - runs vidometer example with image;

start:viewer - runs viewer example;

```tsx
npm run start:gltf
// OR
npm run start:video
// OR
npm run start:image
// OR
npm run start:viewer
```

OR

```tsx
yarn start:gltf
// OR
yarn start:video
// OR
yarn start:image
// OR
yarn start:viewer
```

Run the following URL on your mobile device:

```tsx
https://localhost:8080
```

# API

## vidometry-scene

***Attributes:***

***shadow-cast*** - optional, enables shadow casting functionality;

***Callbacks:***

***onLoading(progress)*** - throws when sources are loading, (form 0 to 1);

***onLoaded()*** - throws when all sources are loaded and experience ready to start;

***onStarted()*** - throws when experience is started;

```jsx
<vidometry-scene shadow-cast>
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

**Attributes:**

***preview*** - (optional) show model on the scene before the starting;

```jsx
<vidometry-scene id="scene">
	<vidometry-vidometer preview></vidometry-vidometer>
</vidometry-scene>
```

### vidometry-viewer

```tsx
<vidometry-scene>
	...
	<vidometry-viewer></vidometry-viewer>
	...
<vidometry-scene>
```

You can use Viewer for the development. Each axis on the scene is approximately 1.5m. 

### vidometry-vitracker

under development