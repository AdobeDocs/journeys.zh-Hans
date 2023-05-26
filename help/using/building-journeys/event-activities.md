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

技术用户配置的事件(请参阅 [此页面](../event/about-events.md))都会显示在屏幕左侧的面板的第一个类别中。

![](../assets/journey43.png)

始终通过拖放事件活动来开始您的历程。 您还可以双击该图标。

![](../assets/journey44.png)

单击画布中的事件活动时，将显示活动配置窗格。 默认情况下，如果您多次使用同一事件，则会向画布中的事件名称添加一个递增的数字。 此外，您还可以使用 **[!UICONTROL Label]** 字段来添加后缀，该后缀将显示在画布中的活动下方。 这对于识别画布中的事件很有用，尤其是当您多次使用同一事件时。 这样还可以使出错时的调试更容易，并使报表更易于阅读。

![](../assets/journey33.png)

## 在特定时间监听事件

位于历程中的事件活动可无限期地侦听事件。 要仅在特定时间内侦听事件，必须为事件配置超时。

然后，该历程将在超时中指定的时间内侦听事件。 如果在该时间段内收到事件，则该人员将流入事件路径。 否则，客户将流入超时路径或结束其历程。

要为事件配置超时，请执行以下步骤：

1. 激活 **[!UICONTROL Enable the event timeout]** 事件属性中的选项。

1. 指定历程将等待事件的时间量。

1. 如果在指定的超时内未收到任何事件时，要将个人发送到超时路径中，请启用 **[!UICONTROL Set the timeout path]** 选项。 如果未启用此选项，则到达超时时间后，个人历程将结束。

   ![](../assets/event-timeout.png)

在本例中，历程向客户发送了第一个欢迎推送。 然后，仅当顾客在第二天进入餐厅时，它才会发送餐点折扣推送。 因此，我们将restaurant事件配置为1天超时：

* 如果在欢迎推送后不到1天收到餐厅事件，则发送餐饮折扣推送活动。
* 如果在第二天未收到餐厅事件，则该人员将流经超时路径。

请注意，如果要对位于之后的多个事件配置超时， **[!UICONTROL Wait]** 活动，您只需在这些事件之一上配置超时即可。

超时将应用于以下时间之后放置的所有事件： **[!UICONTROL Wait]** 活动。 如果在指定的超时之前未收到任何事件，则个人将流入一个超时路径中，或者将结束其历程。

![](../assets/event-timeout-group.png)
