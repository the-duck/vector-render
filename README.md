## Attention please !
This is a fork of the Vector Render addon built by Marco Rossini.
The intent of this fork is to adapt it for production. Here are some possible improvements :
- [workflow] Render operator into compositor node
- [workflow] RenderEngine
- [workflow] Rasterize image in realtime or just as compositing pass
- [visual] Apply a simple material language (per object or material) that can be interpreted to SVG
  --> my usage : for cartographic symbology
- [precision] Read lines and curves directly onto SVG (no need to transform to mesh)
- [visual] Apply holdout when objects are in this mode.
- [visual] Apply object outline (useful for holdout as well, if it is simpler than multiple faces)
- [calculation] Apply ray cast shadows from sun beam (self cast on object, cast by object)

Production usages:
- Technical CAD renders
- 3D cartography with certain precision (cadastre, ...)
- 

# Vector Render
Vector Render is a Blender add-on for creating vector graphics from the objects seen through the camera view.
This is useful for example in publications to illustrate three dimensional objects.
The advantage over normal renders using raster graphics is that there is no resolution problem when printing and that the file sizes can be quite small.

## Features
The add-on has the following features:

- Output formats: SVG (Scalable Vector Graphics) and Metapost
- Support for perspective and orthographic projection
- Rendering of mesh objects (with modifiers applied as an option)
- Drawing of text labels with positions in 3D
- Drawing of mesh edges/wireframe where edges obscured by geometry are . . .
  - hidden
  - drawn with a dash pattern
  - shown normally
- Hiding of edges within planes (using an angle limit)
- Drawing of mesh faces (coloured by material as an option)
- Shading using lamps (currently limited to sun lamps).

## Limitations
There are several limitations to the add-on which are mostly due to the nature of vector graphics:

- No smooth shading
- Shading works only with sun lamps (as of now)
- Intersecting polygons/objects won't work properly
- No cast shadows.

## Installation
1. Download the latest [release](https://github.com/mrossini-ethz/vector-render/releases) or clone the repository into a directory of your convenience.
2. If you downloaded the zip file, extract it.
3. Open Blender.
4. Go to File -> User Preferences -> Addons.
5. At the bottom of the window, chose *Install From File*.
6. Select the file `vector-render.py` from the directory into which you cloned/extracted the repository.
7. Activate the checkbox for the plugin that you will now find in the list.
