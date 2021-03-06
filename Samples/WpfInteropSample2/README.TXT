﻿--------------------------------------------------------------------------------
Project WpfInteropSample2
--------------------------------------------------------------------------------
This project shows how to create a WPF application which displays 3D graphics.
(If you want to create MonoGame game which can open a WPF window, please look at
the project "WpfInteropSample" instead.)

--------------------------------------------------------------------------------
BUILD INSTRUCTIONS
--------------------------------------------------------------------------------
1. In Visual Studio open the solution "InteropSamples-MonoGame-Windows".
2. Build the project "Samples.Content.Pipeline-MonoGame".
   (This project is a content pipeline extension that is required to build the
   sample content.)
3. In Windows Explorer run
   "<DIGITALRUNE_FOLDER>\Samples\Build-Content-MonoGame-Windows.cmd".
   (This batch file calls the MonoGame Content Builder and builds the content
   project. The assets are packed into a ZIP archive.)
4. In Visual Studio build the solution.

--------------------------------------------------------------------------------
Description
--------------------------------------------------------------------------------
This project is a WPF application which displays 3D graphics.

Folder "Content":
This folder contains links to packaged graphics assets. Some of these assets are
pre-built assets of DigitalRune Graphics. Other assets are created by the content
build script (see BUILD INSTRUCTIONS).
The "Build action" of these items is set to "Content". "Copy to output directory"
is set to "Copy if newer".
Regular assets (XNB files) can be loaded in code using the XNA/MonoGame
ContentManager. Packaged assets (ZIP files) can be loaded using the DigitalRune
StorageContentManager.

Folder "Game":
The class MyGame initializes the game services and runs the "game loop".
The class MyGamePresentationTarget is a WPF element into which the MyGame class
renders the 3D graphics.
The class MyGraphicsService is a simple graphics screen that draws a scene graph
using forward rendering.
The class TestLevel creates the game level consisting of some lights and 3D
models.
