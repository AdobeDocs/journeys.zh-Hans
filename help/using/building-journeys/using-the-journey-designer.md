---
product: adobe campaign
solution: Journey Orchestration
title: 使用旅程设计器
description: 进一步了解旅程设计器
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '1354'
ht-degree: 5%

---


# 使用旅程设计器 {#concept_m1g_5qt_52b}

旅程“主页”菜单允许您视图 **旅程的列表**。 创建新旅程或单击现有旅程以打开旅 **程设计者的界面**。 设计人员由以下区域组成：调色板、画布和活动配置窗格。

## 旅程列表 {#journey_list}

The **journey list** allows you to view all your journeys at once, see their status and perform basic actions. 您可以重复、停止或删除您的旅程。某些操作可能不可用，具体取决于旅程。例如，您无法删除或重新启动已关闭的旅程。您可以从中创建新版本、重复或停止它。 您还可以使用搜索栏搜索旅程。

单击列表左上角的过滤器图标即可访问&#x200B;**[!UICONTROL Filters]**。过滤器菜单允许您根据不同的条件（状态、您创建的、在过去30天内修改的、仅限最新版本等）筛选显示的旅程。 您还可以选择仅显示使用特定事件、字段组或操作的旅程。 可以配置列表上显示的列。 所有过滤器和列均按用户保存。

![](../assets/journey74.png)

您的所有版本旅程都以版本号显示在列表中。 请参阅[此页](../building-journeys/journey-versions.md)。

![](../assets/journey37.png)

>[!NOTE]
>
>要在其他浏览器选项卡中打开旅程画布，请 **按住Control****或Command键** 并单击旅程。

## 调色板 {#palette}

调 **色板** 位于屏幕的左侧。 所有可用活动均按多个类别进行分类： **[!UICONTROL Events]**, **[!UICONTROL Orchestration]** 和 **[!UICONTROL Actions]**。 您可以通过单击不同类别的名称展开／折叠其名称。 要在旅程中使用活动，请将其从调色板拖放到画布中。 您还可以在调色板中多次单击某个活动，将其添加到画布中，然后执行下一步操作。 在发布旅程之前，必须配置从调色板添加的每个活动。 如果将活动放在画布中，但未完成其配置，则该活动将保留在画布中，但红色警告将指示该配置未完成。

>[!NOTE]
>
>请注意，设置旅程时有规则。 将丢弃不允许的配置。 例如，您不能并行放置操作、将活动链接到上一步以创建循环、用事件以外的其他方式开始旅程等。

![](../assets/journey38.png)

The **[!UICONTROL Show disabled items]** icon in the top left corner allows you to hide or display unavailable elements in the palette, for example the events that use a different namespace than the ones used in your journey. 默认情况下，不可用项目处于隐藏状态。如果选择显示它们，则它们将灰显。

使用字段 **[!UICONTROL Search]** 时，将显示每个画布活动类别的结果数。

![](../assets/palette-filter.png)

## 画布 {#canvas}

画 **布** 是旅程设计者的中心区域。 您可以在此区域中放置活动并进行配置。 单击画布中的活动进行配置。 这会打开右侧的活动配置窗格。 可使用右上方的“+”和“-”按钮进行放大和缩小。 在画布中，所有活动都允许您在其后添加下一步，但活动除 **[!UICONTROL End]** 外(请 [参阅此页](../building-journeys/end-activity.md))。

![](../assets/journey39.png)

## 活动配置窗格 {#configuration_pane}

单击 **调色板中的活动** ，将显示活动配置窗格。 填写必填字段。 单击该图 **[!UICONTROL Delete]** 标以删除活动。 单击可 **[!UICONTROL Cancel]** 取消修改或进 **[!UICONTROL Ok]** 行确认。 要删除活动，您还可以选择一个活动（或多个）并按背景键。 按转义键将关闭活动配置窗格。

在画布中，您的操作和事件活动由图标表示，该图标下方显示有事件或操作的名称。 在活动配置窗格中，可以使 **[!UICONTROL Label]** 用字段向活动名称添加后缀。 这些标签将帮助您将事件和动作的使用情境化，尤其是当您在旅程中多次使用相同的事件或动作时。 您还可以看到您在报告中添加的标 [!DNL Journey Orchestration] 签。 您还可以为条件活动定义标签。

![](../assets/journey59bis.png)

## 顶栏操作 {#top_actions}

根据旅程的状态，您可以使用右上角的按钮对旅程执行不同的操作： **[!UICONTROL Publish]**、 **[!UICONTROL Duplicate]**、 **[!UICONTROL Delete]**、 **[!UICONTROL Journey properties]**、 **[!UICONTROL Test]**。 未选择活动时，将显示这些按钮。 某些按钮将根据上下文显示。 在激活测试模式时，将显示测试模式日志按钮(请 [参阅此页](../building-journeys/testing-the-journey.md))。 当旅程处于实时、停止或关闭状态时，将显示报告按钮。

![](../assets/journey41.png)

## 在画布中使用路径 {#paths}

多个活动(**[!UICONTROL Condition]**&#x200B;活动 **[!UICONTROL Action]** )允许您定义在出现错误或超时时的回退操作。 在“活动配置”窗格中，选中复选框： **[!UICONTROL Add an alternative path in case of a timeout or an error]**. 在活动后添加另一个路径。 超时持续时间在旅程的属性中定义(请 [由管理](../building-journeys/changing-properties.md) 员用户参阅此页)。 例如，如果电子邮件发送时间过长或出错，您可以决定发送SMS。

![](../assets/journey42.png)

各种活动(事件、操作、等待)允许您在路径后添加多条路径。 为此，请将光标放在活动上并单击“+”符号。 只能同时设置事件和等待活动。 如果多个事件被并行设置，则所选路径将是第一个事件。

在听取事件时，我们建议您不要无限期地等待事件。 它不是强制性的，只是一种最佳实践。 如果您只想在某个时间内聆听一个或多个事件，您将同时放置一个或多个事件和一个等待活动。 请参阅[此章节](../building-journeys/event-activities.md#section_vxv_h25_pgb)。

要删除路径，请将光标放在路径上并单击该 **[!UICONTROL Delete arrow]** 图标。

![](../assets/journey42ter.png)

在画布中，当两个活动断开连接时，将显示警告。 将光标放在警告图标上可显示错误消息。 要解决此问题，只需移动断开连接的活动并将其连接到上一个活动。

![](../assets/canvas-disconnected.png)

## 复制和粘贴活动 {#copy-paste}

您可以复制一个旅程的一活动或多个旅程，并将它们粘贴到同一旅程或不同旅程中。 如果要重复使用之前旅程中已配置的大量活动，这样可以节省时间。

**重要说明**

* 您可以跨不同的选项卡和浏览器进行复制／粘贴。 您只能复制／粘贴同一实例中的活动。
* 如果目标旅程具有使用其他事件的事件，则无法复制／粘贴命名空间。
* 粘贴的活动可能引用目标旅程中不存在的数据，例如，如果您跨不同的沙箱复制／粘贴。 始终检查错误并进行所需的调整。
* 请注意，您无法撤消操作。 要删除粘贴的活动，您需要选择并删除它们。 因此，请确保在复制活动之前只选择所需的数据。
* 您可以从任何旅程中复制活动，甚至是只读旅程。
* 您可以选择任何活动，甚至是未链接的。 链接的活动在粘贴后将保持链接。

以下是复制／粘贴活动的步骤：

1. 开启旅程。
1. 单击时移动鼠标，选择要复制的活动。 您还可以在按Ctrl/Command键的同时单 **击每个活动** 。 如 **果要选择所有活动** ，请使用Ctrl/Command + A。
   ![](../assets/copy-paste1.png)
1. 按 **Ctrl/Command + C**。
如果只想复制一个活动，可单击该，然后使 **用活动配置窗格左上** 方的“复制”图标。
   ![](../assets/copy-paste2.png)
1. 在任何旅程中， **按Ctrl/Command** + V粘贴活动，而不将它们链接到现有节点。 粘贴的活动以相同的顺序放置。 粘贴后，活动将保持选中状态，以便轻松移动它们。 还可以将光标放在空的占位符上并按 **下Ctrl/Command + V**。 粘贴的活动将链接到该节点。
   ![](../assets/copy-paste3.png)

