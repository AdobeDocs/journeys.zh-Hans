---
product: adobe campaign
solution: Journey Orchestration
title: 关于旅程报告
description: 了解如何构建旅程报告
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '732'
ht-degree: 1%

---


# 关于旅程报告 {#concept_rfj_wpt_52b}

>[!NOTE]
>
>投放数据和区段组件仅在您拥有Adobe Campaign Standard时才会填充。

本节将向您介绍如何访问和使用报告来衡量您的旅程的有效性。

## 报告界面 {#reporting-interface}

例如，顶部工具栏允许您修改、保存或打印报表。

![](../assets/dynamic_report_toolbar.png)

使用&#x200B;**[!UICONTROL Project]**&#x200B;选项卡可以：

* **[!UICONTROL Open]**:打开以前创建的报告或模板。
* **[!UICONTROL Save As]**:重复模板，以便能够修改它们。
* **[!UICONTROL Refresh project]**:根据新数据和对过滤器的更改更新您的报告。
* **[!UICONTROL Download CSV]**:将报表导出为CSV文件。
* **[!UICONTROL Print]**:打印您的报告。

**[!UICONTROL Edit]**&#x200B;选项卡允许您：

* **[!UICONTROL Undo]**:取消您对仪表板的上次操作。
* **[!UICONTROL Redo]**:取消您对仪表板 **[!UICONTROL Undo]** 的上次操作。
* **[!UICONTROL Clear all]**:删除仪表板上的每个面板。

**[!UICONTROL Insert]**&#x200B;表允许您通过向仪表板添加图形和表来自定义报表：

* **[!UICONTROL New Blank Panel]**:将新的空白面板添加到仪表板。
* **[!UICONTROL New Freeform]**:为仪表板添加新的自由形式表。
* **[!UICONTROL New Line]**:为仪表板添加新的折线图。
* **[!UICONTROL New Bar]**:为仪表板添加新条形图。

使用左侧选项卡，您可以根据需要构建报表和筛选数据。

![](../assets/dynamic_report_interface.png)

这些选项卡允许您访问以下项目：

* **[!UICONTROL Panels]**:在报表中添加空白面板或自由形式，以开始过滤数据。有关详细信息，请参阅[添加面板](../reporting/creating-your-journey-reports.md#adding-panels)部分
* **[!UICONTROL Visualizations]**:拖放一系列可视化项目，为报表提供图形维度。有关详细信息，请参阅[添加可视化](../reporting/creating-your-journey-reports.md#adding-visualizations)部分。
* **[!UICONTROL Components]**:使用不同的维度、指标、细分和时间段自定义您的报表。有关详细信息，请参阅[添加组件](../reporting/creating-your-journey-reports.md#adding-components)部分。

## 旅程摘要模板{#ootb-template}

报告分为两个类别:现成的模板和自定义报告。
现成的模板**[!UICONTROL Journey summary]**&#x200B;为您提供了最重要的跟踪视图。

![](../assets/dynamic_report_journey_8.png)

每个表由摘要编号和图表表示。 您可以更改详细信息在其各自的可视化设置中的显示方式。

报表顶部提供以下KPI:

* **[!UICONTROL Journey - Entered]**:到达旅程入口事件的个人总数。
* **[!UICONTROL Journey - Completion rate]**:到达旅程结束的个人总数（或者，如果某个人不符合任何条件）与进入旅程的个人总数相比。
* **[!UICONTROL Journey - Current]**:当前旅程中的个人总数。
* **[!UICONTROL Journey - Failed rate]**:未成功执行的旅程总数与run旅程的总数。
* **[!UICONTROL Delivery - Messages sent]**:已发送邮件总数。
* **[!UICONTROL Delivery rate]**:与已发送的消息相比，成功传送的消息总数。
* **[!UICONTROL Delivery - Bounce rate]**:与发送的邮件相比，弹回的邮件总数。
* **[!UICONTROL Delivery - Unsubscribed rate]**:按收件人划分的退订总数与已传递的消息相比。
* **[!UICONTROL Delivery - Open rate]**:已打开邮件的总数与已传递邮件的数量相比。
* **[!UICONTROL Delivery - Click rate]**:投放中的点击总数与已传递消息的数量相比。

旅程流可视化允许您分步查看目标用户档案在旅程中的路径。 仅当定位一个旅程时，此选项才可用。 它是自动生成的，无法修改。

![](../assets/dynamic_report_journey_10.png)

**[!UICONTROL Journey summary]**&#x200B;表包含可用于旅程的数据，如：

* **[!UICONTROL Entered]**:到达旅程入口事件的个人总数。
* **[!UICONTROL Completion rate]**:到达旅程的最终流控制的个人总数与进入旅程的个人总数之比。
* **[!UICONTROL Current]**:当前旅程中的个人总数。
* **[!UICONTROL Failed]**:未成功执行的旅程总数。
* **[!UICONTROL Failed rate]**:未成功执行的旅程总数与run旅程的总数。

**[!UICONTROL Top events]**&#x200B;表显示您旅程中最成功的事件和最成功的&#x200B;**[!UICONTROL Top action]**&#x200B;操作。

![](../assets/dynamic_report_journey_11.png)

**[!UICONTROL Delivery - Sending summary]**&#x200B;表包含可用于旅程投放的数据，如：

* **[!UICONTROL Processed/sent]**:已发送邮件总数。
* **[!UICONTROL Delivered rate]**:与已发送的消息相比，成功传送的消息总数。
* **[!UICONTROL Delivered]**:已成功发送的消息数，与已发送消息的总数有关。
* **[!UICONTROL Bounce + error rate]**:与发送的邮件相比，弹回的邮件总数。
* **[!UICONTROL Bounces + errors]**:在投放和自动返回处理期间累积的与已发送消息总数相关的错误总数。

**[!UICONTROL Delivery - Tracking summary]**&#x200B;表包含跟踪您旅程投放成功情况的可用数据，如：

* **[!UICONTROL Open Rate]**:已打开邮件的百分比。
* **[!UICONTROL Open]**:在投放中打开消息的次数。
* **[!UICONTROL Click trough rate]**:投放中的点击总数与已传递消息的数量相比。
* **[!UICONTROL Click]**:在投放中单击内容的次数。
* **[!UICONTROL Unsubscribe rate]**:按收件人划分的退订与已传送消息的百分比。
* **[!UICONTROL Unsubscribed]**:按收件人划分的退订总数与已传递的消息相比。
