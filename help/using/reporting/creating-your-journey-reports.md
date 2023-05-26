---
product: adobe campaign
title: 创建历程报告
description: 了解如何创建历程报告
feature: Journeys
role: User
level: Intermediate
exl-id: 0d2417e9-5b3f-442d-a00d-8b4df239d952
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '825'
ht-degree: 3%

---

# 创建历程报告 {#concept_rfj_wpt_52b}

## 访问和创建报告 {#accessing-reports}

>[!NOTE]
>
>删除历程后，所有关联的报告将不再可用。

本节将介绍如何创建或使用现成的报告。 将面板、组件和可视化图表组合在一起，以便更好地跟踪您的旅程是否成功。

要访问历程报告并开始跟踪投放是否成功，请执行以下操作：

1. 在顶部菜单中，单击 **[!UICONTROL Home]**&#x200B;选项卡。

1. 选择要报告的历程。

   请注意，您还可以通过单击 **报告** 将鼠标悬停在历程列表中的历程上时。

   ![](../assets/dynamic_report_journey.png)

1. 单击 **[!UICONTROL Report]** 图标。

   ![](../assets/dynamic_report_journey_2.png)

1. 此 **[!UICONTROL Journey summary]** 现成的报告会显示在屏幕上。 要访问自定义报表，请单击 **[!UICONTROL Close]** 按钮。

   ![](../assets/dynamic_report_journey_12.png)

1. 单击 **[!UICONTROL Create new project]** 以从头开始创建报告。

   ![](../assets/dynamic_report_journey_3.png)

1. 从 **[!UICONTROL Panels]** 选项卡，根据需要拖放任意数量的面板或自由格式表。 有关更多信息，请参阅此 [部分](#adding-panels).

   ![](../assets/dynamic_report_journey_4.png)

1. 然后，您可以通过从以下位置拖放维度和量度来开始筛选数据： **[!UICONTROL Components]** 选项卡。 有关更多信息，请参阅此 [部分](#adding-components).

   ![](../assets/dynamic_report_journey_5.png)

1. 为了更清楚地查看数据，您可以从 **[!UICONTROL Visualizations]** 选项卡。 有关更多信息，请参阅此 [部分](#adding-visualizations).

## 添加面板{#adding-panels}

### 添加空白面板 {#adding-a-blank-panel}

要启动报表，可向现成报表或自定义报表添加一组面板。 每个面板包含不同的数据集，由自由格式表和可视化图表组成。

利用此面板，可根据需要构建报告。 您可以在报表中添加任意数量的面板，以按不同的时间段筛选数据。

1. 单击 **[!UICONTROL Panels]** 图标。您还可以通过单击 **[!UICONTROL Insert tab]** 和选择 **[!UICONTROL New Blank Panel]**.

   ![](../assets/dynamic_report_panel_1.png)

1. 拖放 **[!UICONTROL Blank Panel]** 进入您的信息板。

   ![](../assets/dynamic_report_panel.png)

您现在可以将自由格式表添加到面板中以开始定位数据。

### 添加自由格式表 {#adding-a-freeform-table}

自由格式表允许您创建一个表，以使用 **[!UICONTROL Component]** 表格。

每个表和可视化图表均可调整大小，并且可以移动以更好地自定义您的报表。

1. 单击 **[!UICONTROL Panels]** 图标。

   ![](../assets/dynamic_report_panel_1.png)

1. 拖放 **[!UICONTROL Freeform]** 项放入您的仪表板。

   您也可以通过单击 **[!UICONTROL Insert]** 选项卡并选择 **[!UICONTROL New Freeform]** 或通过单击 **[!UICONTROL Add a freeform table]** 在空面板中。

   ![](../assets/dynamic_report_panel_2.png)

1. 将项目从 **[!UICONTROL Components]** 按Tab键进入列和行以构建表。

   ![](../assets/dynamic_report_freeform_3.png)

1. 单击 **[!UICONTROL Settings]** 图标来更改数据在列中的显示方式。

   ![](../assets/dynamic_report_freeform_4.png)

   此 **[!UICONTROL Column settings]** 由以下部分组成：

   * **[!UICONTROL Number]**：用于显示或隐藏列中的概要数字。
   * **[!UICONTROL Percent]**：用于显示或隐藏列中的百分比。
   * **[!UICONTROL Interpret zero as no value]**：用于在值等于零时显示或隐藏。
   * **[!UICONTROL Background]**：用于显示或隐藏单元格中的水平进度条。
   * **[!UICONTROL Include retries]**：用于在结果中包含重试。 此项仅适用于 **[!UICONTROL Sent]** 和 **[!UICONTROL Bounces + Errors]**.

1. 选择一行或多行，然后单击 **[!UICONTROL Visualize]** 图标。 添加了一个可视化图表以反映您选择的行。

   ![](../assets/dynamic_report_freeform_5.png)

您现在可以根据需要添加任意数量的组件，还可以添加可视化图表以直观地表示您的数据。

## 添加组件{#adding-components}

组件可帮助您使用不同的维度、量度和时间段自定义报表。

1. 单击 **[!UICONTROL Components]** 选项卡以访问组件列表。

   ![](../assets/dynamic_report_components.png)

1. 中显示的每个类别 **[!UICONTROL Components]** 选项卡显示五个最常用的项目，单击类别名称可访问其完整的组件列表。

   组件表分为三类：

   * **[!UICONTROL Dimensions]**：从投放日志获取详细信息，例如收件人的浏览器或域，或者投放是否成功。
   * **[!UICONTROL Metrics]**：获取有关消息状态的详细信息。 例如，如果消息已投放且用户已打开。
   * **[!UICONTROL Time]**：为表设置时间段。

1. 将组件拖放到面板中以开始筛选数据。

您可以根据需要拖放任意数量的组件，并将它们相互进行比较。

## 添加可视化{#adding-visualizations}

此 **[!UICONTROL Visualizations]** 选项卡允许您拖放可视化图表项目，例如区域、圆环图和图形。 可视化图表为您提供数据的图形表示形式。

1. 在 **[!UICONTROL Visualizations]** 选项卡，将可视化项拖放到面板中。

   ![](../assets/dynamic_report_visualization_1.png)

1. 向面板添加可视化图表后，报表将自动检测自由格式表中的数据。 选择可视化图表的设置。
1. 如果您有多个自由格式表，请在的图表中选择要添加的可用数据源 **[!UICONTROL Data Source Settings]** 窗口。 单击可视化图表标题旁边的彩色圆点也可使用此窗口。

   ![](../assets/dynamic_report_visualization_2.png)

1. 单击 **[!UICONTROL Visualization]** 设置按钮直接更改图形类型或图形上显示的内容，例如：

   * **[!UICONTROL Percentages]**：以百分比显示值。
   * **[!UICONTROL Anchor Y Axis at Zero]**：强制将y轴设为零，即使值范围在零以上也是如此。
   * **[!UICONTROL Legend visible]**：用于隐藏图例。
   * **[!UICONTROL Normalization]**：强制值匹配。
   * **[!UICONTROL Display Dual Axis]**：向图形中添加另一个轴。
   * **[!UICONTROL Limit Max Items]**：限制显示的图形数量。
   * **[!UICONTROL Threshold]**：用于为图表设置阈值。 它显示为黑色虚线。

   ![](../assets/dynamic_report_visualization_3.png)

此可视化图表允许您在报表中更清楚地查看数据。
