---
product: adobe campaign
solution: Journey Orchestration
title: 使用Adobe Campaign v7/v8操作
description: 了解Adobe Campaign v7/v8操作
feature: Journeys
role: User
level: Intermediate
exl-id: 4e59a256-d494-4407-a0a8-a2523eb1084e
source-git-commit: a9a129b1949d64c4a412d3ea4002b32e3563ea96
workflow-type: tm+mt
source-wordcount: '164'
ht-degree: 17%

---

# 使用 Adobe Campaign v7/v8 {#using_campaign_classic}

如果您使用 Adobe Campaign v7 或 v8，则可以利用集成。利用此功能，可使用Adobe Campaign事务性消息传送功能发送电子邮件、推送通知和短信。

在预配时，Journey Orchestration实例和Campaign实例之间的连接通过Adobe进行设置。 联系Adobe。

要使此功能正常工作，您需要配置专用操作。 请参阅此[章节](../action/acc-action.md)。

此[部分](../usecase/campaign-classic-use-case.md)中介绍了端到端用例。

1. 设计您的历程，从事件开始。 请参阅此[部分](../building-journeys/journey.md)。
1. 在调色板的&#x200B;**操作**&#x200B;部分中，选择一个Campaign操作并将其添加到您的历程。
1. 在&#x200B;**操作参数**&#x200B;中，将显示消息有效负载中预期的所有字段。 您需要将每个字段映射到要使用的字段（从事件或从数据源）。 这与自定义操作类似。 请参阅此[章节](../building-journeys/using-custom-actions.md)。

![](../assets/accintegration2.png)
