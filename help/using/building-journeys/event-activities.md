---
product: adobe campaign
solution: Journey Orchestration
title: 关于事件活动
description: 了解事件活动
feature: 历程
role: 业务从业者
level: 中间
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '450'
ht-degree: 1%

---


# 关于事件活动 {#concept_rws_1rt_52b}

由技术用户配置的事件（请参阅[此页](../event/about-events.md)）均显示在屏幕左侧的调色板的第一类别中。

![](../assets/journey43.png)

始终通过拖放事件活动来开始您的旅程。 您也可以多次单击它。

![](../assets/journey44.png)

单击画布中的事件活动时，将显示活动配置窗格。 默认情况下，当您多次使用相同的事件时，会向画布中的事件名称添加递增的编号。 此外，您还可以使用&#x200B;**[!UICONTROL Label]**&#x200B;字段向事件名称添加后缀，该名称将显示在画布中您的活动下。 这对于在画布中识别事件很有用，尤其是当您多次使用相同事件时。 它还使得在出现错误时调试更简单，并使报告更易于阅读。

![](../assets/journey33.png)

## 在特定时间内侦听事件

位于旅程中的事件活动会无限期地监听事件。 要仅在特定时间内侦听事件，必须为事件配置超时。

然后，该旅程将在超时中指定的时间内侦听事件。 如果在此期间收到事件，则人员将流入事件路径。 否则，客户将进入超时路径，或结束其旅程。

要为事件配置超时，请执行以下步骤：

1. 从事件属性中激活&#x200B;**[!UICONTROL Enable the event timeout]**&#x200B;选项。

1. 指定旅程等待事件的时间。

1. 如果要在指定的超时内未收到事件时将个人发送到超时路径，请启用&#x200B;**[!UICONTROL Set the timeout path]**&#x200B;选项。 如果未启用此选项，则到达超时后，单个的旅程将结束。

   ![](../assets/event-timeout.png)

在此示例中，旅程向客户发送第一个欢迎推送。 然后，只有当顾客在次日进入餐厅时，它才会发送餐费折扣促销。 因此，我们为餐厅事件配置了1天超时：

* 如果在欢迎推送后不到1天内收到餐厅事件，则发送餐点折扣推送活动。
* 如果第二天没有收到餐馆事件，则该人将通过超时路径。

请注意，如果要在&#x200B;**[!UICONTROL Wait]**&#x200B;活动后对定位的多个事件配置超时，则只需在这些事件中配置一个超时。

超时将应用于&#x200B;**[!UICONTROL Wait]**&#x200B;活动之后所有事件。 如果在指定超时后未收到任何事件，则这些个人将流入一个超时路径，或结束其旅程。

![](../assets/event-timeout-group.png)
