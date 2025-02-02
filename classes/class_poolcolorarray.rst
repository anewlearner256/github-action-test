:github_url: hide

.. Generated automatically by doc/tools/make_rst.py in GaaeExplorer's source tree.
.. DO NOT EDIT THIS FILE, but the PoolColorArray.xml source instead.
.. The source is found in doc/classes or modules/<name>/doc_classes.

.. _class_PoolColorArray:

PoolColorArray
==============

:ref:`Color<class_Color>`\ 的\ :ref:`Array<class_Array>`\ 的集合。

描述
----

专门用于保存\ :ref:`Color<class_Color>`\ 的\ :ref:`Array<class_Array>`\ 。对内存的使用进行了优化，不会使内存碎片化。

\ **注意：** 这种类型是通过值传递的，而不是引用。

方法
----

+---------------------------------------------+-----------------------------------------------------------------------------------------------------------------------------+
| :ref:`PoolColorArray<class_PoolColorArray>` | :ref:`PoolColorArray<class_PoolColorArray_method_PoolColorArray>` **(** :ref:`Array<class_Array>` from **)**                |
+---------------------------------------------+-----------------------------------------------------------------------------------------------------------------------------+
| void                                        | :ref:`append<class_PoolColorArray_method_append>` **(** :ref:`Color<class_Color>` color **)**                               |
+---------------------------------------------+-----------------------------------------------------------------------------------------------------------------------------+
| void                                        | :ref:`append_array<class_PoolColorArray_method_append_array>` **(** :ref:`PoolColorArray<class_PoolColorArray>` array **)** |
+---------------------------------------------+-----------------------------------------------------------------------------------------------------------------------------+
| :ref:`bool<class_bool>`                     | :ref:`empty<class_PoolColorArray_method_empty>` **(** **)**                                                                 |
+---------------------------------------------+-----------------------------------------------------------------------------------------------------------------------------+
| :ref:`int<class_int>`                       | :ref:`insert<class_PoolColorArray_method_insert>` **(** :ref:`int<class_int>` idx, :ref:`Color<class_Color>` color **)**    |
+---------------------------------------------+-----------------------------------------------------------------------------------------------------------------------------+
| void                                        | :ref:`invert<class_PoolColorArray_method_invert>` **(** **)**                                                               |
+---------------------------------------------+-----------------------------------------------------------------------------------------------------------------------------+
| void                                        | :ref:`push_back<class_PoolColorArray_method_push_back>` **(** :ref:`Color<class_Color>` color **)**                         |
+---------------------------------------------+-----------------------------------------------------------------------------------------------------------------------------+
| void                                        | :ref:`remove<class_PoolColorArray_method_remove>` **(** :ref:`int<class_int>` idx **)**                                     |
+---------------------------------------------+-----------------------------------------------------------------------------------------------------------------------------+
| void                                        | :ref:`resize<class_PoolColorArray_method_resize>` **(** :ref:`int<class_int>` idx **)**                                     |
+---------------------------------------------+-----------------------------------------------------------------------------------------------------------------------------+
| void                                        | :ref:`set<class_PoolColorArray_method_set>` **(** :ref:`int<class_int>` idx, :ref:`Color<class_Color>` color **)**          |
+---------------------------------------------+-----------------------------------------------------------------------------------------------------------------------------+
| :ref:`int<class_int>`                       | :ref:`size<class_PoolColorArray_method_size>` **(** **)**                                                                   |
+---------------------------------------------+-----------------------------------------------------------------------------------------------------------------------------+

方法说明
--------

.. _class_PoolColorArray_method_PoolColorArray:

- :ref:`PoolColorArray<class_PoolColorArray>` **PoolColorArray** **(** :ref:`Array<class_Array>` from **)**

构建新的\ ``PoolColorArray``\ 。你可以选择传入一个通用的\ :ref:`Array<class_Array>`\ ，它将被转换。

----

.. _class_PoolColorArray_method_append:

- void **append** **(** :ref:`Color<class_Color>` color **)**

向数组末尾追加一个元素（\ :ref:`push_back<class_PoolColorArray_method_push_back>` 的别名）。

----

.. _class_PoolColorArray_method_append_array:

- void **append_array** **(** :ref:`PoolColorArray<class_PoolColorArray>` array **)**

在这个数组的最后添加一个\ ``PoolColorArray``\ 。

----

.. _class_PoolColorArray_method_empty:

- :ref:`bool<class_bool>` **empty** **(** **)**

该数组为空时，返回 ``true``\ 。

----

.. _class_PoolColorArray_method_insert:

- :ref:`int<class_int>` **insert** **(** :ref:`int<class_int>` idx, :ref:`Color<class_Color>` color **)**

在数组中给定的位置插入一个新元素。这个位置必须是有效的，或者是在数组的末端（\ ``idx == size()``\ ）。

----

.. _class_PoolColorArray_method_invert:

- void **invert** **(** **)**

将数组中的元素逆序排列。

----

.. _class_PoolColorArray_method_push_back:

- void **push_back** **(** :ref:`Color<class_Color>` color **)**

将一个值添加到数组中。

----

.. _class_PoolColorArray_method_remove:

- void **remove** **(** :ref:`int<class_int>` idx **)**

从数组中删除位于索引的元素。

----

.. _class_PoolColorArray_method_resize:

- void **resize** **(** :ref:`int<class_int>` idx **)**

设置数组的大小。如果数组被增大，则保留数组末端的元素。如果数组被缩小，则将数组截断到新的大小。

----

.. _class_PoolColorArray_method_set:

- void **set** **(** :ref:`int<class_int>` idx, :ref:`Color<class_Color>` color **)**

更改给定索引处的\ :ref:`Color<class_Color>`\ 。

----

.. _class_PoolColorArray_method_size:

- :ref:`int<class_int>` **size** **(** **)**

返回数组的大小。

.. |virtual| replace:: :abbr:`virtual (This method should typically be overridden by the user to have any effect.)`
.. |const| replace:: :abbr:`const (This method has no side effects. It doesn't modify any of the instance's member variables.)`
.. |vararg| replace:: :abbr:`vararg (This method accepts any number of arguments after the ones described here.)`
