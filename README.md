```
⚠️ WINDOWS ONLY (Currently) ⚠️
This is very early stages. Feel free to contribute.
```

# Godot HTML

A GDExtension, using Ultralight, to render HTML.

<img src="docs/images/EditorView.png">
<img src="docs/images/InspectorView.png">


## Versions
- Godot 4.2
- Ultralight 1.4.0 Beta

## Table of contents
- [What can this plugin do?](#can-do)
- [What's left to do?](#to-do)
- [Prerequisites](#prerequisites)
- [Project Structure](#project-structure)
- [Building](#building)
  - [Clone godot-cpp](#clone-godot-cpp)
  - [Build Godot C++ bindings](#build-godot-cpp-bindings)
  - [Build plugin](#build-plugin)
- [JS Interop](#js-interop)

## CAN-DO
- Render HTML & CSS, with JS capabilities.
- HTML Inspector
- Mouse & Keyboard Input
- JS Interop

## TO-DO
- Only call render once per frame.
- Live code updates (Allow for html to update in the editor when file changed)
- ?? More will arrise I assume ??

## Prerequisites
- Setup [compiling](https://docs.godotengine.org/en/stable/contributing/development/compiling/compiling_for_windows.html) for Godot
- Download [Ultralight](https://ultralig.ht/download/)

## Project Structure
Your project should look like this before building the plugin.
```
main_folder/
|
+--demo/                  # game example/demo to test the extension
  |
  +--plugin_folder/
    |
    +--bin/               # plugin build folder / Other libraries
      +--Ultralight.dll
      +--UltralightCore.dll
      +--WebCore.dll
      +--AppCore.dll
    |
    +--resources/         # Ultralight resources folder (Copied from SDK folder)
  |
  +--inspector/           # Ultralight inspector folder (Copied from SDK folder)
|
+--godot-cpp/             # C++ bindings
|
+--src/                   # Source code of the extension we are building
|
+--ultralight/            # Ultralight SDK
```

## Building

### Clone godot-cpp
```
git submodule update --init --remote
```

### Build Godot C++ bindings
```
cd godot-cpp
scons platform=<platform>
```

### Build plugin

From the main folder.
```
scons platform=<platform>
```

## JS Interop
Using JS Interop requires an understanding of Ultralight.

Check out the [Ultralight Docs](https://docs.ultralig.ht/docs/about-javascript-interop) for more details.

Checkout `AppExample` for a basic implementation of calling a C++ function from JS.