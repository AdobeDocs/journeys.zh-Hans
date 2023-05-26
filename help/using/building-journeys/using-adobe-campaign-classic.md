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
ht-degree: 26%

---

# 使用 Adobe Campaign v7/v8 {#using_campaign_classic}

如果您使用 Adobe Campaign v7 或 v8，则可以利用集成。它允许您使用Adobe Campaign事务性消息传递功能发送电子邮件、推送通知和短信。

Journey Orchestration 实例和 Campaign 实例之间的连接是在配置时通过 Adobe 来设置的。联系Adobe。

要使此功能正常工作，您需要配置专用操作。 请参阅此[章节](../action/acc-action.md)。

本中介绍了端到端用例 [部分](../usecase/campaign-classic-use-case.md).

1. 设计您的历程，从事件开始。 请参阅此[部分](../building-journeys/journey.md)。
1. 在 **操作** 的部分，选择一个Campaign操作并将其添加到您的旅程。
1. 在 **操作参数**，则将显示消息有效负载中预期的所有字段。 您需要从事件或数据源中将每个字段映射到要使用的字段。 这类似于自定义操作。 请参阅此[章节](../building-journeys/using-custom-actions.md)。

![](../assets/accintegration2.png)
