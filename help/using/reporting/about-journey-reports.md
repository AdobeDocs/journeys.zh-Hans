---
product: adobe campaign
solution: Journey Orchestration
title: 关于历程报告
description: 了解如何构建旅程报告
feature: Journeys
role: Business Practitioner
level: Intermediate
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '736'
ht-degree: 1%

---


# 关于历程报告 {#concept_rfj_wpt_52b}

>[!NOTE]
>
>投放数据和区段组件仅在您拥有Adobe Campaign Standard时才会填充。

本节将向您介绍如何访问和使用报表来衡量您的旅程的有效性。

## 报告界面 {#reporting-interface}

例如，顶部工具栏允许您修改、保存或打印报表。

![](../assets/dynamic_report_toolbar.png)

使用&#x200B;**[!UICONTROL Project]**&#x200B;选项卡可以：

* **[!UICONTROL Open]**:打开以前创建的报表或模板。
* **[!UICONTROL Save As]**:重复模板，以便能够修改它们。
* **[!UICONTROL Refresh project]**:根据新数据和对过滤器的更改更新您的报告。
* **[!UICONTROL Download CSV]**:将报表导出为CSV文件。
* **[!UICONTROL Print]**:打印您的报告。

**[!UICONTROL Edit]**&#x200B;选项卡允许您：

* **[!UICONTROL Undo]**:取消您对仪表板的上次操作。
* **[!UICONTROL Redo]**:取消您对 **[!UICONTROL Undo]** 仪表板的上次操作。
* **[!UICONTROL Clear all]**:删除仪表板上的每个面板。

**[!UICONTROL Insert]**&#x200B;表允许您通过向仪表板添加图形和表来自定义报表：

* **[!UICONTROL New Blank Panel]**:将新的空白面板添加到仪表板。
* **[!UICONTROL New Freeform]**:将新的自由格式表添加到仪表板。
* **[!UICONTROL New Line]**:将新的折线图添加到仪表板。
* **[!UICONTROL New Bar]**:将新条形图添加到仪表板。

左侧选项卡可让您根据需要构建报表和筛选数据。

![](../assets/dynamic_report_interface.png)

这些选项卡允许您访问以下项目：

* **[!UICONTROL Panels]**:在报表中添加一个空白面板或自由格式，以便开始过滤您的数据。有关详细信息，请参阅[添加面板](../reporting/creating-your-journey-reports.md#adding-panels)部分
* **[!UICONTROL Visualizations]**:拖放一系列可视化项目，为报表提供图形维度。有关详细信息，请参阅[添加可视化](../reporting/creating-your-journey-reports.md#adding-visualizations)部分。
* **[!UICONTROL Components]**:使用不同的维度、量度、细分和时段自定义您的报表。有关详细信息，请参阅[添加组件](../reporting/creating-your-journey-reports.md#adding-components)部分。

## 历程摘要模板{#ootb-template}

报告分为两个类别:开箱即用的模板和自定义报告。
现成模板**[!UICONTROL Journey summary]**&#x200B;可为您明确视图最重要的跟踪数据。

![](../assets/dynamic_report_journey_8.png)

每个表都由摘要编号和图表表示。 您可以更改详细信息在各自的可视化设置中的显示方式。

报表顶部提供以下KPI:

* **[!UICONTROL Journey - Entered]**:到达旅程入口事件的总人数。
* **[!UICONTROL Journey - Completion rate]**:到达旅程结束的个人总数（或者如果某个人不符合任何条件）与进入旅程的个人总数相比。
* **[!UICONTROL Journey - Current]**:当前旅程中的个人总数。
* **[!UICONTROL Journey - Failed rate]**:未成功执行的旅程总数（与运行旅程总数相比）。
* **[!UICONTROL Delivery - Messages sent]**:已发送邮件的总数。
* **[!UICONTROL Delivery rate]**:与已发送的消息相比，成功传递的消息总数。
* **[!UICONTROL Delivery - Bounce rate]**:与发送的邮件相比，退回的邮件总数。
* **[!UICONTROL Delivery - Unsubscribed rate]**:按收件人列出的退订总数与已传递的消息相比。
* **[!UICONTROL Delivery - Open rate]**:已打开邮件的总数与已传递邮件的数量相比。
* **[!UICONTROL Delivery - Click rate]**:投放中的点击总数与已传递消息的数量相比。

历程流可视化允许您分步查看目标用户档案在整个旅程中的路径。 仅当定位一个旅程时，此选项才可用。 它是自动生成的，无法修改。

![](../assets/dynamic_report_journey_10.png)

**[!UICONTROL Journey summary]**&#x200B;表包含可用于您旅程的数据，例如：

* **[!UICONTROL Entered]**:到达旅程入口事件的总人数。
* **[!UICONTROL Completion rate]**:到达旅程的最终流控制的个人总数与进入旅程的个人总数相比。
* **[!UICONTROL Current]**:当前旅程中的个人总数。
* **[!UICONTROL Failed]**:未成功执行的旅程总数。
* **[!UICONTROL Failed rate]**:未成功执行的旅程总数（与运行旅程总数相比）。

**[!UICONTROL Top events]**&#x200B;表显示了您旅程中最成功的事件和&#x200B;**[!UICONTROL Top action]**，即最成功的操作。

![](../assets/dynamic_report_journey_11.png)

**[!UICONTROL Delivery - Sending summary]**&#x200B;表包含可用于旅程投放的数据，例如：

* **[!UICONTROL Processed/sent]**:已发送邮件的总数。
* **[!UICONTROL Delivered rate]**:与已发送的消息相比，成功传递的消息总数。
* **[!UICONTROL Delivered]**:已成功发送的消息数，与已发送消息的总数有关。
* **[!UICONTROL Bounce + error rate]**:与发送的邮件相比，退回的邮件总数。
* **[!UICONTROL Bounces + errors]**:在投放和自动返回处理期间累积的与已发送消息总数相关的错误总数。

**[!UICONTROL Delivery - Tracking summary]**&#x200B;表包含用于跟踪您的旅程投放成功情况的可用数据，例如：

* **[!UICONTROL Open Rate]**:已打开邮件的百分比。
* **[!UICONTROL Open]**:在投放中打开消息的次数。
* **[!UICONTROL Click trough rate]**:投放中的点击总数与已传递消息的数量相比。
* **[!UICONTROL Click]**:在投放中单击内容的次数。
* **[!UICONTROL Unsubscribe rate]**:按收件人列出的退订与已传递消息的百分比。
* **[!UICONTROL Unsubscribed]**:按收件人列出的退订总数与已传递的消息相比。
