---
product: adobe campaign
title: 关于历程报告
description: 了解如何构建历程报告
feature: Journeys
role: User
level: Intermediate
exl-id: 93768321-b171-4338-a440-6ea189a85a4a
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '777'
ht-degree: 1%

---

# 关于历程报告 {#concept_rfj_wpt_52b}


>[!CAUTION]
>
>**正在查找Adobe Journey Optimizer**？ 单击[此处](https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer/using/ajo-home){target="_blank"}获取Journey Optimizer文档。
>
>
>_本文档参考已被Journey Optimizer替换的旧版Journey Orchestration资料。 如果您对访问Journey Orchestration或Journey Optimizer有任何疑问，请联系您的帐户团队。_



>[!NOTE]
>
>仅当您具有Adobe Campaign Standard时，才会填充投放数据和区段组件。

本节将介绍如何访问和使用报告来衡量历程的有效性。

## 报告界面 {#reporting-interface}

例如，顶部工具栏允许您修改、保存或打印报告。

![](../assets/dynamic_report_toolbar.png)

使用&#x200B;**[!UICONTROL Project]**&#x200B;选项卡可以：

* **[!UICONTROL Open]**：打开之前创建的报表或模板。
* **[!UICONTROL Save As]**：重复模板以便能够修改它们。
* **[!UICONTROL Refresh project]**：根据新数据和筛选器更改更新报告。
* **[!UICONTROL Download CSV]**：将报表导出到CSV文件。
* **[!UICONTROL Print]**：打印报告。

**[!UICONTROL Edit]**&#x200B;选项卡允许您：

* **[!UICONTROL Undo]**：取消您在仪表板上的上一个操作。
* **[!UICONTROL Redo]**：取消您的仪表板上的上一个&#x200B;**[!UICONTROL Undo]**&#x200B;操作。
* **[!UICONTROL Clear all]**：删除仪表板上的每个面板。

**[!UICONTROL Insert]**&#x200B;表允许您通过向仪表板添加图形和表来自定义报表：

* **[!UICONTROL New Blank Panel]**：向仪表板添加新的空白面板。
* **[!UICONTROL New Freeform]**：向仪表板中添加新的自由格式表。
* **[!UICONTROL New Line]**：向仪表板添加新的折线图。
* **[!UICONTROL New Bar]**：向仪表板添加新的条形图。

通过左侧的选项卡，您可以构建报告并根据需要过滤数据。

![](../assets/dynamic_report_interface.png)

这些选项卡可让您访问以下项目：

* **[!UICONTROL Panels]**：在报表中添加空白面板或自由格式以开始筛选数据。 有关更多信息，请参阅[添加面板](../reporting/creating-your-journey-reports.md#adding-panels)部分
* **[!UICONTROL Visualizations]**：拖放所选的可视化项以为您的报表提供一个图形维度。 有关更多信息，请参阅[添加可视化图表](../reporting/creating-your-journey-reports.md#adding-visualizations)部分。
* **[!UICONTROL Components]**：使用不同的维度、量度、区段和时间段自定义您的报表。 有关更多信息，请参阅[添加组件](../reporting/creating-your-journey-reports.md#adding-components)一节。

## 历程摘要模板 {#ootb-template}

报告分为两类：现成模板和自定义报告。
现成模板**[!UICONTROL Journey summary]**&#x200B;为您提供了最重要的跟踪数据的清晰视图。

![](../assets/dynamic_report_journey_8.png)

每个表格都由摘要数字和图表表示。 您可以更改详细信息在其各自可视化图表设置中的显示方式。

报表顶部提供了以下KPI：

* **[!UICONTROL Journey - Entered]**：到达历程进入事件的个人总数。
* **[!UICONTROL Journey - Completion rate]**：与进入历程的个人总数相比，到达历程结束的个人总数（或者，如果个人不符合任何条件）。
* **[!UICONTROL Journey - Current]**：历程中当前个人的总数。
* **[!UICONTROL Journey - Failed rate]**：与运行历程数相比，未成功执行的历程总数。
* **[!UICONTROL Delivery - Messages sent]**：已发送的邮件总数。
* **[!UICONTROL Delivery rate]**：与已发送的邮件数相比，已成功传递的邮件总数。
* **[!UICONTROL Delivery - Bounce rate]**：退回的邮件总数与发送的邮件数之比。
* **[!UICONTROL Delivery - Unsubscribed rate]**：与传递的邮件相比，收件人退订的总数。
* **[!UICONTROL Delivery - Open rate]**：打开的邮件总数与已送达的邮件数的比较。
* **[!UICONTROL Delivery - Click rate]**：与已投放邮件数相比，投放中的点击总数。

历程流可视化允许您查看目标用户档案的路径，以分步方式浏览历程。 仅当定位一个历程时，此选项才可用。 它是自动生成的，无法修改。

![](../assets/dynamic_report_journey_10.png)

**[!UICONTROL Journey summary]**&#x200B;表包含历程可用的数据，例如：

* **[!UICONTROL Entered]**：到达历程进入事件的个人总数。
* **[!UICONTROL Completion rate]**：与进入历程的个人总数相比，已达到历程的结束流量控制的个人总数。
* **[!UICONTROL Current]**：历程中当前个人的总数。
* **[!UICONTROL Failed]**：未成功执行的历程总数。
* **[!UICONTROL Failed rate]**：与运行历程数相比，未成功执行的历程总数。

**[!UICONTROL Top events]**&#x200B;表显示最成功的事件和历程中最成功的操作&#x200B;**[!UICONTROL Top action]**。

![](../assets/dynamic_report_journey_11.png)

**[!UICONTROL Delivery - Sending summary]**&#x200B;表包含可用于历程投放的数据，例如：

* **[!UICONTROL Processed/sent]**：已发送的邮件总数。
* **[!UICONTROL Delivered rate]**：与已发送的邮件数相比，已成功传递的邮件总数。
* **[!UICONTROL Delivered]**：成功发送的邮件数，与已发送的邮件总数相关。
* **[!UICONTROL Bounce + error rate]**：退回的邮件总数与发送的邮件数之比。
* **[!UICONTROL Bounces + errors]**：投放和自动返回处理期间累计的错误总数与已发送消息的总数相关。

**[!UICONTROL Delivery - Tracking summary]**&#x200B;表包含可用于跟踪历程投放成功性的数据，例如：

* **[!UICONTROL Open Rate]**：已打开邮件的百分比。
* **[!UICONTROL Open]**：传递中打开邮件的次数。
* **[!UICONTROL Click trough rate]**：与已投放邮件数相比，投放中的点击总数。
* **[!UICONTROL Click]**：在投放中点击内容的次数。
* **[!UICONTROL Unsubscribe rate]**：收件人的退订次数与已传递邮件的百分比。
* **[!UICONTROL Unsubscribed]**：与传递的邮件相比，收件人退订的总数。
