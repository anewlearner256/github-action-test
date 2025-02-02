:github_url: hide

.. Generated automatically by doc/tools/make_rst.py in GaaeExplorer's source tree.
.. DO NOT EDIT THIS FILE, but the Engine.xml source instead.
.. The source is found in doc/classes or modules/<name>/doc_classes.

.. _class_Engine:

Engine
======

**Inherits:** :ref:`Object<class_Object>`

进入引擎属性。

描述
----

``Engine``\ 单例使您可以查询和修改项目的运行时参数，例如每秒帧数，时间范围等。

属性
----

+---------------------------+---------------------------------------------------------------------------+----------+
| :ref:`bool<class_bool>`   | :ref:`editor_hint<class_Engine_property_editor_hint>`                     | ``true`` |
+---------------------------+---------------------------------------------------------------------------+----------+
| :ref:`int<class_int>`     | :ref:`iterations_per_second<class_Engine_property_iterations_per_second>` | ``60``   |
+---------------------------+---------------------------------------------------------------------------+----------+
| :ref:`float<class_float>` | :ref:`physics_jitter_fix<class_Engine_property_physics_jitter_fix>`       | ``0.5``  |
+---------------------------+---------------------------------------------------------------------------+----------+
| :ref:`bool<class_bool>`   | :ref:`print_error_messages<class_Engine_property_print_error_messages>`   | ``true`` |
+---------------------------+---------------------------------------------------------------------------+----------+
| :ref:`int<class_int>`     | :ref:`target_fps<class_Engine_property_target_fps>`                       | ``0``    |
+---------------------------+---------------------------------------------------------------------------+----------+
| :ref:`float<class_float>` | :ref:`time_scale<class_Engine_property_time_scale>`                       | ``1.0``  |
+---------------------------+---------------------------------------------------------------------------+----------+

方法
----

+-------------------------------------+-----------------------------------------------------------------------------------------------------------------------+
| :ref:`Dictionary<class_Dictionary>` | :ref:`get_author_info<class_Engine_method_get_author_info>` **(** **)** |const|                                       |
+-------------------------------------+-----------------------------------------------------------------------------------------------------------------------+
| :ref:`Array<class_Array>`           | :ref:`get_copyright_info<class_Engine_method_get_copyright_info>` **(** **)** |const|                                 |
+-------------------------------------+-----------------------------------------------------------------------------------------------------------------------+
| :ref:`Dictionary<class_Dictionary>` | :ref:`get_donor_info<class_Engine_method_get_donor_info>` **(** **)** |const|                                         |
+-------------------------------------+-----------------------------------------------------------------------------------------------------------------------+
| :ref:`int<class_int>`               | :ref:`get_frames_drawn<class_Engine_method_get_frames_drawn>` **(** **)**                                             |
+-------------------------------------+-----------------------------------------------------------------------------------------------------------------------+
| :ref:`float<class_float>`           | :ref:`get_frames_per_second<class_Engine_method_get_frames_per_second>` **(** **)** |const|                           |
+-------------------------------------+-----------------------------------------------------------------------------------------------------------------------+
| :ref:`int<class_int>`               | :ref:`get_idle_frames<class_Engine_method_get_idle_frames>` **(** **)** |const|                                       |
+-------------------------------------+-----------------------------------------------------------------------------------------------------------------------+
| :ref:`Dictionary<class_Dictionary>` | :ref:`get_license_info<class_Engine_method_get_license_info>` **(** **)** |const|                                     |
+-------------------------------------+-----------------------------------------------------------------------------------------------------------------------+
| :ref:`String<class_String>`         | :ref:`get_license_text<class_Engine_method_get_license_text>` **(** **)** |const|                                     |
+-------------------------------------+-----------------------------------------------------------------------------------------------------------------------+
| :ref:`MainLoop<class_MainLoop>`     | :ref:`get_main_loop<class_Engine_method_get_main_loop>` **(** **)** |const|                                           |
+-------------------------------------+-----------------------------------------------------------------------------------------------------------------------+
| :ref:`int<class_int>`               | :ref:`get_physics_frames<class_Engine_method_get_physics_frames>` **(** **)** |const|                                 |
+-------------------------------------+-----------------------------------------------------------------------------------------------------------------------+
| :ref:`float<class_float>`           | :ref:`get_physics_interpolation_fraction<class_Engine_method_get_physics_interpolation_fraction>` **(** **)** |const| |
+-------------------------------------+-----------------------------------------------------------------------------------------------------------------------+
| :ref:`Object<class_Object>`         | :ref:`get_singleton<class_Engine_method_get_singleton>` **(** :ref:`String<class_String>` name **)** |const|          |
+-------------------------------------+-----------------------------------------------------------------------------------------------------------------------+
| :ref:`Dictionary<class_Dictionary>` | :ref:`get_version_info<class_Engine_method_get_version_info>` **(** **)** |const|                                     |
+-------------------------------------+-----------------------------------------------------------------------------------------------------------------------+
| :ref:`bool<class_bool>`             | :ref:`has_singleton<class_Engine_method_has_singleton>` **(** :ref:`String<class_String>` name **)** |const|          |
+-------------------------------------+-----------------------------------------------------------------------------------------------------------------------+
| :ref:`bool<class_bool>`             | :ref:`is_in_physics_frame<class_Engine_method_is_in_physics_frame>` **(** **)** |const|                               |
+-------------------------------------+-----------------------------------------------------------------------------------------------------------------------+

属性说明
--------

.. _class_Engine_property_editor_hint:

- :ref:`bool<class_bool>` **editor_hint**

+-----------+------------------------+
| *Default* | ``true``               |
+-----------+------------------------+
| *Setter*  | set_editor_hint(value) |
+-----------+------------------------+
| *Getter*  | is_editor_hint()       |
+-----------+------------------------+

If ``true``, the script is currently running inside the editor. This is useful for ``tool`` scripts to conditionally draw editor helpers, or prevent accidentally running "game" code that would affect the scene state while in the editor:

::

    if Engine.editor_hint:
        draw_gizmos()
    else:
        simulate_physics()

See :doc:`Running code in the editor <../tutorials/misc/running_code_in_the_editor>` in the documentation for more information.

\ **Note:** To detect whether the script is run from an editor *build* (e.g. when pressing ``F5``), use :ref:`OS.has_feature<class_OS_method_has_feature>` with the ``"editor"`` argument instead. ``OS.has_feature("editor")`` will evaluate to ``true`` both when the code is running in the editor and when running the project from the editor, but it will evaluate to ``false`` when the code is run from an exported project.

----

.. _class_Engine_property_iterations_per_second:

- :ref:`int<class_int>` **iterations_per_second**

+-----------+----------------------------------+
| *Default* | ``60``                           |
+-----------+----------------------------------+
| *Setter*  | set_iterations_per_second(value) |
+-----------+----------------------------------+
| *Getter*  | get_iterations_per_second()      |
+-----------+----------------------------------+

The number of fixed iterations per second. This controls how often physics simulation and :ref:`Node._physics_process<class_Node_method__physics_process>` methods are run. This value should generally always be set to ``60`` or above, as GaaeExplorer doesn't interpolate the physics step. As a result, values lower than ``60`` will look stuttery. This value can be increased to make input more reactive or work around collision tunneling issues, but keep in mind doing so will increase CPU usage. See also :ref:`target_fps<class_Engine_property_target_fps>` and :ref:`ProjectSettings.physics/common/physics_fps<class_ProjectSettings_property_physics/common/physics_fps>`.

\ **Note:** Only 8 physics ticks may be simulated per rendered frame at most. If more than 8 physics ticks have to be simulated per rendered frame to keep up with rendering, the game will appear to slow down (even if ``delta`` is used consistently in physics calculations). Therefore, it is recommended not to increase :ref:`iterations_per_second<class_Engine_property_iterations_per_second>` above 240. Otherwise, the game will slow down when the rendering framerate goes below 30 FPS.

----

.. _class_Engine_property_physics_jitter_fix:

- :ref:`float<class_float>` **physics_jitter_fix**

+-----------+-------------------------------+
| *Default* | ``0.5``                       |
+-----------+-------------------------------+
| *Setter*  | set_physics_jitter_fix(value) |
+-----------+-------------------------------+
| *Getter*  | get_physics_jitter_fix()      |
+-----------+-------------------------------+

控制物理时钟与实时同步程度。如果是0或更少，时钟是同步的。这样的值建议用于网络游戏，因为时钟的同步性很重要。较高的值会导致游戏中的时钟和真实时钟之间的偏差较大，但可以平滑帧速率的抖动。默认值0.5对大多数人来说应该是良好的；超过2的值可能导致游戏对掉帧的反应有明显的延迟，因此不推荐使用。

\ **注意：**\ 为了获得最佳效果，当使用自定义物理插值这种解决方案时，应通过将\ :ref:`physics_jitter_fix<class_Engine_property_physics_jitter_fix>`\ 设置为\ ``0``\ 来禁用物理抖动修复。

----

.. _class_Engine_property_print_error_messages:

- :ref:`bool<class_bool>` **print_error_messages**

+-----------+---------------------------------+
| *Default* | ``true``                        |
+-----------+---------------------------------+
| *Setter*  | set_print_error_messages(value) |
+-----------+---------------------------------+
| *Getter*  | is_printing_error_messages()    |
+-----------+---------------------------------+

如果\ ``false``\ ，停止打印错误和警告信息到控制台和编辑器输出日志。这可以用来在单元测试套件运行期间隐藏错误和警告信息。这个属性等同于\ :ref:`ProjectSettings.application/run/disable_stderr<class_ProjectSettings_property_application/run/disable_stderr>`\ 项目设置。

\ **警告:** 如果你在项目的任意位置将其设置为\ ``false``\ ，重要的错误信息可能会被隐藏，即使它们是由其他脚本触发。如果在\ ``@tool``\ 脚本中把这个设置为\ ``false``\ ，这也会影响到编辑器本身。在确保错误信息被启用之前，\ *不*\ 报告错误（默认情况下）。

\ **注意:**\ 当从编辑器运行一个项目时，这个属性不影响编辑器的错误选项卡。

----

.. _class_Engine_property_target_fps:

- :ref:`int<class_int>` **target_fps**

+-----------+-----------------------+
| *Default* | ``0``                 |
+-----------+-----------------------+
| *Setter*  | set_target_fps(value) |
+-----------+-----------------------+
| *Getter*  | get_target_fps()      |
+-----------+-----------------------+

所需的每秒帧数。如果硬件无法跟上，则可能不遵守此设置。值为0表示没有限制。

----

.. _class_Engine_property_time_scale:

- :ref:`float<class_float>` **time_scale**

+-----------+-----------------------+
| *Default* | ``1.0``               |
+-----------+-----------------------+
| *Setter*  | set_time_scale(value) |
+-----------+-----------------------+
| *Getter*  | get_time_scale()      |
+-----------+-----------------------+

控制游戏中的时钟与现实生活中的时钟的快慢。默认值为1.0。值为2.0意味着游戏的移动速度是现实生活的两倍，而值为0.5意味着游戏的移动速度是常规速度的一半。

方法说明
--------

.. _class_Engine_method_get_author_info:

- :ref:`Dictionary<class_Dictionary>` **get_author_info** **(** **)** |const|

返回一个字典中的引擎作者信息。

\ ``lead_developers`` - 字符串的数组，主要开发者的名字

\ ``founders`` - 创始人姓名的字符串数组

\ ``project_managers`` - 项目经理姓名的字符串数组

\ ``developers`` - 开发者名称的字符串数组

----

.. _class_Engine_method_get_copyright_info:

- :ref:`Array<class_Array>` **get_copyright_info** **(** **)** |const|

返回一个版权信息字典数组。

\ ``name`` - 字符串，组件名称。

\ ``partic`` - 描述组件子部分的字典数组 {``files``, ``copyright``, ``license``}

----

.. _class_Engine_method_get_donor_info:

- :ref:`Dictionary<class_Dictionary>` **get_donor_info** **(** **)** |const|

返回捐赠者姓名数组的字典。

{``platinum_sponsors``, ``gold_sponsors``, ``silver_sponsors``, ``bronze_sponsors``, ``mini_sponsors``, ``gold_donors``, ``silver_donors``, ``bronze_donors``}

----

.. _class_Engine_method_get_frames_drawn:

- :ref:`int<class_int>` **get_frames_drawn** **(** **)**

返回绘制的总帧数。在精简平台上，或者如果通过命令行使用 ``--disable-render-loop`` 禁用渲染循环，\ :ref:`get_frames_drawn<class_Engine_method_get_frames_drawn>` 总是返回 ``0``\ 。参阅\ :ref:`get_idle_frames<class_Engine_method_get_idle_frames>`\ 。

----

.. _class_Engine_method_get_frames_per_second:

- :ref:`float<class_float>` **get_frames_per_second** **(** **)** |const|

返回运行游戏的每秒帧数。

----

.. _class_Engine_method_get_idle_frames:

- :ref:`int<class_int>` **get_idle_frames** **(** **)** |const|

返回自引擎初始化以来的总帧数，在每个\ **空闲帧**\ 都会进行，无论渲染循环是否被启用。参阅\ :ref:`get_frames_drawn<class_Engine_method_get_frames_drawn>`\ 和\ :ref:`get_physics_frames<class_Engine_method_get_physics_frames>`\ 。

\ :ref:`get_idle_frames<class_Engine_method_get_idle_frames>`\ 可以用来减少运行高消耗逻辑的次数，而不需要依靠\ :ref:`Timer<class_Timer>`\ 。

::

    func _process(_delta):
        if Engine.get_idle_frames() % 2 == 0:
            pass  # Run expensive logic only once every 2 idle (render) frames here.

----

.. _class_Engine_method_get_license_info:

- :ref:`Dictionary<class_Dictionary>` **get_license_info** **(** **)** |const|

返回GaaeExplorer使用的Dictionary 字典列表，其中包括第三方组件。

----

.. _class_Engine_method_get_license_text:

- :ref:`String<class_String>` **get_license_text** **(** **)** |const|

返回GaaeExplorer许可证文本。

----

.. _class_Engine_method_get_main_loop:

- :ref:`MainLoop<class_MainLoop>` **get_main_loop** **(** **)** |const|

返回主循环对象（请参阅\ :ref:`MainLoop<class_MainLoop>`\ 和\ :ref:`SceneTree<class_SceneTree>`\ ）。

----

.. _class_Engine_method_get_physics_frames:

- :ref:`int<class_int>` **get_physics_frames** **(** **)** |const|

返回自引擎初始化以来通过的总帧数，该帧数在每个\ **物理帧**\ 上进行。参阅\ :ref:`get_idle_frames<class_Engine_method_get_idle_frames>`\ 。

\ :ref:`get_physics_frames<class_Engine_method_get_physics_frames>`\ 可以用来减少运行高消耗逻辑的次数，而不需要依靠\ :ref:`Timer<class_Timer>`\ 。

::

    func _physics_process(_delta):
        if Engine.get_physics_frames() % 2 == 0:
            pass  # Run expensive logic only once every 2 physics frames here.

----

.. _class_Engine_method_get_physics_interpolation_fraction:

- :ref:`float<class_float>` **get_physics_interpolation_fraction** **(** **)** |const|

返回渲染框架时当前物理滴标记中的分数。这可用于实现固定的时间步插值。

----

.. _class_Engine_method_get_singleton:

- :ref:`Object<class_Object>` **get_singleton** **(** :ref:`String<class_String>` name **)** |const|

返回具有给定\ ``name``\ 的全局单例。通常用于插件，例如Android上的\ ``GaaeExplorerPayment``\ 。

----

.. _class_Engine_method_get_version_info:

- :ref:`Dictionary<class_Dictionary>` **get_version_info** **(** **)** |const|

在字典中返回当前的引擎版本信息。

\ ``major`` - 将主要版本号作为一个int来保存。

\ ``minor`` - 将小版本号作为一个int保存。

\ ``patch`` - 将补丁版本号作为一个int来保存。

\ ``hex`` - 保存以十六进制int编码的完整版本号，每个数字一个字节(2位)(见下例)

\ ``status`` - 以字符串形式保存状态 (例如 "beta", "rc1", "rc2", ... "stable")

\ ``build`` - 将build名称(例如 "custom_build")作为一个字符串保存。

\ ``hash`` - 以字符串形式保存完整的 Git 提交哈希值。

\ ``year`` - 将版本发布的年份作为一个int值来保存。

\ ``string`` - ``major`` + ``minor`` + ``patch`` + ``status`` + ``build``\ 在一个字符串中。

\ ``十六进制``\ 值的编码如下，从左到右：一个字节代表主要版本，一个字节代表次要版本，一个字节代表补丁版本。例如，"3.1.12 "就是\ ``0x03010C``\ 。\ **注意：**\ 内部还是一个int，打印出来会给你它的十进制表示法，意义不是特别大。使用十六进制的字数，方便从代码中进行版本比较。

::

    if Engine.get_version_info().hex >= 0x030200:
        # Do things specific to version 3.2 or later
    else:
        # Do things specific to versions before 3.2

----

.. _class_Engine_method_has_singleton:

- :ref:`bool<class_bool>` **has_singleton** **(** :ref:`String<class_String>` name **)** |const|

如果全局范围内存在具有给定\ ``name``\ 的单例，则返回\ ``true``\ 。

----

.. _class_Engine_method_is_in_physics_frame:

- :ref:`bool<class_bool>` **is_in_physics_frame** **(** **)** |const|

如果游戏在游戏循环的固定过程和物理阶段内，返回 ``true``\ 。

.. |virtual| replace:: :abbr:`virtual (This method should typically be overridden by the user to have any effect.)`
.. |const| replace:: :abbr:`const (This method has no side effects. It doesn't modify any of the instance's member variables.)`
.. |vararg| replace:: :abbr:`vararg (This method accepts any number of arguments after the ones described here.)`
