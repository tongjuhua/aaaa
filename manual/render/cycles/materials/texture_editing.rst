
***************
Texture Editing
***************

3D View draw types, UV mapping,
and texture painting work somewhat differently when Cycles is enabled.
UV Maps no longer get image textures assigned themselves;
rather they must always be assigned by adding an image texture node to a material.


3D View Draw Types
==================

The Texture draw types used for Blender Internal have been replaced by three others in Cycles:

Texture
   This draw mode is used for editing, painting and mapping individual textures.
   Lighting is the same as in solid mode, so this is similar to the existing textured solid for Blender Internal.
   The texture drawn is the active image texture node for the material.
Material
   A simplified version of the entire material is drawn using GLSL shaders.
   This uses solid lighting, and also is mostly useful for editing, painting and mapping textures,
   but while seeing how they integrate with the material.
Rendered
   In this draw mode the render engine does the drawing,
   interactively refining the full rendered image by taking more samples.
   Unlike offline rendering, objects still use the viewport rather than render resolution and visibility.

.. figure:: /images/render_cycles_materials_texture-editing_draw-modes.jpg

   Material draw modes (Texture, Material, Rendered).


Texture Properties
==================

.. figure:: /images/cycles_texture_tab_menu.jpg
   :width: 225px
   :align: right


In the texture properties,
the texture can now be selected from a list that contains all texture nodes from the world,
lamps and materials, but also from e.g. modifiers, brushes and physics fields.

For shading nodes, the available textures are Cycles textures. For others,
Blender textures are still used, but this will change in the future.

.. container:: lead

   .. clear


Painting & UV Editing
=====================

.. figure:: /images/cycles_texture_active.png
   :align: right

For texture paint mode,
the image that is painted on is taken from the active image texture node.
This can be selected in the Node editor or the texture properties,
and it is indicated as blue in the material properties.

For UV mapping, the active UV map as specified in the mesh properties is used.
Assigning images in the UV/Image editor also affects the active image texture node.
