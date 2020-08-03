---
title: 关于简单用例
description: 在旅程中进一步了解简单的用例
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
workflow-type: tm+mt
source-wordcount: '175'
ht-degree: 12%

---


# 关于简单用例{#concept_grh_vby_w2b}

## 用途 {#purpose}

我们以一个叫马尔顿的酒店品牌为例。 在他们的酒店里，他们把信标设备放在了所有战略区域附近： 大堂、地板、餐厅、健身房、游泳池等。

在此用例中，我们将了解如何实时向在spa附近的信标旁边走动的人发送个性化信息。

我们只想在人是女人时发送信息。 消息必须在数秒内收到。

![](../assets/journeyuc1_16.png)

## 先决条件{#prerequisites}

为了我们的用例，我们设计了一个Adobe Campaign Standard的电子邮件交易消息模板。 我们使用事件事务消息模板。 Refer to this [page](https://docs.adobe.com/content/help/zh-Hans/campaign-standard/using/communication-channels/transactional-messaging/about-transactional-messaging.html).

Adobe Campaign Standard配置为发送电子邮件。

事件在信标附近被检测到时从客户的移动电话发送。 您需要设计一个移动应用程序，将事件从客户的手机发送到移动SDK。