---
product: adobe campaign
title: 使用历程设计器
description: 了解有关使用历程设计器的更多信息
feature: Journeys
role: User
level: Intermediate
exl-id: 2f001e42-46dd-48aa-b3dd-23bfdf97e1c7
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '1474'
ht-degree: 5%

---

# 使用历程设计器 {#concept_m1g_5qt_52b}


>[!CAUTION]
>
>**正在查找Adobe Journey Optimizer**？ 单击[此处](https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer/using/ajo-home){target="_blank"}获取Journey Optimizer文档。
>
>
>_本文档参考已被Journey Optimizer替换的旧版Journey Orchestration资料。 如果您对访问Journey Orchestration或Journey Optimizer有任何疑问，请联系您的帐户团队。_


历程主页菜单允许您查看历程的&#x200B;**列表**。 创建新历程或单击现有历程以打开&#x200B;**历程设计器的界面**。 设计器由以下区域组成：调色板、画布和活动配置窗格。

## 历程列表 {#journey_list}

**历程列表**&#x200B;允许您同时查看所有历程、查看其状态并执行基本操作。 您可以重复、停止或删除您的历程。某些操作可能不可用，具体取决于历程。例如，您无法删除或重新启动已关闭的历程。您可以从中创建新版本、复制它或停止它。 您还可以使用搜索栏搜索历程。

单击列表左上角的过滤器图标即可访问 **[!UICONTROL Filters]**。过滤器菜单允许您根据不同的条件（状态、您创建的条件、过去30天内修改的条件、仅限最新版本等）筛选显示的历程。 您还可以选择仅显示使用特定事件、字段组或操作的历程。 可以配置列表中显示的列。 每个用户都会保存所有筛选器和列。

![](../assets/journey74.png)

历程的所有版本都会显示在带有版本号的列表中。 请参阅[此页](../building-journeys/journey-versions.md)。

![](../assets/journey37.png)

>[!NOTE]
>
>要在其他浏览器选项卡中打开历程的画布，请按住&#x200B;**Control**&#x200B;或&#x200B;**Command**&#x200B;键并单击历程。

## 面板 {#palette}

**调色板**&#x200B;位于屏幕的左侧。 所有可用活动都分为几个类别： **[!UICONTROL Events]**、**[!UICONTROL Orchestration]**&#x200B;和&#x200B;**[!UICONTROL Actions]**。 您可以通过单击不同类别的名称来展开/折叠这些类别。 要在历程中使用活动，请将其从面板拖放到画布中。 在下一步骤中，您还可以双击面板中的活动以将其添加到画布。 您必须在发布历程之前配置从面板添加的每个活动。 如果将活动拖放到画布中并且未完成其配置，则该活动将停留在画布中，但会出现红色警告，指示此活动的配置未完成。

>[!NOTE]
>
>请注意，设置历程时存在规则。 将放弃不允许的配置。 例如，您不能同时执行操作、将活动链接到上一步来创建循环、使用事件之外的其他内容开始历程等。

![](../assets/journey38.png)

左上角的&#x200B;**[!UICONTROL Filter items]**&#x200B;图标允许您显示以下过滤器：

* **仅显示可用项**：在面板中隐藏或显示不可用的元素，例如使用不同于您的历程中使用的命名空间的事件。 默认情况下，不可用项目处于隐藏状态。 如果选择显示它们，它们将显示为灰色。

* **仅显示最近使用的项目**：此筛选器除开箱即用的事件和操作外，还允许您仅显示最近使用的五个事件和操作。 这具体取决于每个用户。默认情况下，将显示所有项目。

![](../assets/palette-filter.png)

您还可以使用&#x200B;**[!UICONTROL Search]**&#x200B;字段。 仅过滤事件和操作。

## 画布 {#canvas}

**画布**&#x200B;是历程设计器中的中心区域。 您可以在此区域中删除并配置活动。 单击画布中的活动以进行配置。 这将打开右侧的活动配置窗格。 您可以使用右上角的“+”和“ — ”按钮进行放大和缩小。 在画布中，所有活动都允许您在活动之后添加下一步，但&#x200B;**[!UICONTROL End]**&#x200B;活动除外（请参阅[此页面](../building-journeys/end-activity.md)）。

![](../assets/journey39.png)

## 活动配置窗格 {#configuration_pane}

单击面板中的某个活动时，将显示&#x200B;**活动配置窗格**。 填写必填字段。 单击&#x200B;**[!UICONTROL Delete]**&#x200B;图标以删除该活动。 单击&#x200B;**[!UICONTROL Cancel]**&#x200B;以取消修改，或单击&#x200B;**[!UICONTROL Ok]**&#x200B;以确认。 要删除活动，您还可以选择一个（或多个）活动并按Backspace键。 按Esc键将关闭活动配置窗格。

在画布中，操作和事件活动由一个图标表示，图标下方显示了事件或操作的名称。 在活动配置窗格中，您可以使用&#x200B;**[!UICONTROL Label]**&#x200B;字段向活动名称添加后缀。 这些标签可帮助您根据上下文来使用事件和操作，尤其是在历程中多次使用同一事件或操作时。 您还将能够在[!DNL Journey Orchestration]报表中查看您添加的标签。 您还可以为条件活动定义标签。

默认情况下，只读字段处于隐藏状态。 要显示只读字段，请单击活动配置窗格左上角的&#x200B;**显示只读字段**&#x200B;图标。 此设置适用于所有历程中的所有活动。

![](../assets/journey59bis.png)

## 顶部栏操作 {#top_actions}

根据历程的状态，您可以使用右上角的按钮对历程执行不同的操作： **[!UICONTROL Publish]**、**[!UICONTROL Duplicate]**、**[!UICONTROL Delete]**、**[!UICONTROL Journey properties]**、**[!UICONTROL Test]**。 如果未选择任何活动，则会显示这些按钮。 某些按钮将会根据上下文显示。 激活测试模式时，将显示测试模式日志按钮（请参阅[此页面](../building-journeys/testing-the-journey.md)）。 当历程处于活动状态、停止状态或关闭状态时，将显示“报告”按钮。

![](../assets/journey41.png)

## 在画布中使用路径 {#paths}

多个活动（**[!UICONTROL Condition]**、**[!UICONTROL Action]**&#x200B;个活动）允许您定义在发生错误或超时时的回退操作。 在活动配置窗格中，选中方框： **[!UICONTROL Add an alternative path in case of a timeout or an error]**。 活动后会添加其他路径。 超时持续时间在历程的属性中定义（请参阅[管理员用户在此页面](../building-journeys/changing-properties.md)）。 例如，如果电子邮件发送时间过长或出错，您可以决定发送短信。

![](../assets/journey42.png)

利用各种活动（事件、操作、等待），可在活动之后添加多个路径。 为此，请将光标放在活动上并单击“+”符号。 只有事件和等待活动可以并行设置。 如果并行设置多个事件，则选择的路径将是第一个发生的事件之一。

在侦听事件时，我们建议您不要无限期地等待该事件。 这不是强制性的，只是最佳做法。 如果只想在特定时间内侦听一个或多个事件，则可以并行放置一个或多个事件和等待活动。 请参阅[此小节](../building-journeys/event-activities.md#section_vxv_h25_pgb)。

要删除路径，请将光标放在路径上并单击&#x200B;**[!UICONTROL Delete arrow]**&#x200B;图标。

![](../assets/journey42ter.png)

在画布中，当两个活动断开连接时，会显示警告。 将光标放在警告图标上以显示错误消息。 要解决此问题，只需移动断开连接的活动，并将其连接到上一个活动即可。

![](../assets/canvas-disconnected.png)

## 复制和粘贴活动 {#copy-paste}

您可以复制历程的一个或多个活动，并将其粘贴到同一历程或其他历程中。 如果您希望重用之前历程中已配置的多个活动，这可以节省时间。

**重要备注**

* 您可以在不同选项卡和浏览器之间复制/粘贴。 您只能复制/粘贴同一实例中的活动。
* 如果目标历程具有使用其他命名空间的事件，则无法复制/粘贴事件。
* 粘贴的活动可能引用目标历程中不存在的数据，例如，如果您在不同沙盒之间复制/粘贴。 始终检查错误并进行所需的调整。
* 请注意，无法撤消操作。 要删除粘贴的活动，您需要选择并删除它们。 因此，在复制活动之前，请确保仅选择所需的活动。
* 您可以从任何历程中复制活动，甚至可以复制处于只读状态的活动。
* 您可以选择任何活动，甚至是未链接的活动。 链接的活动在粘贴后将保持链接。

以下是复制/粘贴活动的步骤：

1. 打开历程。
1. 单击时移动鼠标，选择要复制的活动。 在按&#x200B;**Ctrl/Command**&#x200B;键时，您还可以单击每个活动。 如果要选择所有活动，请使用&#x200B;**Ctrl/Command + A**。
   ![](../assets/copy-paste1.png)
1. 按&#x200B;**Ctrl/Command + C**。
如果只想复制一个活动，可以单击该活动并使用活动配置窗格左上角的&#x200B;**复制**&#x200B;图标。
   ![](../assets/copy-paste2.png)
1. 在任何历程中，按&#x200B;**Ctrl/Command + V**&#x200B;粘贴活动而不将其链接到现有节点。 粘贴的活动将按相同顺序放置。 粘贴后，活动将保持选中状态，以便您轻松移动活动。 您还可以将光标放在空的占位符上并点击&#x200B;**Ctrl/Command + V**。 粘贴的活动将链接到节点。
   ![](../assets/copy-paste3.png)
