:github_url: hide

.. Generated automatically by doc/tools/make_rst.py in GaaeExplorer's source tree.
.. DO NOT EDIT THIS FILE, but the KinematicCollision2D.xml source instead.
.. The source is found in doc/classes or modules/<name>/doc_classes.

.. _class_KinematicCollision2D:

KinematicCollision2D
====================

**Inherits:** :ref:`Reference<class_Reference>` **<** :ref:`Object<class_Object>`

:ref:`KinematicBody2D<class_KinematicBody2D>` 动态物体2D碰撞器碰撞的数据。

描述
----

包含\ :ref:`KinematicBody2D<class_KinematicBody2D>`\ 碰撞的碰撞数据。当使用 :ref:`KinematicBody2D.move_and_collide<class_KinematicBody2D_method_move_and_collide>` 移动\ :ref:`KinematicBody2D<class_KinematicBody2D>`\ 时，如果检测到与另一个物体的碰撞，它将停止。如果检测到碰撞，则返回KinematicCollision2D对象。

该对象包含有关碰撞的信息，包括碰撞对象，剩余运动和碰撞坐标。该信息可用于计算碰撞响应。

属性
----

+-------------------------------+---------------------------------------------------------------------------------------+---------------------+
| :ref:`Object<class_Object>`   | :ref:`collider<class_KinematicCollision2D_property_collider>`                         |                     |
+-------------------------------+---------------------------------------------------------------------------------------+---------------------+
| :ref:`int<class_int>`         | :ref:`collider_id<class_KinematicCollision2D_property_collider_id>`                   | ``0``               |
+-------------------------------+---------------------------------------------------------------------------------------+---------------------+
| :ref:`Variant<class_Variant>` | :ref:`collider_metadata<class_KinematicCollision2D_property_collider_metadata>`       |                     |
+-------------------------------+---------------------------------------------------------------------------------------+---------------------+
| :ref:`RID<class_RID>`         | :ref:`collider_rid<class_KinematicCollision2D_property_collider_rid>`                 |                     |
+-------------------------------+---------------------------------------------------------------------------------------+---------------------+
| :ref:`Object<class_Object>`   | :ref:`collider_shape<class_KinematicCollision2D_property_collider_shape>`             |                     |
+-------------------------------+---------------------------------------------------------------------------------------+---------------------+
| :ref:`int<class_int>`         | :ref:`collider_shape_index<class_KinematicCollision2D_property_collider_shape_index>` | ``0``               |
+-------------------------------+---------------------------------------------------------------------------------------+---------------------+
| :ref:`Vector2<class_Vector2>` | :ref:`collider_velocity<class_KinematicCollision2D_property_collider_velocity>`       | ``Vector2( 0, 0 )`` |
+-------------------------------+---------------------------------------------------------------------------------------+---------------------+
| :ref:`Object<class_Object>`   | :ref:`local_shape<class_KinematicCollision2D_property_local_shape>`                   |                     |
+-------------------------------+---------------------------------------------------------------------------------------+---------------------+
| :ref:`Vector2<class_Vector2>` | :ref:`normal<class_KinematicCollision2D_property_normal>`                             | ``Vector2( 0, 0 )`` |
+-------------------------------+---------------------------------------------------------------------------------------+---------------------+
| :ref:`Vector2<class_Vector2>` | :ref:`position<class_KinematicCollision2D_property_position>`                         | ``Vector2( 0, 0 )`` |
+-------------------------------+---------------------------------------------------------------------------------------+---------------------+
| :ref:`Vector2<class_Vector2>` | :ref:`remainder<class_KinematicCollision2D_property_remainder>`                       | ``Vector2( 0, 0 )`` |
+-------------------------------+---------------------------------------------------------------------------------------+---------------------+
| :ref:`Vector2<class_Vector2>` | :ref:`travel<class_KinematicCollision2D_property_travel>`                             | ``Vector2( 0, 0 )`` |
+-------------------------------+---------------------------------------------------------------------------------------+---------------------+

方法
----

+---------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------+
| :ref:`float<class_float>` | :ref:`get_angle<class_KinematicCollision2D_method_get_angle>` **(** :ref:`Vector2<class_Vector2>` up_direction=Vector2( 0, -1 ) **)** |const| |
+---------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------+

属性说明
--------

.. _class_KinematicCollision2D_property_collider:

- :ref:`Object<class_Object>` **collider**

+----------+----------------+
| *Getter* | get_collider() |
+----------+----------------+

碰撞体。

----

.. _class_KinematicCollision2D_property_collider_id:

- :ref:`int<class_int>` **collider_id**

+-----------+-------------------+
| *Default* | ``0``             |
+-----------+-------------------+
| *Getter*  | get_collider_id() |
+-----------+-------------------+

碰撞体的唯一实例ID。参阅\ :ref:`Object.get_instance_id<class_Object_method_get_instance_id>`\ 。

----

.. _class_KinematicCollision2D_property_collider_metadata:

- :ref:`Variant<class_Variant>` **collider_metadata**

+----------+-------------------------+
| *Getter* | get_collider_metadata() |
+----------+-------------------------+

碰撞体的元数据。参阅\ :ref:`Object<class_Object>`\ 。

----

.. _class_KinematicCollision2D_property_collider_rid:

- :ref:`RID<class_RID>` **collider_rid**

+----------+--------------------+
| *Getter* | get_collider_rid() |
+----------+--------------------+

:ref:`Physics2DServer<class_Physics2DServer>` 使用的碰撞体的 :ref:`RID<class_RID>`\ 。

----

.. _class_KinematicCollision2D_property_collider_shape:

- :ref:`Object<class_Object>` **collider_shape**

+----------+----------------------+
| *Getter* | get_collider_shape() |
+----------+----------------------+

碰撞体的形状。

----

.. _class_KinematicCollision2D_property_collider_shape_index:

- :ref:`int<class_int>` **collider_shape_index**

+-----------+----------------------------+
| *Default* | ``0``                      |
+-----------+----------------------------+
| *Getter*  | get_collider_shape_index() |
+-----------+----------------------------+

碰撞形状的索引。参阅\ :ref:`CollisionObject2D<class_CollisionObject2D>`\ 。

----

.. _class_KinematicCollision2D_property_collider_velocity:

- :ref:`Vector2<class_Vector2>` **collider_velocity**

+-----------+-------------------------+
| *Default* | ``Vector2( 0, 0 )``     |
+-----------+-------------------------+
| *Getter*  | get_collider_velocity() |
+-----------+-------------------------+

碰撞对象的速度。

----

.. _class_KinematicCollision2D_property_local_shape:

- :ref:`Object<class_Object>` **local_shape**

+----------+-------------------+
| *Getter* | get_local_shape() |
+----------+-------------------+

移动对象的碰撞形状。

----

.. _class_KinematicCollision2D_property_normal:

- :ref:`Vector2<class_Vector2>` **normal**

+-----------+---------------------+
| *Default* | ``Vector2( 0, 0 )`` |
+-----------+---------------------+
| *Getter*  | get_normal()        |
+-----------+---------------------+

碰撞体的形状在碰撞点的法线。

----

.. _class_KinematicCollision2D_property_position:

- :ref:`Vector2<class_Vector2>` **position**

+-----------+---------------------+
| *Default* | ``Vector2( 0, 0 )`` |
+-----------+---------------------+
| *Getter*  | get_position()      |
+-----------+---------------------+

碰撞点，以全局坐标表示。

----

.. _class_KinematicCollision2D_property_remainder:

- :ref:`Vector2<class_Vector2>` **remainder**

+-----------+---------------------+
| *Default* | ``Vector2( 0, 0 )`` |
+-----------+---------------------+
| *Getter*  | get_remainder()     |
+-----------+---------------------+

移动物体的剩余运动向量。

----

.. _class_KinematicCollision2D_property_travel:

- :ref:`Vector2<class_Vector2>` **travel**

+-----------+---------------------+
| *Default* | ``Vector2( 0, 0 )`` |
+-----------+---------------------+
| *Getter*  | get_travel()        |
+-----------+---------------------+

运动物体在碰撞前行进的距离。

方法说明
--------

.. _class_KinematicCollision2D_method_get_angle:

- :ref:`float<class_float>` **get_angle** **(** :ref:`Vector2<class_Vector2>` up_direction=Vector2( 0, -1 ) **)** |const|

根据\ ``up_direction``\ 的碰撞角度，默认为\ ``Vector2.UP``\ 。这个值总是为正。

.. |virtual| replace:: :abbr:`virtual (This method should typically be overridden by the user to have any effect.)`
.. |const| replace:: :abbr:`const (This method has no side effects. It doesn't modify any of the instance's member variables.)`
.. |vararg| replace:: :abbr:`vararg (This method accepts any number of arguments after the ones described here.)`
