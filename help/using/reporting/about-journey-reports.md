---
title: 关于旅程报告
description: 了解如何构建旅程报告
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
source-git-commit: b5b3c8b6adafaedbdd80db3091300e7a26249a3e
workflow-type: tm+mt
source-wordcount: '732'
ht-degree: 1%

---


# 关于旅程报告 {#concept_rfj_wpt_52b}

>[!NOTE]
>
>投放数据和区段组件仅在您具有Adobe Campaign Standard时才会填充。

本节将向您介绍如何访问和使用报告来衡量您的旅程的有效性。

## 报告界面 {#reporting-interface}

例如，顶部工具栏允许您修改、保存或打印报表。

![](../assets/dynamic_report_toolbar.png)

使用选 **[!UICONTROL Project]** 项卡可以：

* **[!UICONTROL Open]**: 打开以前创建的报告或模板。
* **[!UICONTROL Save As]**: 重复模板，以便能够修改它们。
* **[!UICONTROL Refresh project]**: 根据新数据和对过滤器的更改更新您的报告。
* **[!UICONTROL Download CSV]**: 将报表导出为CSV文件。
* **[!UICONTROL Print]**: 打印您的报告。

该选 **[!UICONTROL Edit]** 项卡允许您：

* **[!UICONTROL Undo]**: 取消您对仪表板的上次操作。
* **[!UICONTROL Redo]**: 取消您对仪表板 **[!UICONTROL Undo]** 的上次操作。
* **[!UICONTROL Clear all]**: 删除仪表板上的每个面板。

通过 **[!UICONTROL Insert]** 该表，您可以通过向仪表板添加图形和表来自定义报表：

* **[!UICONTROL New Blank Panel]**: 将新的空白面板添加到仪表板。
* **[!UICONTROL New Freeform]**: 为仪表板添加新的自由形式表。
* **[!UICONTROL New Line]**: 为仪表板添加新的折线图。
* **[!UICONTROL New Bar]**: 为仪表板添加新条形图。

使用左侧选项卡，您可以根据需要构建报表和筛选数据。

![](../assets/dynamic_report_interface.png)

这些选项卡允许您访问以下项目：

* **[!UICONTROL Panels]**: 在报表中添加空白面板或自由形式，以开始过滤数据。 For more on this, refer to the [Adding panels](../reporting/creating-your-journey-reports.md#adding-panels) section
* **[!UICONTROL Visualizations]**: 拖放一系列可视化项目，为报表提供图形维度。 For more on this, refer to the [Adding visualizations](../reporting/creating-your-journey-reports.md#adding-visualizations) section.
* **[!UICONTROL Components]**: 使用不同的维度、指标、细分和时间段自定义您的报表。 For more on this, refer to the [Adding components](../reporting/creating-your-journey-reports.md#adding-components) section.

## 旅程摘要模板 {#ootb-template}

报告分为两个类别: 现成的模板和自定义报告。
开箱即用的模板可为您 **[!UICONTROL Journey summary]**&#x200B;明确视图最重要的跟踪数据。

![](../assets/dynamic_report_journey_8.png)

每个表由摘要编号和图表表示。 您可以更改详细信息在其各自的可视化设置中的显示方式。

报表顶部提供以下KPI:

* **[!UICONTROL Journey - Entered]**: 到达旅程入口事件的个人总数。
* **[!UICONTROL Journey - Completion rate]**: 到达旅程结束的个人总数（或者，如果某个人不符合任何条件）与进入旅程的个人总数相比。
* **[!UICONTROL Journey - Current]**: 当前旅程中的个人总数。
* **[!UICONTROL Journey - Failed rate]**: 未成功执行的旅程总数与run旅程的总数。
* **[!UICONTROL Delivery - Messages sent]**: 已发送邮件总数。
* **[!UICONTROL Delivery rate]**: 与已发送的消息相比，成功传送的消息总数。
* **[!UICONTROL Delivery - Bounce rate]**: 与发送的邮件相比，弹回的邮件总数。
* **[!UICONTROL Delivery - Unsubscribed rate]**: 按收件人划分的退订总数与已传递的消息相比。
* **[!UICONTROL Delivery - Open rate]**: 已打开邮件的总数与已传递邮件的数量相比。
* **[!UICONTROL Delivery - Click rate]**: 投放中的点击总数与已传递消息的数量相比。

旅程流可视化允许您分步查看目标用户档案在旅程中的路径。 仅当定位一个旅程时，此选项才可用。 它是自动生成的，无法修改。

![](../assets/dynamic_report_journey_10.png)

该 **[!UICONTROL Journey summary]** 表包含可用于旅程的数据，如：

* **[!UICONTROL Entered]**: 到达旅程入口事件的个人总数。
* **[!UICONTROL Completion rate]**: 到达旅程的最终流控制的个人总数与进入旅程的个人总数之比。
* **[!UICONTROL Current]**: 当前旅程中的个人总数。
* **[!UICONTROL Failed]**: 未成功执行的旅程总数。
* **[!UICONTROL Failed rate]**: 未成功执行的旅程总数与run旅程的总数。

该 **[!UICONTROL Top events]** 表显示了您旅程中最成 **[!UICONTROL Top action]**&#x200B;功的事件和最成功的操作。

![](../assets/dynamic_report_journey_11.png)

该 **[!UICONTROL Delivery - Sending summary]** 表包含可用于旅程投放的数据，如：

* **[!UICONTROL Processed/sent]**: 已发送邮件总数。
* **[!UICONTROL Delivered rate]**: 与已发送的消息相比，成功传送的消息总数。
* **[!UICONTROL Delivered]**: 已成功发送的消息数，与已发送消息的总数有关。
* **[!UICONTROL Bounce + error rate]**: 与发送的邮件相比，弹回的邮件总数。
* **[!UICONTROL Bounces + errors]**: 在投放和自动返回处理期间累积的与已发送消息总数相关的错误总数。

该 **[!UICONTROL Delivery - Tracking summary]** 表包含跟踪您旅程投放成功情况的可用数据，如：

* **[!UICONTROL Open Rate]**: 已打开邮件的百分比。
* **[!UICONTROL Open]**: 在投放中打开消息的次数。
* **[!UICONTROL Click trough rate]**: 投放中的点击总数与已传递消息的数量相比。
* **[!UICONTROL Click]**: 在投放中单击内容的次数。
* **[!UICONTROL Unsubscribe rate]**: 按收件人划分的退订与已传送消息的百分比。
* **[!UICONTROL Unsubscribed]**: 按收件人划分的退订总数与已传递的消息相比。
