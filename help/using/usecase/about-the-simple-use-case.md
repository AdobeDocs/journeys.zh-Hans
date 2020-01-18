---
title: 关于简单的用例
description: 在旅程中了解更多简单的用例
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
source-git-commit: 54b54a64ad2822eec96008ac4a2e16c208a4a3ab

---


# 关于简单的用例{#concept_grh_vby_w2b}

## 用途 {#purpose}

我们以一个叫马尔顿的酒店品牌为例， 在他们的酒店里，他们把信标设备放在了所有战略区域附近：大堂、楼板、餐厅、健身房、游泳池等。

在此使用案例中，我们将了解如何向在spa附近的信标旁边走动的人实时发送个性化信息。

我们只想在此人是女性时发送信息。 消息必须在数秒内收到。

![](../assets/journeyuc1_16.png)

## 先决条件 {#prerequisites}

对于我们的用例，我们在Adobe Campaign standard中设计了一个电子邮件交易消息模板。 我们使用的是活动事务消息传递模板。 Refer to this [page](https://docs.adobe.com/content/help/en/campaign-standard/using/communication-channels/transactional-messaging/about-transactional-messaging.html).

Adobe Campaign standard配置为发送电子邮件。

当在信标附近检测到事件时，从客户的移动电话发送事件。 您需要设计移动应用程序，将事件从客户的手机发送到移动SDK。