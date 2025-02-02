:github_url: hide

.. Generated automatically by doc/tools/make_rst.py in GaaeExplorer's source tree.
.. DO NOT EDIT THIS FILE, but the EditorSettings.xml source instead.
.. The source is found in doc/classes or modules/<name>/doc_classes.

.. _class_EditorSettings:

EditorSettings
==============

**Inherits:** :ref:`Resource<class_Resource>` **<** :ref:`Reference<class_Reference>` **<** :ref:`Object<class_Object>`

保存与项目无关的编辑器设置的对象。

描述
----

保存与项目无关的编辑器设置的对象。这些设置通常在 **编辑器 > 编辑器设置** 菜单中可见。

属性名使用斜线分隔符来区分部分。设置值可以是任何 :ref:`Variant<class_Variant>` 类型。建议使用\ ``snake_case``\ 进行编辑器设置，以便与GaaeExplorer编辑器本身保持一致。

访问设置可以使用以下方法，例如。

::

    # `settings.set("some/property", value)` also works as this class overrides `_set()` internally.
    settings.set_setting("some/property",value)
    
    # `settings.get("some/property", value)` also works as this class overrides `_get()` internally.
    settings.get_setting("some/property")
    
    var list_of_settings = settings.get_property_list()

\ **注意:**\ 这个类不应该直接实例化，而是使用\ :ref:`EditorInterface.get_editor_settings<class_EditorInterface_method_get_editor_settings>`\ 访问单子。相反，使用\ :ref:`EditorInterface.get_editor_settings<class_EditorInterface_method_get_editor_settings>`\ 访问单例。

方法
----

+-----------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| void                                          | :ref:`add_property_info<class_EditorSettings_method_add_property_info>` **(** :ref:`Dictionary<class_Dictionary>` info **)**                                                                                       |
+-----------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| void                                          | :ref:`erase<class_EditorSettings_method_erase>` **(** :ref:`String<class_String>` property **)**                                                                                                                   |
+-----------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :ref:`PoolStringArray<class_PoolStringArray>` | :ref:`get_favorites<class_EditorSettings_method_get_favorites>` **(** **)** |const|                                                                                                                                |
+-----------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :ref:`Variant<class_Variant>`                 | :ref:`get_project_metadata<class_EditorSettings_method_get_project_metadata>` **(** :ref:`String<class_String>` section, :ref:`String<class_String>` key, :ref:`Variant<class_Variant>` default=null **)** |const| |
+-----------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :ref:`String<class_String>`                   | :ref:`get_project_settings_dir<class_EditorSettings_method_get_project_settings_dir>` **(** **)** |const|                                                                                                          |
+-----------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :ref:`PoolStringArray<class_PoolStringArray>` | :ref:`get_recent_dirs<class_EditorSettings_method_get_recent_dirs>` **(** **)** |const|                                                                                                                            |
+-----------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :ref:`Variant<class_Variant>`                 | :ref:`get_setting<class_EditorSettings_method_get_setting>` **(** :ref:`String<class_String>` name **)** |const|                                                                                                   |
+-----------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :ref:`String<class_String>`                   | :ref:`get_settings_dir<class_EditorSettings_method_get_settings_dir>` **(** **)** |const|                                                                                                                          |
+-----------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :ref:`bool<class_bool>`                       | :ref:`has_setting<class_EditorSettings_method_has_setting>` **(** :ref:`String<class_String>` name **)** |const|                                                                                                   |
+-----------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :ref:`bool<class_bool>`                       | :ref:`property_can_revert<class_EditorSettings_method_property_can_revert>` **(** :ref:`String<class_String>` name **)**                                                                                           |
+-----------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :ref:`Variant<class_Variant>`                 | :ref:`property_get_revert<class_EditorSettings_method_property_get_revert>` **(** :ref:`String<class_String>` name **)**                                                                                           |
+-----------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| void                                          | :ref:`set_favorites<class_EditorSettings_method_set_favorites>` **(** :ref:`PoolStringArray<class_PoolStringArray>` dirs **)**                                                                                     |
+-----------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| void                                          | :ref:`set_initial_value<class_EditorSettings_method_set_initial_value>` **(** :ref:`String<class_String>` name, :ref:`Variant<class_Variant>` value, :ref:`bool<class_bool>` update_current **)**                  |
+-----------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| void                                          | :ref:`set_project_metadata<class_EditorSettings_method_set_project_metadata>` **(** :ref:`String<class_String>` section, :ref:`String<class_String>` key, :ref:`Variant<class_Variant>` data **)**                 |
+-----------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| void                                          | :ref:`set_recent_dirs<class_EditorSettings_method_set_recent_dirs>` **(** :ref:`PoolStringArray<class_PoolStringArray>` dirs **)**                                                                                 |
+-----------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| void                                          | :ref:`set_setting<class_EditorSettings_method_set_setting>` **(** :ref:`String<class_String>` name, :ref:`Variant<class_Variant>` value **)**                                                                      |
+-----------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

信号
----

.. _class_EditorSettings_signal_settings_changed:

- **settings_changed** **(** **)**

在编辑器设置改变后触发。

常量
----

.. _class_EditorSettings_constant_NOTIFICATION_EDITOR_SETTINGS_CHANGED:

- **NOTIFICATION_EDITOR_SETTINGS_CHANGED** = **10000** --- 在编辑器设置改变后触发。它被各种编辑器插件用于在主题变化时更新其视觉效果或在配置变化时更新逻辑。

方法说明
--------

.. _class_EditorSettings_method_add_property_info:

- void **add_property_info** **(** :ref:`Dictionary<class_Dictionary>` info **)**

将自定义属性信息添加到属性。该词典必须包含：

-``名称``\ ：\ :ref:`String<class_String>`\ （属性名称）

-``类型``\ ：\ :ref:`int<class_int>`\ （请参阅\ :ref:`Variant.Type<enum_@GlobalScope_Variant.Type>`\ ）

-（可选）\ ``提示``\ ：\ :ref:`int<class_int>`\ （请参阅\ :ref:`PropertyHint<enum_@GlobalScope_PropertyHint>`\ ）和\ ``hint_string``\ ：\ :ref:`String<class_String>`\ 

\ **示例：**\ 

::

    editor_settings.set("category/property_name", 0)
    
    var property_info = {
        "name": "category/property_name",
        "type": TYPE_INT,
        "hint": PROPERTY_HINT_ENUM,
        "hint_string": "one,two,three"
    }
    
    editor_settings.add_property_info(property_info)

----

.. _class_EditorSettings_method_erase:

- void **erase** **(** :ref:`String<class_String>` property **)**

删除名称为指定\ ``property``\ 的设置。

----

.. _class_EditorSettings_method_get_favorites:

- :ref:`PoolStringArray<class_PoolStringArray>` **get_favorites** **(** **)** |const|

返回本项目最收藏的文件和目录列表。

----

.. _class_EditorSettings_method_get_project_metadata:

- :ref:`Variant<class_Variant>` **get_project_metadata** **(** :ref:`String<class_String>` section, :ref:`String<class_String>` key, :ref:`Variant<class_Variant>` default=null **)** |const|

返回指定的\ ``section``\ 和\ ``key``\ 的特定项目元数据。如果元数据不存在，将返回\ ``default``\ 。另请参阅 :ref:`set_project_metadata<class_EditorSettings_method_set_project_metadata>`\ 。

----

.. _class_EditorSettings_method_get_project_settings_dir:

- :ref:`String<class_String>` **get_project_settings_dir** **(** **)** |const|

返回项目特定设置的路径。项目在设置路径中都有一个唯一的子目录，保存项目的特定设置。

----

.. _class_EditorSettings_method_get_recent_dirs:

- :ref:`PoolStringArray<class_PoolStringArray>` **get_recent_dirs** **(** **)** |const|

返回此项目文件对话框中最近访问的文件夹列表。

----

.. _class_EditorSettings_method_get_setting:

- :ref:`Variant<class_Variant>` **get_setting** **(** :ref:`String<class_String>` name **)** |const|

返回 ``name`` 指定的设置的值。这相当于在EditorSettings实例上使用\ :ref:`Object.get<class_Object_method_get>`\ 。

----

.. _class_EditorSettings_method_get_settings_dir:

- :ref:`String<class_String>` **get_settings_dir** **(** **)** |const|

获取引擎的全局设置路径。在此路径内，您可以找到一些标准路径，例如：

\ ``settings / tmp``-用于文件的临时存储

\ ``settings/templates``-导出模板所在的位置

----

.. _class_EditorSettings_method_has_setting:

- :ref:`bool<class_bool>` **has_setting** **(** :ref:`String<class_String>` name **)** |const|

如果由名称 ``name`` 指定的设置存在，则返回 ``true``\ ，否则返回 ``false``\ 。

----

.. _class_EditorSettings_method_property_can_revert:

- :ref:`bool<class_bool>` **property_can_revert** **(** :ref:`String<class_String>` name **)**

如果\ ``name``\ 指定的设置可以将其值还原为默认值，则返回\ ``true``\ ，否则返回\ ``false``\ 。当此方法返回\ ``true``\ 时，编辑器设置中的设置旁边会显示一个还原按钮。

----

.. _class_EditorSettings_method_property_get_revert:

- :ref:`Variant<class_Variant>` **property_get_revert** **(** :ref:`String<class_String>` name **)**

返回 ``name`` 指定的设置的默认值。当点击编辑器设置中的 "还原 "按钮时，该值将被应用。

----

.. _class_EditorSettings_method_set_favorites:

- void **set_favorites** **(** :ref:`PoolStringArray<class_PoolStringArray>` dirs **)**

设置此项目为收藏的文件和目录列表。

----

.. _class_EditorSettings_method_set_initial_value:

- void **set_initial_value** **(** :ref:`String<class_String>` name, :ref:`Variant<class_Variant>` value, :ref:`bool<class_bool>` update_current **)**

将 ``name`` 指定的设置的初始值设置为 ``value``\ 。这用于为编辑器设置中的“还原”按钮提供一个值。如果 ``update_current`` 为真，则设置的当前值也会被设置为 ``value``\ 。

----

.. _class_EditorSettings_method_set_project_metadata:

- void **set_project_metadata** **(** :ref:`String<class_String>` section, :ref:`String<class_String>` key, :ref:`Variant<class_Variant>` data **)**

设置项目特定的元数据，并指定 ``section``\ 、\ ``key`` 和 ``data``\ 。这个元数据被保存在项目文件夹之外，因此不会被检查到版本控制中。参阅 :ref:`get_project_metadata<class_EditorSettings_method_get_project_metadata>`\ 。

----

.. _class_EditorSettings_method_set_recent_dirs:

- void **set_recent_dirs** **(** :ref:`PoolStringArray<class_PoolStringArray>` dirs **)**

在文件对话框中设置本项目最近访问过的文件夹列表。

----

.. _class_EditorSettings_method_set_setting:

- void **set_setting** **(** :ref:`String<class_String>` name, :ref:`Variant<class_Variant>` value **)**

设置 ``name`` 指定的设置的 ``value``\ 。这相当于在EditorSettings实例上使用\ :ref:`Object.set<class_Object_method_set>`\ 。

.. |virtual| replace:: :abbr:`virtual (This method should typically be overridden by the user to have any effect.)`
.. |const| replace:: :abbr:`const (This method has no side effects. It doesn't modify any of the instance's member variables.)`
.. |vararg| replace:: :abbr:`vararg (This method accepts any number of arguments after the ones described here.)`
