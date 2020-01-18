---
title: 使用旅程设计师
description: 进一步了解旅程设计人员的使用
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 1bc8d845716044671a11c200e4bab92302841994

---


# 使用旅程设计师 {#concept_m1g_5qt_52b}

旅程“主页”菜单允许您查看 **旅程列表**。 创建新的旅程或单击现有的旅程以打开旅 **程设计人员的界面**。 设计人员由以下区域组成：调色板、画布和活动配置窗格。

## 旅程列表 {#journey_list}

旅 **程列表** ，允许您同时查看所有旅程、查看其状态并执行基本操作。 您可以复制、停止或删除您的旅程。 根据旅程，某些操作可能不可用。 例如，您无法停止已停止的旅程。 您还可以使用搜索栏搜索旅程。

单 **[!UICONTROL Filters]**击列表左上角的过滤器图标可访问。 过滤器菜单允许您根据不同的条件（状态、您创建的、在过去30天内修改的、仅限最新版本等）过滤显示的旅程。 您还可以选择仅显示使用特定事件、字段组或操作的旅程。 可以配置列表中显示的列。 所有过滤器和列均按用户保存。

![](../assets/journey74.png)

您的旅程的所有版本都显示在列表中，并带有版本号。 请参见 [](../building-journeys/journey-versions.md)。

![](../assets/journey37.png)

>[!NOTE]
>
>要在其他浏览器选项卡中打开旅程画布，请按住 **Control****或Command键** ，然后单击该旅程。

## 调色板 {#palette}

调 **色板** 位于屏幕的左侧。 所有可用活动都分为几个类别： **[!UICONTROL Events]**和**[!UICONTROL Orchestration]****[!UICONTROL Actions]**。 您可以通过单击不同类别的名称展开／折叠这些类别。 要在旅程中使用活动，请将其从调色板中拖放到画布中。 您还可以双击调色板中的活动，在下一个步骤中将其添加到画布。 在发布旅程之前，您必须配置从调色板添加的每个活动。 如果将活动放在画布中但未完成其配置，则该活动将保留在画布中，但会出现红色警告，指示此活动的配置未完成。

>[!NOTE]
>
>请注意，设置旅程时有一些规则。 将丢弃不允许的配置。 例如，您不能并行放置操作、将活动链接到上一步以创建循环、以事件以外的内容开始旅程等。

![](../assets/journey38.png)

## 画布 {#canvas}

画 **布** 是旅程设计者的中心区域。 您可以在此区域拖放活动并进行配置。 单击画布中的活动可对其进行配置。 此操作将打开右侧的活动配置窗格。 您可以使用右上角的“+”和“-”按钮进行放大和缩小。 在画布中，所有活动都允许您在活动后面添加下一步，活动除 **[!UICONTROL End]**外(请参阅[](../building-journeys/end-activity.md))。

![](../assets/journey39.png)

## 活动配置窗格 {#configuration_pane}

单击 **调色板中的活动** ，将显示活动配置窗格。 填写必填字段。 单击该图 **[!UICONTROL Delete]**标可删除活动。 单击可**[!UICONTROL Cancel]** 取消修改或进行 **[!UICONTROL Ok]**确认。 要删除活动，您还可以选择一个活动（或多个），然后按Backspace键。 按转义键将关闭活动配置窗格。

在画布中，您的操作和活动由图标表示，该图标下面显示了事件或操作的名称。 在活动配置窗格中，您可以使用 **[!UICONTROL Label]**字段向活动名称添加后缀。 这些标签将帮助您将事件和动作的使用情境化，尤其是当您在旅程中多次使用同一事件或动作时。 您还可以查看在“旅程安排”报告中添加的标签。

![](../assets/journey59bis.png)

## 顶栏操作 {#top_actions}

根据旅程的状态，您可以使用右上角的按钮对旅程执行不同的操作： **[!UICONTROL Publish]**,**[!UICONTROL Duplicate]**, **[!UICONTROL Delete]**,**[!UICONTROL Journey properties]**, **[!UICONTROL Test]**. 未选择任何活动时，将显示这些按钮。 某些按钮将根据上下文显示。 在激活测试模式时，将显示测试模式日志按钮(请参[](../building-journeys/testing-the-journey.md)阅)。 当旅程实时、停止或完成时，将显示报告按钮。

![](../assets/journey41.png)

## 在画布中使用路径 {#paths}

多个活动(**[!UICONTROL Condition]**活动**[!UICONTROL Action]** )允许您定义在出现错误或超时时的回退操作。 在活动配置窗格中，选中复选框： **[!UICONTROL Add an alternative path in case of a timeout or an error]**. 活动后会添加另一个路径。 超时持续时间在旅程的属性中定义(由管理[](../building-journeys/changing-properties.md)员用户查看)。 例如，如果电子邮件发送时间过长或出错，您可以决定发送SMS。

![](../assets/journey42.png)

各种活动（事件、操作、等待）允许您在其后添加多个路径。 为此，请将光标放在活动上并单击“+”符号。 只能同时设置事件和等待活动。 如果多个事件设置为并行，则所选路径将是第一个发生的事件之一。

在收听活动时，我们建议您不要无限期地等待该活动。 它不是强制性的，只是最佳实践。 如果只想在特定时间内收听一个或多个事件，您将并行放置一个或多个事件和等待活动。 请参见 [](../building-journeys/event-activities.md#section_vxv_h25_pgb)。

要删除路径，请将光标放在该路径上，然后单击该 **[!UICONTROL Delete arrow]**图标。

![](../assets/journey42ter.png)
