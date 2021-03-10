---
product: adobe campaign
solution: Journey Orchestration
title: 关于简单用例
description: 深入了解旅程中的简单用例
feature: 历程
role: 业务从业者
level: 中间
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '179'
ht-degree: 11%

---


# 关于简单用例{#concept_grh_vby_w2b}

## 用途{#purpose}

让我们举一个叫马尔顿的酒店品牌的例子。 在他们的酒店里，他们把信标设备放在了所有战略区域附近：大堂、楼层、餐厅、健身房、游泳池等。

在此用例中，我们将了解如何实时向在spa附近的信标旁边走动的人发送个性化信息。

我们只想在此人是女性时发送信息。 必须在数秒内收到消息。

![](../assets/journeyuc1_16.png)

## 先决条件{#prerequisites}

对于我们的用例，我们在Adobe Campaign Standard中设计了一个电子邮件交易消息模板。 我们使用事件事务消息模板。 请参阅此[页](https://docs.adobe.com/content/help/zh-Hans/campaign-standard/using/communication-channels/transactional-messaging/about-transactional-messaging.html)。

Adobe Campaign Standard已配置为发送电子邮件。

当在信标附近检测到事件时，从客户的移动电话发送它们。 您需要设计一个移动应用程序，将事件从客户的手机发送到移动SDK。