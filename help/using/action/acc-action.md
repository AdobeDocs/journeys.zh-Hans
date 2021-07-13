---
product: adobe campaign
title: 关于Campaign v7/v8集成
description: 了解Campaign v7/v8集成
feature: 历程
role: User
level: Intermediate
exl-id: 4b321b63-c624-4c2a-ae92-f9a2a95688d4
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '443'
ht-degree: 7%

---

# 使用 Adobe Campaign v7/v8 {#integrating-with-adobe-campaign-classic}

此集成适用于从21.1版本开始的Adobe Campaign Classic v7和Adobe Campaign v8。 它允许您使用Adobe Campaign事务型消息传送功能发送电子邮件、推送通知和短信。

Journey Orchestration 实例和 Campaign 实例之间的连接是在预配置时通过 Adobe 来设置的。

此[部分](../usecase/campaign-classic-use-case.md)中提供了端到端用例。

对于配置的每个操作，历程设计器面板中都提供了一个操作活动。 请参阅此[部分](../building-journeys/using-adobe-campaign-classic.md)。

## 重要说明

* 没有消息限制。 根据我们当前的促销活动SLA，我们将可发送的消息数量限制为50,000/小时。 因此，历程编排仅应用于单一用例（单个事件，而不是区段）。

* 您需要在每个要使用的模板的画布上配置一个操作。 您需要在Journey Orchestration中为要从Adobe Campaign使用的每个模板配置一个操作。

* 我们建议您使用为此集成托管的专用消息中心实例，以避免影响您可能正在进行的任何其他Campaign操作。 营销服务器可以是托管的，也可以是内部部署的。 所需的内部版本为21.1发行候选版本或更高版本。

* 没有验证有效负载或Campaign消息是否正确。

* 您不能将促销活动操作与区段鉴别事件结合使用。

## 先决条件

在Campaign中，您需要创建并发布事务型消息及其关联事件。 请参阅[Adobe Campaign文档](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/introduction/about-transactional-messaging.html#transactional-messaging)。

您可以按照以下模式构建与每个消息对应的JSON有效负载。 然后，在Journey Orchestration中配置操作时，您将粘贴此有效负载（请参阅下文）

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

* **渠道**:为营销活动事务型模板定义的渠道
* **eventType**:营销活动事件的内部名称
* **ctx**:变量。

## 配置操作

在Journey Orchestration中，您需要为每个事务型消息配置一个操作。 请执行以下步骤：

1. 创建新操作。 请参阅此[部分](../action/action.md)。
1. 输入名称和描述。
1. 在&#x200B;**Action type**&#x200B;字段中，选择&#x200B;**Adobe Campaign Classic**。
1. 单击&#x200B;**有效负荷**&#x200B;字段，并粘贴与Campaign消息对应的JSON有效负荷示例。 联系Adobe以获取此有效负载。
1. 根据要在历程画布上映射不同字段，将其调整为静态字段或变量字段。 某些字段(例如电子邮件地址和个性化字段(ctx)的渠道参数)，您可能希望定义为用于在历程上下文中映射的变量。
1. 单击&#x200B;**保存**。

![](../assets/accintegration1.png)


