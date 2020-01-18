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

---


# 关于旅程报告 {#concept_rfj_wpt_52b}

>[!NOTE]
>
>只有在您拥有Adobe Campaign standard的情况下，才会填充交付数据和区段组件。

本节将向您介绍如何访问和使用报告来衡量您的旅程的有效性。

## 报告界面 {#reporting-interface}

例如，顶部工具栏允许您修改、保存或打印报表。

![](../assets/dynamic_report_toolbar.png)

使用该选 **[!UICONTROL Project]**项卡可以：

* **[!UICONTROL Open]**:打开先前创建的报告或模板。
* **[!UICONTROL Save As]**:复制模板以便能够修改它们。
* **[!UICONTROL Refresh project]**:根据新数据和对筛选器的更改更新您的报告。
* **[!UICONTROL Download CSV]**:将报告导出为CSV文件。
* **[!UICONTROL Print]**:打印您的报告。

该选 **[!UICONTROL Edit]**项卡允许您：

* **[!UICONTROL Undo]**:取消您在功能板上的上次操作。
* **[!UICONTROL Redo]**:取消功能板**[!UICONTROL Undo]** 上的上次操作。
* **[!UICONTROL Clear all]**:删除功能板上的每个面板。

通过 **[!UICONTROL Insert]**此表格，您可以通过向功能板添加图形和表格来自定义报表：

* **[!UICONTROL New Blank Panel]**:将新的空白面板添加到功能板。
* **[!UICONTROL New Freeform]**:将新的自由格式表添加到功能板。
* **[!UICONTROL New Line]**:将新的折线图添加到功能板。
* **[!UICONTROL New Bar]**:将新条形图添加到功能板。

使用左侧选项卡，您可以根据需要构建报表和筛选数据。

![](../assets/dynamic_report_interface.png)

这些选项卡允许您访问以下项目：

* **[!UICONTROL Panels]**:在报表中添加空白面板或自由格式，开始筛选数据。 有关详细信息，请参阅添加面[板部分](../reporting/creating-your-journey-reports.md#adding-panels)。
* **[!UICONTROL Visualizations]**:拖放一系列可视化项目，为报表提供图形维度。 有关此内容的详细信息，请参阅添[加可视化](../reporting/creating-your-journey-reports.md#adding-visualizations)部分。
* **[!UICONTROL Components]**:使用不同的维度、指标、细分和时间段自定义您的报表。 有关详细信息，请参阅添[加组件](../reporting/creating-your-journey-reports.md#adding-components)。

## 旅程摘要模板 {#ootb-template}

报告分为两类：现成的模板和自定义报告。
开箱即用的模板可让您清 **[!UICONTROL Journey summary]**晰地查看最重要的跟踪数据。

![](../assets/dynamic_report_journey_8.png)

每个表由摘要编号和图表表示。 您可以更改详细信息在各自的可视化设置中的显示方式。

报表顶部提供以下KPI:

* **[!UICONTROL Journey - Entered]**:到达旅程进入事件的总人数。
* **[!UICONTROL Journey - Completion rate]**:到达旅程结束的个人总数（或者，如果某个人不符合任何条件）与进入旅程的个人总数相比较。
* **[!UICONTROL Journey - Current]**:当前旅程中的个人总数。
* **[!UICONTROL Journey - Failed rate]**:未成功执行的旅程总数与运行的旅程总数相比。
* **[!UICONTROL Delivery - Messages sent]**:发送的消息总数。
* **[!UICONTROL Delivery rate]**:与发送的消息相比，成功传送的消息总数。
* **[!UICONTROL Delivery - Bounce rate]**:弹回的消息总数与发送的消息相比。
* **[!UICONTROL Delivery - Unsubscribed rate]**:与已交付消息相比，收件人取消订阅的总数。
* **[!UICONTROL Delivery - Open rate]**:已打开消息的总数与已传送消息的数量相比。
* **[!UICONTROL Delivery - Click rate]**:与已传送消息的数量相比，传送中的点击总数。

旅程流可视化允许您逐步查看目标配置文件在旅程中的路径。 仅当定位一个旅程时，此选项才可用。 它是自动生成的，无法修改。

![](../assets/dynamic_report_journey_10.png)

该 **[!UICONTROL Journey summary]**表包含可用于旅程的数据，如：

* **[!UICONTROL Entered]**:到达旅程进入事件的总人数。
* **[!UICONTROL Completion rate]**:到达旅程的最终流控制的个人总数与进入旅程的个人总数相比。
* **[!UICONTROL Current]**:当前旅程中的个人总数。
* **[!UICONTROL Failed]**:未成功执行的旅程总数。
* **[!UICONTROL Failed rate]**:未成功执行的旅程总数与运行的旅程总数相比。

该 **[!UICONTROL Top events]**表显示了您旅程中最成功**[!UICONTROL Top action]**&#x200B;的事件和最成功的操作。

![](../assets/dynamic_report_journey_11.png)

该 **[!UICONTROL Delivery - Sending summary]**表包含可用于旅程交付的数据，例如：

* **[!UICONTROL Processed/sent]**:发送的消息总数。
* **[!UICONTROL Delivered rate]**:与发送的消息相比，成功传送的消息总数。
* **[!UICONTROL Delivered]**:已成功发送的消息数，与已发送消息的总数有关。
* **[!UICONTROL Bounce + error rate]**:弹回的消息总数与发送的消息相比。
* **[!UICONTROL Bounces + errors]**:在发送和自动返回处理期间累积的与已发送消息总数有关的错误总数。

该表 **[!UICONTROL Delivery - Tracking summary]**包含跟踪旅程交付成功情况的可用数据，例如：

* **[!UICONTROL Open Rate]**:已打开消息的百分比。
* **[!UICONTROL Open]**:邮件在分发中打开的次数。
* **[!UICONTROL Click trough rate]**:与已传送消息的数量相比，传送中的点击总数。
* **[!UICONTROL Click]**:内容在分发中的点击次数。
* **[!UICONTROL Unsubscribe rate]**:收件人取消订阅与已交付消息的百分比。
* **[!UICONTROL Unsubscribed]**:与已交付消息相比，收件人取消订阅的总数。
