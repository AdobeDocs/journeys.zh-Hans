---
title: 关于事件活动
description: 了解事件活动
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: e353d593ab2710f50a88a3715378c86c2e37b4f6
workflow-type: tm+mt
source-wordcount: '446'
ht-degree: 1%

---


# 关于事件活动 {#concept_rws_1rt_52b}

由技术用户配置的事件 [(请参阅](../event/about-events.md)本页)均显示在面板左侧的第一个类别中。

![](../assets/journey43.png)

始终通过拖放开始活动来事件您的旅程。 您还可以多次单击它。

![](../assets/journey44.png)

单击画布中的事件活动时，将显示活动配置窗格。 默认情况下，当您多次使用相同的事件时，将向画布中的事件名称添加一个递增的编号。 此外，您还可以使用该字 **[!UICONTROL Label]** 段向事件名称添加后缀，该名称将显示在画布中您的活动下。 这在画布中识别事件非常有用，尤其是当您多次使用相同事件时。 它还使得在出现错误时调试更简单，并使报告更易于阅读。

![](../assets/journey33.png)

## 在特定时间内监听事件

位于旅程中的事件活动无限地监听事件。 要仅在某段时间内监听事件，必须为事件配置超时。

然后，该旅程将在超时中指定的时间内侦听事件。 如果在此期间收到事件，则人员将进入事件路径。 否则，客户将进入超时路径，或结束其旅程。

要为事件配置超时，请执行以下步骤：

1. 从事件 **[!UICONTROL Enable the event timeout]** 属性中激活选项。

1. 指定旅程等待事件的时间。

1. 如果要在指定超时内未收到事件时将单个发送到超时路径，请启用该选 **[!UICONTROL Set the timeout path]** 项。 如果未启用此选项，则到达超时后，单个的旅程将结束。

   ![](../assets/event-timeout.png)

在此示例中，旅程向客户发送第一个欢迎推送。 然后，只有顾客在次日进入餐厅，它才会发送餐点折扣促销。 因此，我们为餐厅事件配置了1天超时：

* 如果在欢迎推送后不到1小时收到餐厅事件，则发送餐点折扣推送活动。
* 如果第二天没有收到餐馆事件，则人员将通过超时路径。

请注意，如果要对在事件后定位的多个活动配置超 **[!UICONTROL Wait]** 时，您只需对这些事件中的一个配置超时。

超时将应用于事件后所定位的所有活动 **[!UICONTROL Wait]** 。 如果在指定超时后未收到事件，则这些个人将流入一个超时路径，或结束其旅程。

![](../assets/event-timeout-group.png)
