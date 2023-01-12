<!--
author:   Peter Wackernagel, Hochschule für Bildende Künste Dresden
email:    wackernagel@hfbk-dresden.de
version:  0.0.3
logo:     A-Frame_logo.png
language: en
narrator: English Female
comment:  Digital spaces in VR with A-Frame
mode:     textbook
dark:     true
date:     01/12/2023
@classroom: disable
@sharing: true
-->

# 1 Introduction

[A-Frame](https://aframe.io/docs/1.4.0/introduction/) is an open source project that allows you to build VR on top of regular HTML, so you can create a WebXR experience just as easily as you can make a web page, simply by including a script and markup in your page. With A-Frame, you can create cross-platform VR apps that users across multiple device types can access.

---

**A-Frame Samples**

Sample applications on the A-Frame home page: [https://aframe.io/](https://aframe.io/)

![Screenshot](AFrame_Website.png)

Navigation in the scenes is done

- on **desktop** with the arrow keys or WASD (if enabled)
- on **mobile devices** with finger gestures
- on **VR headsets** by active body movement.
- The **VR** button in the right corner puts the scene in full screen or VR view.

More examples: [glitch.com/webxr](https://glitch.com/webxr)

---

## HTML-Code

![Screenshot Starter Template Code](AFrame_Starter-Template-Source.png)

- HTML (Hyper Text markup Language) is the language used to describe web pages.
- A-Frame uses this language to describe the objects of the scene

---

**Tags**

```html
<tag></tag>
```

- An HTML element consists of **tags**. It is always formed from an opening-tag and a closing-tag.
- Tags can have different names and thus different functions.
- tags must be surrounded by angle brackets, the closing-tag has a preceding slash.

---

**Attributes**

```html
<tag attribute></tag>

<tag attribute="value"></tag>
```

- In the opening-tag there can be attributes that define further properties of the element.
- Attributes often also have a value, which consists of numbers, color values or text expressions.
- Attribute and value are connected without spaces with the is-equal sign, the value is always in quotes.

---

**Nested elements**

```html
<tag1 attribute="value">
	<tag2 attribute="value"></tag2>
	<tag3 attribute="value"></tag3>
</tag1>
```

- Elements can be nested and placed between the opening-tag and the closing-tag of the outer element..
- This way, tag1 works like a container which groups the nested tags together.

---

**Comments**

```html
<tag attribute="value">
	<tag2 attribute="value"></tag2> <!-- this comment will not be interpreted by the browser -->
</tag>
```

- Comments can be included with hints about the code.
- Comments are framed with angle brackets, execution marks and 2 minus signs as above.

---

**Syntax**

```html
<tag attribute="value"></tag>
```

- the correct use of characters is essential
- missing brackets or quotation marks or additional spaces in attributes lead to errors in the display.
- HTML for web pages still uses content between tags. For A-Frame this is unnecessary.

---

**Structure of an HTML page**

```html
<!DOCTYPE html>
<html>  
	<head>  <!-- invisible part with metadata and scripts -->  </head>  
	<body>  <!-- visible part with texts, media, A-Frame scene -->  </body>  
</html>
```

- The basic structure of an HTML page is standardized and is divided into the areas:

	- Head: invisible part with metadata and scripts.
	- Body: visible part with texts, media, AFrame scene.

- Blank lines can be placed between them as desired and make it easier to keep track.
- There should be no text outside of tags, except for comments.

---

## A-Frame Base scene

```html
<!DOCTYPE html>
<html>  
  <head>  
    <script src="https://aframe.io/releases/latest/aframe.min.js"></script>  
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

The code-highlighting makes it easier for us to distinguish the individual components. Depending on the program used, there can be different colors here, but the division of the syntax (the code language) into different colors is always the same.

---

**Script**

```html
  <head>  
    <script src="https://aframe.io/releases/latest/aframe.min.js"></script>  
  </head>  
```

The Java script linked in the head is what makes the scene work. This is the actual A-Frame "program".

It is a program code that interprets the scene specified in the body, displays it and controls its operation on different devices.

This program code can be viewed by calling the URL directly in the browser:

- Data saving minimized variant, poorly readable for humans: https://aframe.io/releases/latest/aframe.min.js
- Structured, annotated and easy to read variant: https://aframe.io/releases/latest/aframe.js
- There are different versions of the script. Instead of *latest* there is often a specific version number in the URL of the linked script, for example 1.4.0.

---

**Scene**

```html
<a-scene>  
	<a-box position="-1 0.5 -3" rotation="0 45 0" color="#4CC3D9"></a-box>  
	<a-sphere position="0 1.25 -5" radius="1.25" color="#EF2D5E"></a-sphere>  
	<a-cylinder position="1 0.75 -3" radius="0.5" height="1.5" color="#FFC65D"></a-cylinder>  
	<a-plane position="0 0 -4" rotation="-90 0 0" width="4" height="4" color="#7BC8A4"></a-plane>  
	<a-sky color="#ECECEC"></a-sky>  
</a-scene>  
```

- The A-Frame scene is initialized by the *a-scene* tag. The scene objects are nested inside this tag.
- All tags belonging to A-Frame have a prefix *a-* to distinguish them from standard HTML tags.

---

Each **element** *a-box*, *a-sphere*, *a-cylinder* etc. describes a single **object** within the scene with the following attributes:

- position = x y z = width height depth

	- Numbers separated by blanks, in meters but without units
	- Depth z: -z moves away from the camera. Positive values are behind the camera

- rotation: data as for position
- radius, width, height: data depending on object type (cylinder, surface)
- color: hexadecimal specification: red, green and blue components:

	- Hex Colors: https://www.w3schools.com/colors/colors_hexadecimal.asp
	- color Picker: https://www.w3schools.com/colors/colors_picker.asp
	- color names are also possible: https://www.w3schools.com/colors/colors_names.asp

---

## Practice

**Code Hosting**

A server environment is required for A-Frame to run in the browser. The easiest way to start is to use the code hosting platform Glitch.com to develop your own project. There you will also find numerous projects that can be built upon. 

Advantages of code hosting:

- immediate deployment online, no need to have your own hosting
- full function of dynamic scripts

--- 

**Starter Template**

We'll use the A-Frame Starter-Template on glitch.com: [https://glitch.com/~aframe](https://glitch.com/~aframe)

![Screenshot Starter Template](Starter-Template.png)

> Hit **Remix your own** to start your own project based on this project.
> Play around with this scene to see what will happen.


# 2 Building the scene

## A-Frame Primitives

A-Frame provides a handful of elements such as *a-box* or *a-sky* called primitives that wrap the entity-component pattern to make it appealing for beginners. These are some examples with additional attributes:

**a-box**

The box primitive creates shapes such as boxes, cubes, or walls.

```html
<a-box width="0.5" height="2" depth="1" position="-1 1 -4" color="red"></a-box>
<a-box width="1" height="0.5" depth="2" position="1 1 -4" color="green" wireframe="true" wireframe-linewidth="2"></a-box>
```

---

**a-cylinder**

The cylinder primitive is used to create tubes and curved surfaces.

```html
<a-cylinder color="crimson" height="3" radius="1.5" position="0 1 -5"></a-cylinder>
```

---

**a-plane **

The plane primitive creates flat surfaces.

```html
<a-plane position="0 1 -4" rotation="0 45 0" width="4" height="4" color="#7BC8A4"></a-plane>
<a-plane color="grey" height="20" width="20" position="0 0 -10" rotation="-90 0 0"></a-plane> <!-- Ground plane -->
```

---

**a-sphere**

The sphere primitive creates a spherical or polyhedron shapes.

```html
<a-sphere color="yellow" radius="1" position="0 1 -5"></a-sphere>
```

---

**a-text**

Adds a text.

```html
<a-text value="Hello, World!" color="black" position="0 1 -3"></a-text>
```

---

**a-image**

The image primitive shows an image on a flat plane.

```html
<a-image src="image.jpg" width="3" height="2" position="0 1 -5"></a-image>
```

- mages can be uploaded on glitch into the assets-folder. Copy their URL from there and paste it into the src-attribute of the element.
- Ensuring that the image is not distorted by stretching requires us to appropriately set the width and height preserving the original aspect ratio of the image. This properties are set in meters, don’t confuse with pixels.

---

**a-sky**

The sky primitive adds a background color or 360° image to a scene. A sky is a large sphere with a color or texture mapped to the inside.

``` html
<a-sky color="#6EBAA7"></a-sky> <!-- background color -->
<a-sky src="sky.jpg"></a-sky> <!-- equirectangular background-image -->
```

- You can download Sky-Images here: https://polyhaven.com/hdris ... Use the 8K Tonemapped-JPG from the hamburger-menu on the upper right.
- To use the image with A-Frame on the web, you should downscale (4K: 4096px width is enough) and compress it again (JPG,medium compression, ca. 75%). You can do this locally with IrfanView or Photoshop and online using [Photopea](https://www.photopea.com/).

---

**More**

You can find every primitive that A-Frame provides out of the box at the bottom of the documentation navigation sidebar: https://aframe.io/docs/1.4.0/primitives/a-box.html

Developers can create their own primitives as well.

---

## A-Frame Entities

A-Frame elements can be specified in 2 ways: as a special primitive (e.g. a-box) or as a general entity (a-entity) together with components.  
Primitives are simplifications for the representation of common objects and refer to entities within A-Frame.

```html
<a-box color="red" width="3"></a-box>

<a-entity geometry="primitive: box; width: 3" material="color: red"></a-entity>
```

Detailed information is available at
- https://aframe.io/docs/1.4.0/introduction/html-and-primitives.html und
- https://aframe.io/docs/1.4.0/introduction/entity-component-system.html

---

**Tip: making groups**

Entities can also be used to group other objects. This allows several objects to be positioned together, e.g.:

```html
<a-entity position="0 0 -5" rotation="0 45 0">
	<a-box position="-2 0 0"></a-box>
	<a-box position="0 0 0"></a-box>
	<a-box position="2 0 0"></a-box>
</a-entity>
```

In Blender, this is comparable to using an *empty* as a parent for other objects.
 
---

## Practice

> Develop your scene with different objects.
> Try your scene on different devices: desktop, mobile and VR.

