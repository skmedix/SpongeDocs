=====================
The Coordinate System
=====================

The Vanilla coordinate System
=============================

.. explain default system here
   - origin, 0°, etc.

By default Minecraft uses a right-handed cartesian coordinate sytem to describe the position of an entity.
The ``X`` coordinate is used to determine the East/West position, while the ``Z`` coordiante is used for North/South
and finally the ``Y`` coordiante for the height. However this only represents the position of the Entity, not its
orientation.

Minecraft introduces two angles to cover the orientation of the player. First an angle for the horizontal plane
(looking left and right) and second an angle representing the vertical view (looking up and down).

Turning clockwise increses the first angle. It ranges from negative 180° to positive 180°, with the zero point facing
towards positive ``Z`` (East). The second angle zeros when looking horizontal and increases when lowering the sight. It
range is -90° to 90°.

While this suffices for Vanilla Minecraft, we want to be able to rotate entities in every possible direction. Thus,
there's a need to introduce a better representation of at least the orientation of an entity.

Euler angles
============

That's when Euler angles come into play. Euler angles are three angles that describe the orientation of an entity in an
3D space. Usually they're known as ``Pitch``, ``Yaw`` and ``Roll``. Each of this angles is tied to an axis:

* ``Pitch`` represents a rotation around the ``X`` axis,
* ``Yaw`` represents a rotation around the ``Y`` axis and
* ``Roll`` represents a rotation around the ``Z`` axis.

This leaves us with 3 cartesian coordinates plus 3 angles to fully describe the position and orientation of an entity
in 3D space. While this representation is as sane as it can be, we'll mostly run into issues when we try to use it.

Quaternions and Flowpowered math
================================

This is where Quaternions and the Flowpowered math library come in handy.


Converting from Eulerangles to cartesian coordinates
====================================================

.. Eulerangels -> XYZ
