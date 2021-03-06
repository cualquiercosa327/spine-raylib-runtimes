# spine-raylib

<img align="left" src="./assets/raylib_logo.png" width="256">

The spine-raylib runtime provides functionality to load, manipulate and render [Spine](http://esotericsoftware.com) skeletal animation data using [Raylib](https://www.raylib.com/). spine-raylib is based on [spine-c](https://github.com/EsotericSoftware/spine-runtimes/tree/3.8/spine-c).

One of the most amazing features of [Raylib](https://www.raylib.com/), besides the ease of use and its numerous ports to several languages, is the ability to compile to [WebAssembly](https://webassembly.org/), allowing to show your games arround the world with just a link.

## Known Bugs
I think it's fair to let you know the problems early. So here it goes: The 3D part is buggy. If you want to use it in 2D it will work like a charm. But you are going to have problems with alpha if you use it in 3D. I think I can fix it somehow, but I need to learn more about how 3D works. So there you have it. Do your own research and let me know if you make it work!. A PR will be a nice thing to have. Thanks in advance. 

## Licensing
You are welcome to evaluate the Spine Runtimes and the examples we provide in this repository free of charge.

You can integrate the Spine Runtimes into your software free of charge, but users of your software must have their own [Spine license](https://esotericsoftware.com/spine-purchase). Please make your users aware of this requirement! This option is often chosen by those making development tools, such as an SDK, game toolkit, or software library.

In order to distribute your software containing the Spine Runtimes to others that don't have a Spine license, you need a [Spine license](https://esotericsoftware.com/spine-purchase) at the time of integration. Then you can distribute your software containing the Spine Runtimes however you like, provided others don't modify it or use it to create new software. If others want to do that, they'll need their own Spine license.

For the official legal terms governing the Spine Runtimes, please read the [Spine Runtimes License Agreement](http://esotericsoftware.com/spine-runtimes-license) and Section 2 of the [Spine Editor License Agreement](http://esotericsoftware.com/spine-editor-license#s2).

## Examples

This CMake-based project is an example of how to use the library on a 2D setting.

### Example 2D
[Example 2D](https://htmlpreview.github.io/?https://github.com/WEREMSOFT/spine-raylib-runtimes/blob/master/html/example_2d/example_2d.html)

<img src="./doc_images/example_2d.png" width="300">

### Example 2D Mesh Based Animation
[Example 2D mesh](https://htmlpreview.github.io/?https://github.com/WEREMSOFT/spine-raylib-runtimes/blob/master/html/example_2d_owl/example_2d_owl.html)

<img src="./doc_images/example_2d_owl.png" width="300">

### Example 2D Mesh Based Animation spine 3.7
[Example 2D 3.7](https://htmlpreview.github.io/?https://github.com/WEREMSOFT/spine-raylib-runtimes/blob/master/html/example_2d_cat/example_2d_cat.html)

<img src="./doc_images/example_2d_cat.png" width="300">

### Example 3D
[Example 3D](https://htmlpreview.github.io/?https://github.com/WEREMSOFT/spine-raylib-runtimes/blob/master/html/example_3d/example_3d.html)

<img src="./doc_images/example_3d.png" width="300">

For more examples regarding RayLib, a huge list of [examples](https://www.raylib.com/examples.html) can be found on the [raylib examples page](https://www.raylib.com/examples.html).



## Spine version

spine-raylib works with data exported from Spine 3.8.x and Spine 3.7.x. Check the demos for how to prepare your project for different assets versions.

## Setup

1. Download the Spine Runtimes source using [git](https://help.github.com/articles/set-up-git) or by downloading it as a zip via the download button above.
1. Use the file src/example_2d.c for an example with a 2D camera. Use src/example_3d.c for an example with a 3D camera.
1. Compile and run. If you need extra help compiling in the different platforms, check the awesome [Raylib documentation](https://github.com/raysan5/raylib/wiki) under the **Development Platforms** section.

## Notes

In order to use the generic C runtimes from Spine, you need to implement a bunch of functions on your code. 
All these functions are in src/spine-raylib.h and they are independent from spine runtime library.

The intention of this is to give the freedom to the user to upgrade the spine runtime libraries if needed with very little or no changes.

In order to upgrade the spine library, you have to download the [spine-c](https://github.com/EsotericSoftware/spine-runtimes/tree/3.8/spine-c) library and overwrite the /lib/include/spine and the /lib/src/spine folders.

The function ```drawSkeleton(skeleton, skeletonPosition)``` draws the spine in 3d coordinates, so it can be used as a billboard, but is the user who needs to orientate the spine skeleton to the camera during the game loop.

This project is based on CMake as a build pipeline.
