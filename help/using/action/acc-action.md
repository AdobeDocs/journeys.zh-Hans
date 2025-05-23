---
product: adobe campaign
title: 关于Campaign v7/v8集成
description: 了解Campaign v7/v8集成
feature: Journeys
role: User
level: Intermediate
exl-id: 4b321b63-c624-4c2a-ae92-f9a2a95688d4
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '482'
ht-degree: 12%

---

# 使用 Adobe Campaign v7/v8 {#integrating-with-adobe-campaign-classic}


>[!CAUTION]
>
>**正在查找Adobe Journey Optimizer**？ 单击[此处](https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer/using/ajo-home){target="_blank"}获取Journey Optimizer文档。
>
>
>_本文档参考已被Journey Optimizer替换的旧版Journey Orchestration资料。 如果您对访问Journey Orchestration或Journey Optimizer有任何疑问，请联系您的帐户团队。_


此集成适用于Adobe Campaign Classic v7（从21.1版本开始）和Adobe Campaign v8。 通过它，可使用 Adobe Campaign 交易型消息传递功能发送电子邮件、推送通知和短信。

Journey Orchestration 实例和 Campaign 实例之间的连接是在配置时通过 Adobe 来设置的。

此[部分](../usecase/campaign-classic-use-case.md)中介绍了端到端用例。

对于所配置的每个操作，历程设计器面板中都提供了操作活动。 请参阅此[章节](../building-journeys/using-adobe-campaign-classic.md)。

## 重要说明

* 消息不受限制。 根据我们当前的Campaign SLA，我们会将可发送超过50,000条/小时的消息数量限制在50,000条/小时。 因此，历程编排应仅用于单一用例（单个事件，而不是区段）。

* 您需要在要使用的每个模板的画布上配置一个操作。 您需要在Journey Orchestration中为要从Adobe Campaign使用的每个模板配置一个操作。

* 我们建议您使用为此集成托管的专用消息中心实例，以避免影响您可能正在执行的任何其他Campaign操作。 营销服务器可以托管，也可以内部部署。 所需的版本是21.1版本候选版本或更高版本。

* 无法验证有效负载或Campaign消息是否正确。

* 营销活动操作不能与区段资格事件一起使用。

## 先决条件

在Campaign中，您需要创建和发布事务型消息及其关联的事件。 请参阅[Adobe Campaign文档](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/introduction/about-transactional-messaging.html?lang=zh-Hans#transactional-messaging)。

您可以按照以下模式构建与每条消息对应的JSON有效负载。 然后，在Journey Orchestration中配置操作时，您会粘贴此有效负载（请参阅下文）

示例如下：

```
{
    "channel": "email",
    "eventType": "welcome",
    "email": "example@adobe.com",
    "ctx": {
        "firstName": "John"
    }
}
```

* **渠道**：为营销活动事务模板定义的渠道
* **eventType**： Campaign事件的内部名称
* **ctx**：变量基于您在消息中的个性化设置。

## 配置操作

在Journey Orchestration中，您需要为每个事务性消息配置一个操作。 执行以下步骤：

1. 创建新操作。 请参阅此[章节](../action/action.md)。
1. 输入名称和说明。
1. 在&#x200B;**操作类型**&#x200B;字段中，选择&#x200B;**Adobe Campaign Classic**。
1. 单击&#x200B;**有效负载**&#x200B;字段，并粘贴与营销活动消息对应的JSON有效负载示例。 联系Adobe以获取此有效负载。
1. 根据您想要在历程画布上映射这些字段，可以将这些字段调整为静态或变量。 某些字段，例如电子邮件地址和个性化字段(ctx)的渠道参数，您可能希望定义为要在历程上下文中映射的变量。
1. 单击&#x200B;**保存**。

![](../assets/accintegration1.png)


