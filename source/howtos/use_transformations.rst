Using transformations
=====================

Matrix transformations in RoboFab are done with the help of the matrix module from ``fontTools``. ``RContour``, ``RPoint``, ``bPoint``, ``RGlyph`` all have ``transform()`` methods which accept a matrix object.

Transform objects and the Identity transform
--------------------------------------------

A Transform object from fontTools is a 2×2 transformation matrix plus offset, a.k.a. Affine transform. Transform instances are "immutable": all transforming methods, eg. ``rotate()``, return a new ``Transform`` instance. One way to make a new transform object is by importing the **Identity** transform from ``fontTools.misc.transform``. Identity is an instance of ``Transform`` and it is initialised to transform to itself (i.e. no visible transformation). The you modify the Identity object: each method (such as ``rotate()``, ``translate()`` etc) returns a new ``Transform`` object with the last transformation added to it.

Oh no! Math!
^^^^^^^^^^^^

Transform objects are a fast and powerful way to do math with matrices. If you don't know what that means don't worry. If you follow the examples you can build Transform objects that rotate, translate and skew. Of course you can look up **affine transform** on google for some more in depth explanation of transformations.

Angles
^^^^^^

Angles in all Python's math modules are measured in **radians** by default. A radian is a (perhaps) more scientific unit for angles than the regular "degrees", measuring the "distance travelled" over the circle rather than the angle. The length of a full circle (with radius 1) is 2 * pi. 90 degrees = 1/2 pi radians. One can easily be converted to the other using conversion methods from the math module::

    import math
    # example of a conversion of degrees to radians
    print math.radians(90)
     
    # example of a conversion from radians to degrees
    print math.degrees(math.pi)

Example
^^^^^^^

.. showcode:: ../../examples/howtos/transformations_00.py

.. code::

    < Transform [1 0 0 1 0 0] >
    < Transform [0.939692620786 0.342020143326 -0.342020143326 0.939692620786 0 0] >

---------------------------
Methods of Transform object
---------------------------

See the source code of ``fontTools.misc.transform`` for detailed descriptions and examples.

.. py:function:: reverseTransform()

Return a new transformation, which is the other transformation transformed by ``self``. ``self.reverseTransform(other)`` is equivalent to ``other.transform(self)``.

.. py:function:: rotate(angle)

Return a new transformation, rotated by ``angle`` (in radians).

.. py:function:: skew(x, y)

Return a new transformation, skewed by ``x`` and ``y`` (in radians).

.. py:function:: scale(x=1, y=None)

Return a new transformation, scaled by ``x`` and ``y``. The ``y`` argument may be ``None``, which implies to use the ``x`` value for ``y`` as well.

.. py:function:: toPS()

Return a string with the values of the transform written out in the PostScript manner: ``[1 0 0 1 0 0]``.

.. py:function:: transform(other)

Return a new transformation, transformed by another transformation.

.. py:function:: inverse()

Return the inverse transformation.

.. py:function:: transformPoint((x,y))

Transform a point, i.e. apply the transformation to the point.

.. py:function:: transformPoints(points)

Transform a list of points.
