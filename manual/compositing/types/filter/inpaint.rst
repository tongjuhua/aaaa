.. _bpy.types.CompositorNodeInpaint:

************
Inpaint Node
************

.. figure:: /images/compositing_nodes_filter_inpaint.png
   :align: right

   Inpaint Node.

The *Inpaint node* is used to extend borders of an image into transparent or masked regions.
This can be useful to solve problems like "wire removal" and holes created during chroma-keying.


Inputs
======

Image
   Standard image input.


Properties
==========

Distance
   The number of times to extend the image.

Outputs
=======

Image
   Standard image output.


Examples
========

In the left image shows the "wire" in place and after chroma-key has been applied you will see you're left
with a blank space -- it's shown as a black line here but it will be alpha in your Blender output.

.. figure:: /images/compositing_nodes_filter_inpaint_example.png

   Inpaint Node Example.

Inpainting fills in a couple of pixels using the surrounding image and voilà... your wire is removed.

.. note::

   The wider your "hole" is, the more noticeable this effect is!
   If you use more than a few pixels of infill,
   the effect is almost as irritating as the wire and your viewers won't be impressed.

Inpainting can also cover up a multitude of other minor sins
such as control points for motion capture: use it sparingly and it will amaze.
