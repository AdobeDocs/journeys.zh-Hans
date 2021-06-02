---
product: adobe campaign
title: 关于历程报告
description: 了解如何构建历程报告
feature: 历程
role: Business Practitioner
level: Intermediate
exl-id: 93768321-b171-4338-a440-6ea189a85a4a
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '733'
ht-degree: 1%

---

# 关于历程报告 {#concept_rfj_wpt_52b}

>[!NOTE]
>
>仅当您具有Adobe Campaign Standard时，才会填充投放数据和区段组件。

本节将介绍如何访问和使用报告来衡量您的历程的有效性。

## 报告界面 {#reporting-interface}

例如，顶部工具栏允许您修改、保存或打印报表。

![](../assets/dynamic_report_toolbar.png)

使用&#x200B;**[!UICONTROL Project]**&#x200B;选项卡可执行以下操作：

* **[!UICONTROL Open]**:打开之前创建的报表或模板。
* **[!UICONTROL Save As]**:复制模板以便能够对其进行修改。
* **[!UICONTROL Refresh project]**:根据新数据和对过滤器所做的更改更新您的报表。
* **[!UICONTROL Download CSV]**:将报表导出为CSV文件。
* **[!UICONTROL Print]**:打印您的报表。

**[!UICONTROL Edit]**&#x200B;选项卡允许您：

* **[!UICONTROL Undo]**:取消您在功能板上的上次操作。
* **[!UICONTROL Redo]**:取消功能板 **[!UICONTROL Undo]** 上的上次操作。
* **[!UICONTROL Clear all]**:删除功能板上的每个面板。

**[!UICONTROL Insert]**&#x200B;表允许您通过向功能板添加图形和表格来自定义报表：

* **[!UICONTROL New Blank Panel]**:向功能板中添加新的空白面板。
* **[!UICONTROL New Freeform]**:向功能板中添加了新的自由格式表。
* **[!UICONTROL New Line]**:将新折线图添加到功能板。
* **[!UICONTROL New Bar]**:向功能板中添加新的条形图。

利用左侧选项卡，可构建报表并根据需要过滤数据。

![](../assets/dynamic_report_interface.png)

利用这些选项卡，可访问以下项目：

* **[!UICONTROL Panels]**:在报表中添加一个空白面板或自由格式，以开始过滤数据。有关更多信息，请参阅[添加面板](../reporting/creating-your-journey-reports.md#adding-panels)一节
* **[!UICONTROL Visualizations]**:拖放一系列可视化项目，为报表提供图形维度。有关更多信息，请参阅[添加可视化图表](../reporting/creating-your-journey-reports.md#adding-visualizations)一节。
* **[!UICONTROL Components]**:使用不同的维度、量度、区段和时间段自定义您的报表。有关更多信息，请参阅[添加组件](../reporting/creating-your-journey-reports.md#adding-components)一节。

## 历程摘要模板{#ootb-template}

报表分为两类：现成的模板和自定义报表。
现成的模板**[!UICONTROL Journey summary]**&#x200B;可让您清楚地查看最重要的跟踪数据。

![](../assets/dynamic_report_journey_8.png)

每个表都由概要数字和图表表示。 您可以更改详细信息在各自的可视化设置中的显示方式。

以下KPI位于报表顶部：

* **[!UICONTROL Journey - Entered]**:到达历程的登入事件的个人总数。
* **[!UICONTROL Journey - Completion rate]**:到达历程结束的个人总数（或者当个人与任何条件不匹配时）与进入历程的个人总数相比。
* **[!UICONTROL Journey - Current]**:当前历程中的个人总数。
* **[!UICONTROL Journey - Failed rate]**:未成功执行的历程总数与运行历程的数量相比。
* **[!UICONTROL Delivery - Messages sent]**:已发送的消息总数。
* **[!UICONTROL Delivery rate]**:与已发送的消息相比，成功发送的消息总数。
* **[!UICONTROL Delivery - Bounce rate]**:与已发送的消息相比，已退回的消息总数。
* **[!UICONTROL Delivery - Unsubscribed rate]**:与已交付的消息相比，收件人取消订阅的总数。
* **[!UICONTROL Delivery - Open rate]**:已打开消息的总数与已投放消息的数量相比。
* **[!UICONTROL Delivery - Click rate]**:与已投放消息数相比，投放中的点击总数。

历程流量可视化图表允许您逐步查看目标用户档案在历程中的路径。 仅当定位一个历程时，此选项才可用。 它是自动生成的，无法修改。

![](../assets/dynamic_report_journey_10.png)

**[!UICONTROL Journey summary]**&#x200B;表包含可用于历程的数据，例如：

* **[!UICONTROL Entered]**:到达历程的登入事件的个人总数。
* **[!UICONTROL Completion rate]**:达到历程的最终流控制的个人总数，与进入历程的个人总数相比。
* **[!UICONTROL Current]**:当前历程中的个人总数。
* **[!UICONTROL Failed]**:未成功执行的历程总数。
* **[!UICONTROL Failed rate]**:未成功执行的历程总数与运行历程的数量相比。

**[!UICONTROL Top events]**&#x200B;表显示历程中最成功的事件和&#x200B;**[!UICONTROL Top action]**&#x200B;最成功的操作。

![](../assets/dynamic_report_journey_11.png)

**[!UICONTROL Delivery - Sending summary]**&#x200B;表包含可用于历程投放的数据，例如：

* **[!UICONTROL Processed/sent]**:已发送的消息总数。
* **[!UICONTROL Delivered rate]**:与已发送的消息相比，成功发送的消息总数。
* **[!UICONTROL Delivered]**:已成功发送的消息数，与已发送消息的总数有关。
* **[!UICONTROL Bounce + error rate]**:与已发送的消息相比，已退回的消息总数。
* **[!UICONTROL Bounces + errors]**:在投放和自动回访处理过程中累积的与已发送消息总数有关的错误总数。

**[!UICONTROL Delivery - Tracking summary]**&#x200B;表包含可用于跟踪历程交付成功与否的数据，例如：

* **[!UICONTROL Open Rate]**:已打开消息的百分比。
* **[!UICONTROL Open]**:投放中消息打开的次数。
* **[!UICONTROL Click trough rate]**:与已投放消息数相比，投放中的点击总数。
* **[!UICONTROL Click]**:在投放中点击内容的次数。
* **[!UICONTROL Unsubscribe rate]**:收件人取消订阅与已投放消息的百分比。
* **[!UICONTROL Unsubscribed]**:与已交付的消息相比，收件人取消订阅的总数。
