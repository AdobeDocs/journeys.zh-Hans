---
product: adobe campaign
title: 关于简单用例
description: 详细了解历程简单用例
feature: Journeys
role: User
level: Intermediate
exl-id: 11858c7a-fdb3-43a4-af28-0d5c23fa2468
product_v2:
  - id: cf67d108-ecf9-4fde-af49-3a3c39083bc8
    internal-label: Journey Orchestration
feature_v2:
  - id: 7de3230f-9523-5ba5-8d5c-2313288b27ef
    internal-label: Journeys
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
source-git-commit: 255cd6677e7c9ebff63ea9a1028a042c19e63ecc
workflow-type: tm+mt
source-wordcount: '236'
ht-degree: 36%
---
# 关于简单用例{#concept_grh_vby_w2b}


>[!CAUTION]
>
>**希望了解 Adobe Journey Optimizer**？ 请单击[此处](https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer/using/ajo-home){target="_blank"}获取 Journey Optimizer 文档。
>
>
>_本文档参考已被 Journey Optimizer 取代的旧版 Journey Orchestration 资料。 如果您对访问 Journey Orchestration 或 Journey Optimizer 有任何疑问，请联系帐户团队。_


## 用途 {#purpose}

以一个叫马尔顿的酒店品牌为例。 在酒店里，他们在所有战略区域附近都放置了信标设备：大厅、地板、餐厅、健身房、游泳池等。

在此使用案例中，我们将了解如何实时向位于spa附近信标旁边的人发送个性化消息。

我们只想在当事人是妇女的情况下发送消息。 必须在秒内收到消息。

![](../assets/journeyuc1_16.png)

## 先决条件 {#prerequisites}

对于我们的用例，我们在Adobe Campaign Standard中设计了一个电子邮件事务型消息传递模板。 我们正在使用事件事务性消息模板。 请参见[此页面](https://experienceleague.adobe.com/docs/campaign-standard/using/communication-channels/transactional-messaging/getting-started-with-transactional-msg.html?lang=zh-Hans)。

Adobe Campaign Standard配置为发送电子邮件。

当在信标附近检测到事件时，将从客户的手机发送事件。 您需要设计一个移动应用程序，以将事件从客户的手机发送到Mobile SDK。
