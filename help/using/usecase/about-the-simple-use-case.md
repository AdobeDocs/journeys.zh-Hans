---
product: adobe campaign
title: 关于简单用例
description: 进一步了解历程简单用例
feature: 历程
role: User
level: Intermediate
exl-id: 11858c7a-fdb3-43a4-af28-0d5c23fa2468
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '174'
ht-degree: 12%

---

# 关于简单用例{#concept_grh_vby_w2b}

## 用途 {#purpose}

我们以一个叫马尔顿的酒店品牌为例。 在他们的酒店里，他们把信标设备定位在所有战略区域附近：大堂、地板、餐厅、健身房、游泳池等

在此用例中，我们将了解如何实时向位于spa附近的信标旁边的人员发送个性化消息。

我们只想在人是女人时发送信息。 必须在数秒内收到消息。

![](../assets/journeyuc1_16.png)

## 先决条件 {#prerequisites}

对于我们的用例，我们在Adobe Campaign Standard中设计了一个电子邮件事务型消息传递模板。 我们使用的是事件事务型消息模板。 请参见此[页面](https://experienceleague.adobe.com/docs/campaign-standard/using/communication-channels/transactional-messaging/getting-started-with-transactional-msg.html?lang=zh-Hans)。

Adobe Campaign Standard配置为发送电子邮件。

当在信标附近检测到客户的手机事件时，会从他们的手机发送事件。 您需要设计一个移动应用程序，以将事件从客户的手机发送到Mobile SDK。
