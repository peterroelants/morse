Semantic camera sensor
======================

This sensor emulates a hight level camera that outputs the names of the objects
that are located within the field of view of the camera.

The sensor determines first which objects are marked with a **Logic Property**
called **Object**, of type String and which should have the same value as the
name of the object.
Then a test is made to identify which of these objects are inside of the view
frustum of the camera. Finally, a single visibility test is performed by casting
a ray from the center of the camera to the center of the object. If anything
other than the test object is found first by the ray, the object is considered
to be occluded by something else, even if it is only the center that is being
blocked.

The cameras make use of Blender's **VideoTexture** module, which requires a
graphic card capable of GLSL shading. Also, the 3D view window in Blender must be
set to draw **Textured** objects.

Files
-----

- Blender: ``$MORSE_ROOT/data/morse/components/sensors/morse_camera.blend``
- Python: ``$MORSE_ROOT/src/morse/sensors/semantic_camera.py``


Local data
----------

- **visible_objects**: (List) An array with the names of the objects visible by
  the camera.

Configurable parameters
-----------------------

The Empty object corresponding to this sensor has the following parameters:

- **capturing**: (Boolean) flag that determines whether the camera should
  generate an image. It can be toggled on or off by pressing the :kbd:`Space`
- **cam_width**: (double) generated image width in pixels
- **cam_height**: (double) generated image height in pixels
- **cam_focal**: (double) camera focal length as defined in Blender.
  Not really important for this kind of camera.

Applicable modifiers
--------------------

No camera modifiers available at the moment
