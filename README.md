# THREE.js / WebGL Tutorial
A demonstration of how to use 3D Web Graphics to re-create a classic screensaver, this time with a bouncing die.

<!-- BADGES -->
[![](https://badgen.net/github/license/thehale/threejs-dice-screensaver)](https://github.com/thehale/threejs-dice-screensaver/blob/master/LICENSE)
[![](https://badgen.net/badge/icon/Sponsor/pink?icon=github&label)](https://github.com/sponsors/thehale)
[![](https://img.shields.io/badge/LinkedIn-thehale-0A66C2?logo=linkedin)](https://linkedin.com/in/thehale)

![3D Dice Screensaver](./tutorial/images/final.gif)

_Video Overview: https://youtu.be/K_Z1ZWucn-c_

Created by Jacob Janes, Joseph Hale, and Brent Watkins as part of an "Advanced Topic" project for SER421 - Web Application Programming at Arizona State University during the Fall 2021 Semester.

## Table of Contents
* [Learning Outcomes](#learning-outcomes)
* [Learning Activities](#learning-activities)
* [History](#history)
* [Analysis](#analysis-and-future-outlook)
* [References](#references)
* [Resources](#resources)

## Learning Outcomes 
### Learning Outcome 1: Geometries and Meshes
The student will be able to use `THREE.js` to draw basic 3D objects in a web browser.
### Learning Outcome 2: Textures
The student will be able to use `THREE.js` to add color and images to 3D objects.
### Learning Outcome 3: Animation
The student will be able to create a basic render loop in `THREE.js` to create visible animations of 3D objects in the browser window.
### Learning Outcome 4: Interactivity
The student will be able to connect 3D objects to browser events to dynamically move and manipulate objects on the scene in response to user input.
### Learning Outcome 5: Lighting
The student will be able to use `THREE.js` to create lighting effects on 3D objects moving in the browser window.
### Learning Outcome 6: Normal Maps
The student will be able to use `THREE.js` to apply normal maps and depth to 3D objects.

## Learning Activities
We've created six activities to teach the basics of 3D rendering on the web using `THREE.js`, a beginner-friendly library for working with WebGL.
You can find the tutorial in the `tutorial` folder of this project or by clicking [here](./tutorial/tutorial.md).

## History
The first computer graphics design dates back to 1963. 
Early computer graphics had to be made by directly talking with graphics hardware, but when graphics hardware was updated the graphics software had to be refactored in order to align with the hardware updates. 
Early Graphics Libraries (GLs) helped this issue a little, but most libraries were designed to only work with one operating system and with specific hardware. 
Portability and maintainability of graphics software suffered because of this weakness. 

### OpenGL
In an attempt to create a more useful graphics API that could work cross-platform, Mark Segal and Kurt Akeley created a Graphics Library named OpenGL in 1992.
In the 1.0 Specification document, OpenGL is described as "a software interface to graphics hardware.
The interface consists of a set of several hundred procedures and functions that allow a programmer to specify the objects and operations involved in producing high-quality graphical images, specifically color images of three-dimensional object" (Segal and Akeley, pg. 1). 

Below is a brief overview of OpenGL releases and major features:
- OpenGL 1.0 created basic 3D rendering functionality such as creating shapes and polygons, lighting, and rasterization. 
    - OpenGL 1.1 through 1.5 added more functionality related to textures.
- OpenGL 2.0 provided users with shader features and abilities.
- OpenGL 3.0 provided users with new context creation as well as profiles. This release also marked many previous, outdated features as depreciated, with the intent to remove those features completely in the next release (3.1)
    - OpenGL 3.1 removed all the depreciated features listed in version 3.0 except for wide lines.
    - OpenGL 3.2 and 3.3 updated the shading language used and provided extensions for core features, such as blending capabilities and additional shading and texture effects.
- OpenGL 4.0 once again updated the shading language and created more extensions, like tessellation.
    - OpenGL 4.1 through 4.6 (the most recent release) continued to add core extensions, create validation of objects, colors, and effects, and created compatibility with current OpenGL ES versions. 

### OpenGL ES
While OpenGL is powerful in creating and rendering graphics, this process uses many hardware resources.
While laptops, desktops, and other large systems are better suited for rendering OpenGL graphics, 
mobile and embedded systems had difficulty and poor performance rendering these same graphics.

To provide better performance and capabilities with mobile and embedded systems, the OpenGL team created OpenGL ES!
OpenGL ES stands for OpenGL for Embedded Systems. 
OpenGL ES provides better graphics rendering capabilities for devices such as smartphones, consoles, and vehicles by including core features and functionality of OpenGL that can be run on low-power devices.
Through this design, most graphics-capable embedded systems can render OpenGL ES graphics without majorly affecting performance and battery life.

Below is a brief overview of OpenGL ES releases and features:
- OpenGL ES 1.0 and 1.1 were created with comparison to OpenGL 1.5 and its features.
1.0 and 1.1 allowed developers to use fixed function graphics acceleration
- OpenGL ES 2.0 was created with comparison to OpenGL 2.0 and its features.
2.0 allowed developers to program shaders and shading effects.
- OpenGL ES 3.0 was created with comparison to OpenGL 3.0 and its features.
    - 3.0 allowed multiple render targets and provided additional texture features.
    - 3.1 allowed general purpose compute.
    - 3.2 incorporated additional features based on an official Android extension

### WebGL
As technologies continued to improve, the Internet increasingly became a new platform for creating, sharing, accessing, and hosting content and applications.
Web browsers became an ideal place for software developers to host cross-platform applications and include graphics within their web applications.
To provide graphics libraries for web applications, WebGL was created! 
WebGL 1.0 was essentially OpenGL ES 2.0 implemented in JavaScript, 
and this allowed graphical features and functionality to be created with the Internet in mind.

One of the major aspects of WebGL is that it does not require any plug-ins, 
and it utilizes web abilities from HTML and resources from browsers. 
Because of these benefits, WebGL has become a powerful, cross-platform library that is supported by all major browsers, 
allowing programmers to create and share their web applications for virtually all web users to use.

Below is a brief overview of WebGL releases and features:
- WebGL 1.0 implements OpenGL ES 2.0 in JavaScript, providing similar functions and features described above.
- WebGL 2.0 is comparable to OpenGL ES 3.0, and incorporates compatibility with HTML5 features, such as HTML5 Canvas elements.

## Analysis and Future Outlook
_Jacob and Joseph_

Many aspects of web programming can be difficult to understand, which often makes it hard to just get started with learning new advanced topics like 3D rendering.
While plain CSS and JS offer a lot of customizable fields and script options that have revolutionized the web industry, they don't have the power or ease of creating advanced 3D graphics provided by WebGL.
THREE.js takes this a step further and simplifies the WebGL API to one that is easier for beginners to pick up and start working with (albeit by limiting some key functionality like boolean object operations and advanced shader development).

For people used to another 3D rendering framework like Unity, these tools will feel very familiar since they utilize DOM manipulation and scene manipulation similarly.
This parity simplifies the HTML interactions for many developers and opens up opportunities to treat web development like engine development.

As for the future, since it's founded on the battle-hardened, industry-standard, decades-proven OpenGL, we feel confident that WebGL is here to stay.
Additionally, at the time of writing, THREE.js has [76k stars on GitHub](https://github.com/mrdoob/three.js) and [2k dependent packages on npm](https://www.npmjs.com/package/three), which indicates its widespread appeal and acceptance. As such, we also feel like THREE.js is here to stay. 

With its approachability for beginners and developers coming from other frameworks, we see THREE.js as a great tool for anyone who wants to start creating 3D content on the web.

_Brent_

3D modelling with graphics libraries like WebGL and THREE.js are definitely powerful in their abilities.
However, there is a learning curve when starting to use these graphics libraries and trying to render objects in 3D.
Thankfully WebGL and THREE.js have excellent documentation to help developers know how to use these libraries.

Personally, I feel like the application of 2D/3D modelling has a very specific target field.
Websites with 2D or 3D games are one of the first types of websites I thought would only use web graphics,
but after viewing example websites on the THREE.js main website I can see that other types of interactive websites 
(like NASA's interactive mission to Mars listed on the THREE.js main website) can benefit from web graphics.
I believe that content hosting websites or websites involved with transactions (such as banking websites) have the least
benefit to using 3D graphics, as 3D graphics can create a User Interface that may make many users confused with the
key functionality of those websites. Most content and functionality for these do not need to be rendered in a special 
2D/3D way.
Websites demonstrating a product, simulating an event, or presenting information in a visually appealing way can 
benefit from the ease of development and visual effects available with 2D/3D graphics libraries on the web.

## References
* OpenGL summary and version history: https://www.khronos.org/opengl/wiki/History_of_OpenGL
* OpenGL ES overview and homepage: https://www.khronos.org/opengles/
* WebGL overview and homepage: https://www.khronos.org/webgl/
* WebGL 1.0 Documentation (Work in Progress document): https://www.khronos.org/registry/webgl/specs/latest/1.0/
* WebGL 2.0 Documentation (Work in Progress document): https://www.khronos.org/registry/webgl/specs/latest/2.0/
* An overview of web graphics with a focus on OpenGL: http://learnwebgl.brown37.net/the_big_picture/webgl_history.html
* WebGL animation and textures: https://developer.mozilla.org/en-US/docs/Web/API/WebGL_API/Tutorial/Using_textures_in_WebGL
* Picking and intersection tracking for objects: https://threejsfundamentals.org/threejs/lessons/threejs-picking.html
* Rendering on demand: https://threejsfundamentals.org/threejs/lessons/threejs-rendering-on-demand.html
* Mouse tracking objects: https://www.demo2s.com/javascript/javascript-three-js-object-follows-mouse-position.html
* Mouse over object for intersection: https://pretagteam.com/question/threejs-projector-and-ray-objects

## Resources
* "Awesome WebGL" - A curated list of WebGL resources: https://github.com/sjfricke/awesome-webgl
* Three.js Official Documentation: https://threejs.org/
* Three.js Fundamentals Tutorial: https://threejsfundamentals.org/threejs/lessons/threejs-lights.html
* Bablyon.js Official Documentation: https://doc.babylonjs.com/
* Mozilla Developer Network Guide to WebGL: https://developer.mozilla.org/en-US/docs/Web/API/WebGL_API
* Khronos Group WebGL 2.0 Specification: https://www.khronos.org/registry/webgl/specs/latest/2.0/ 
* Fireship.io's 3D Portfolio Website Tutorial: https://www.youtube.com/watch?v=Q7AOvWpIVHU
* Guillaume Gouessan's interactive slides about 3D graphics on the web: https://guillaumegouessan.com/talk/workshop/
* Guillaume Gouessan's interactive slides about movement and translation on the web: https://guillaumegouessan.com/talk/move/
* How to make a normal map in Photoshop: https://dreamlight.com/how-to-create-normal-maps-from-photographs/
* How to make a normal map in GIMP: https://www.youtube.com/watch?v=77Nd7yXuSgg

