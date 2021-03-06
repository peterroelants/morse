How to efficiently add complex bounding boxes to your objects 
=============================================================

It is often important to simplify the bounding box of a complex object not to kill the performances of the MORSE physics engine.

Here is the "how-to"

#. Create plain boxes and put them around your object to shape the bounds.
#. Apply :kbd:`Ctrl-a` scaling on each boxes.
#. Choose one of them and parent all the other + the original object mesh to this box.
#. In the Physics properties, set the original object to ``No collision``
#. Set the collision properties for all other boxes belonging to the bounding box, not forgetting to set the radius to be smaller than the box. All the boxes must have their ``Collision bounds`` set to ``Box`` and ``Compound`` must be selected.
#. All the bounding boxes can be set as well to ``Invisible`` in the same Physics panel.

If you decide to use an Empty as parent, set its bounds to ``Convex Hull``, else a big "magic" box will wrap your empty.
