---
title: 使用旅程设计器
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
source-git-commit: e53ecd96bbb308fe109843de6f64cde4cba5e246

---


# 使用旅程设计器 {#concept_m1g_5qt_52b}

旅程“主页”菜单允许您视图旅 **程的列表**。 创建新的旅程或单击现有的旅程以打开旅 **程设计人员的界面**。 设计人员由以下区域组成：调色板、画布和活动配置窗格。

## 旅程列表 {#journey_list}

旅 **程列表** ，您可以同时视图所有旅程，查看其状态并执行基本操作。 您可以重复、停止或删除您的旅程。 根据旅程，某些操作可能不可用。 例如，您无法删除或重新开始已完成的旅程。 您可以从中创建新版本、重复或停止它。 您还可以使用搜索栏搜索旅程。

单 **[!UICONTROL Filters]** 击列表左上角的过滤器图标即可访问。 过滤器菜单允许您根据不同的条件（状态、您创建的、在过去30天内修改的、仅限最新版本等）筛选显示的旅程。 您还可以选择仅显示使用特定事件、字段组或操作的旅程。 可以配置列表上显示的列。 所有过滤器和列均按用户保存。

![](../assets/journey74.png)

您的旅程的所有版本都显示在列表中，并带有版本号。 请参见 [](../building-journeys/journey-versions.md)。

![](../assets/journey37.png)

>[!NOTE]
>
>要在其他浏览器选项卡中打开旅程画布，请按住 **Control****或Command键** ，然后单击该旅程。

## 调色板 {#palette}

调 **色板** 位于屏幕的左侧。 所有可用活动分为几个类别: **[!UICONTROL Events]**&#x200B;和 **[!UICONTROL Orchestration]****[!UICONTROL Actions]**。 您可以通过单击不同类别的名称展开／折叠其名称。 要在旅程中使用活动，请将其从调色板中拖放到画布中。 您还可以在调色板中多次单击活动，将其添加到画布中（下一步可用）。 您必须先配置从调色板中添加的每个活动，然后再发布旅程。 如果将某个活动放在画布中，但未完成其配置，该活动将保留在画布中，但会出现红色警告，指示该配置未完成。

>[!NOTE]
>
>请注意，设置旅程时有一些规则。 将丢弃不允许的配置。 例如，您不能并行放置操作、将活动链接到上一步以创建循环、将旅程与事件以外的内容开始等。

![](../assets/journey38.png)

使用左 **上角的“显示禁用的项目** ”图标可隐藏或显示调色板中不可用的元素，例如使用与旅程中使用的命名空间不同的事件的区域。 默认情况下，不可用的项目是隐藏的。 如果选择显示它们，则它们将灰显。

使用“搜 **索** ”字段时，将显示每个画布活动类别的结果数。

![](../assets/palette-filter.png)

## 画布 {#canvas}

画 **布** 是旅程设计者的中心区域。 您可以在此区域放置活动并配置它们。 单击画布中的活动进行配置。 这将打开右侧的活动配置窗格。 您可以使用右上角的“+”和“-”按钮进行放大和缩小。 在画布中，所有活动允许您在它们之后添加下一步，但活动除外 **[!UICONTROL End]** (请参阅 [](../building-journeys/end-activity.md))。

![](../assets/journey39.png)

## 活动配置窗格 {#configuration_pane}

单击 **调色板中的活动** ，将显示活动配置窗格。 填写必填字段。 单击该图 **[!UICONTROL Delete]** 标可删除活动。 单击可 **[!UICONTROL Cancel]** 取消修改或进行 **[!UICONTROL Ok]** 确认。 要删除活动，还可以选择一个活动（或多个）并按Backspace键。 按转义键将关闭活动配置窗格。

在画布中，您的操作和事件活动由图标表示，该图标的名称显示在下方。 在活动配置窗格中，可以使用字 **[!UICONTROL Label]** 段向活动名称添加后缀。 这些标签将帮助您将事件和动作的使用情境化，尤其是当您在旅程中多次使用相同的事件或动作时。 您还可以看到在“旅程编排”报告中添加的标签。

![](../assets/journey59bis.png)

## 顶栏操作 {#top_actions}

根据旅程的状态，您可以使用右上角的按钮对旅程执行不同的操作： **[!UICONTROL Publish]**, **[!UICONTROL Duplicate]**, **[!UICONTROL Delete]**, **[!UICONTROL Journey properties]**, **[!UICONTROL Test]**. 如果未选择活动，则显示这些按钮。 某些按钮将根据上下文显示。 在激活测试模式时，将显示测试模式日志按钮(请参 [](../building-journeys/testing-the-journey.md)阅)。 当旅程实时、停止或完成时，将显示报告按钮。

![](../assets/journey41.png)

## 在画布中使用路径 {#paths}

多个活动(**[!UICONTROL Condition]**&#x200B;活动 **[!UICONTROL Action]** )允许您在出现错误或超时时定义回退操作。 在活动配置窗格中，选中复选框： **[!UICONTROL Add an alternative path in case of a timeout or an error]**. 在活动后添加另一个路径。 超时持续时间在旅程的属性中定义(由管理 [](../building-journeys/changing-properties.md) 员用户查看)。 例如，如果电子邮件发送时间过长或出错，您可以决定发送SMS。

![](../assets/journey42.png)

各种活动(事件、操作、等待)允许您在其后添加多个路径。 为此，请将光标放在活动上并单击“+”符号。 只能同时设置事件和等待活动。 如果多个事件并行设置，则所选路径将是第一个事件。

在听取事件时，我们建议您不要无限期地等待事件。 它不是强制性的，只是最佳实践。 如果您只想在特定时间内聆听一个或多个事件，您将同时放置一个或多个事件和一个等待活动。 请参见 [](../building-journeys/event-activities.md#section_vxv_h25_pgb)。

要删除路径，请将光标放在该路径上并单击该 **[!UICONTROL Delete arrow]** 图标。

![](../assets/journey42ter.png)

在画布中，当两个活动断开连接时，将显示一条警告。 将光标放在警告图标上以显示错误消息。 要解决该问题，只需移动断开连接的活动并将其连接到上一个活动。

![](../assets/canvas-disconnected.png)