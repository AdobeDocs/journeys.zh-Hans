---
product: adobe campaign
title: 关于事件活动
description: 了解事件活动
feature: Journeys
role: User
level: Intermediate
exl-id: 3a4ff8b1-bbe7-47c8-9fba-defe4b1d5299
source-git-commit: 5b09ed456b6a9645dbb7897481317d3904e29d31
workflow-type: tm+mt
source-wordcount: '446'
ht-degree: 1%

---

# 关于事件活动 {#concept_rws_1rt_52b}

技术用户配置的事件(请参阅 [本页](../event/about-events.md))都显示在屏幕左侧面板的第一个类别中。

![](../assets/journey43.png)

始终通过拖放事件活动来开始您的历程。 您还可以双击该页面。

![](../assets/journey44.png)

在画布中单击事件活动时，将显示活动配置窗格。 默认情况下，当您多次使用同一事件时，画布中的事件名称中会添加一个递增的数字。 此外，您还可以使用 **[!UICONTROL Label]** 字段，为将在画布中活动下方显示的事件名称添加后缀。 在画布中识别事件时，这非常有用，尤其是当您多次使用同一事件时。 它还可以在出错时更轻松地进行调试，并且还可以更轻松地阅读报表。

![](../assets/journey33.png)

## 在特定时间内侦听事件

An event activity positioned in the journey listens to events indefinitely. 要仅在特定时间内侦听事件，必须为该事件配置超时。

The journey will then listen to the event during the time specified in the timeout. If an event is received during that period, the person will flow in the event path. If not, the customer will either flow into a timeout path, or end their journey.

要为事件配置超时，请执行以下步骤：

1. 激活 **[!UICONTROL Enable the event timeout]** 选项。

1. 指定历程将等待事件的时长。

1. 如果要在指定的超时内未收到任何事件时将个人发送到超时路径，请启用 **[!UICONTROL Set the timeout path]** 选项。 If this option is not enabled, the journey will end for the individual once the timeout is reached.

   ![](../assets/event-timeout.png)

在此示例中，历程向客户发送第一个欢迎推送。 然后，仅当客户在次日进入餐厅时，才会发送餐饮折扣推送。 因此，我们为餐厅事件配置了1天的超时：

* If the restaurant event is received less than 1 day after the welcome push, the meal discount push activity is sent.
* If no restaurant event is received within the next day, the person flows through the timeout path.

Note that if you want to configure a timeout on multiple events positioned after a **[!UICONTROL Wait]** activity, you need to configure the timeout on one of these events only.

The timeout will apply to all the events positioned after the **[!UICONTROL Wait]** activity. 如果在指定的超时前未收到任何事件，则这些个人将流入一个超时路径，或结束其历程。

![](../assets/event-timeout-group.png)
