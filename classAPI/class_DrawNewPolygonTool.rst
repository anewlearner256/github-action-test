.. _class_DrawNewPolygonTool:

DrawNewPolygonTool 
===================

**Inherits:** :ref:`BaseTool<class_BaseTool>` **<** :ref:`Node<class_Node>` **<** :ref:`Object<class_Object>`

描述
----

绘制多边形工具

示例
----

属性
----

+-------------------------------------------------------------+-------------------------------------------------------------------------+
| :ref:`Boolean<class_Boolean>`                               | :ref:`IsInteractive<class_DrawNewPolygonTool_property_IsInteractive>`   |
+-------------------------------------------------------------+-------------------------------------------------------------------------+
| :ref:`PolygonGeometryElement<class_PolygonGeometryElement>` | :ref:`Element<class_DrawNewPolygonTool_property_Element>`               |
+-------------------------------------------------------------+-------------------------------------------------------------------------+
| :ref:`Geometry<class_Geometry>`                             | :ref:`OffsetGeometry<class_DrawNewPolygonTool_property_OffsetGeometry>` |
+-------------------------------------------------------------+-------------------------------------------------------------------------+

方法
----

+-------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :ref:`Void<class_Void>`       | :ref:`_Ready<class_DrawNewPolygonTool_method__Ready>` **(** **)**                                                                                                |
+-------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :ref:`Void<class_Void>`       | :ref:`OnMouseDown<class_DrawNewPolygonTool_method_OnMouseDown>` **(** :ref:`Vector2<class_Vector2>` screenpos, :ref:`Int32<class_Int32>` btn **)**               |
+-------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :ref:`Boolean<class_Boolean>` | :ref:`OnMouseDoubleClick<class_DrawNewPolygonTool_method_OnMouseDoubleClick>` **(** :ref:`Vector2<class_Vector2>` screenpos, :ref:`Int32<class_Int32>` btn **)** |
+-------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :ref:`Void<class_Void>`       | :ref:`OnMouseMove<class_DrawNewPolygonTool_method_OnMouseMove>` **(** :ref:`Vector2<class_Vector2>` screenpos, :ref:`Int32<class_Int32>` btn **)**               |
+-------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :ref:`Void<class_Void>`       | :ref:`_Process<class_DrawNewPolygonTool_method__Process>` **(** :ref:`Single<class_Single>` delta **)**                                                          |
+-------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :ref:`List`1<class_List`1>`   | :ref:`GetPolygon<class_DrawNewPolygonTool_method_GetPolygon>` **(** **)**                                                                                        |
+-------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------+

属性说明
-------

.. _class_DrawNewPolygonTool_property_IsInteractive:

- :ref:`Boolean<class_Boolean>` **IsInteractive**

+----------+---+
| *Setter* |   |
+----------+---+
| *Getter* |   |
+----------+---+

是否开启交互

----

.. _class_DrawNewPolygonTool_property_Element:

- :ref:`PolygonGeometryElement<class_PolygonGeometryElement>` **Element**

+----------+---+
| *Setter* |   |
+----------+---+
| *Getter* |   |
+----------+---+

面要素

----

.. _class_DrawNewPolygonTool_property_OffsetGeometry:

- :ref:`Geometry<class_Geometry>` **OffsetGeometry**

+----------+---+
| *Setter* |   |
+----------+---+
| *Getter* |   |
+----------+---+

绘制点集合

----


方法说明
-------

.. _class_DrawNewPolygonTool_method__Ready:

- :ref:`Void<class_Void>` **_Ready** **(** **)**

对象被添加到场景中时执行一些初始化操作

----

.. _class_DrawNewPolygonTool_method_OnMouseDown:

- :ref:`Void<class_Void>` **OnMouseDown** **(** :ref:`Vector2<class_Vector2>` screenpos, :ref:`Int32<class_Int32>` btn **)**

处理鼠标按键事件（绘制多边形）

----

.. _class_DrawNewPolygonTool_method_OnMouseDoubleClick:

- :ref:`Boolean<class_Boolean>` **OnMouseDoubleClick** **(** :ref:`Vector2<class_Vector2>` screenpos, :ref:`Int32<class_Int32>` btn **)**

处理鼠标双击事件

----

.. _class_DrawNewPolygonTool_method_OnMouseMove:

- :ref:`Void<class_Void>` **OnMouseMove** **(** :ref:`Vector2<class_Vector2>` screenpos, :ref:`Int32<class_Int32>` btn **)**

处理鼠标移动事件。（绘制多边形）

----

.. _class_DrawNewPolygonTool_method__Process:

- :ref:`Void<class_Void>` **_Process** **(** :ref:`Single<class_Single>` delta **)**

处理逻辑

----

.. _class_DrawNewPolygonTool_method_GetPolygon:

- :ref:`List`1<class_List`1>` **GetPolygon** **(** **)**

获取坐标

----

