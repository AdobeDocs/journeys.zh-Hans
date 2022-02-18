---
product: adobe campaign
solution: Journey Orchestration
title: 使用 Campaign v7/v8 发送消息
description: 使用 Campaign v7/v8 发送消息
source-git-commit: 2195ee3863b38ead504eb6785ceb3c37735fade9
workflow-type: tm+mt
source-wordcount: '394'
ht-degree: 6%

---

# 使用 Campaign v7/v8 发送消息 {#campaign-classic-use-case}

此用例介绍使用与Adobe Campaign Classic v7和Adobe Campaign v8的集成发送电子邮件所需的所有步骤。

我们将首先在Campaign中创建事务型电子邮件模板。 然后，在Journey Orchestration中，我们将创建事件、操作并设计历程。

要了解有关Campaign集成的更多信息，请参阅以下页面：

* [创建Campaign操作](../action/acc-action.md)
* [在历程中使用操作](../building-journeys/using-adobe-campaign-classic.md).

**Adobe Campaign**

需要为此集成配置您的Campaign实例。 需要配置事务型消息传递功能。

1. 登录到Campaign控制实例。

1. 在 **管理** > **平台** > **枚举**，选择 **事件类型** (eventType)枚举。 创建新事件类型（在我们的示例中为“journey-event”）。 以后编写JSON文件时，必须使用事件类型的内部名称。

   ![](../assets/accintegration-uc-1.png)

1. 断开连接并重新连接到实例，以便创建生效。

1. 在 **消息中心** > **事务型消息模板**，则根据之前创建的事件类型创建新电子邮件模板。

   ![](../assets/accintegration-uc-2.png)

1. 设计模板。 在此示例中，我们对用户档案的名字和订单号进行个性化设置。 名字在Adobe Experience Platform数据源中，订单号是我们Journey Orchestration事件中的一个字段。 确保在Campaign中使用正确的字段名称。

   ![](../assets/accintegration-uc-3.png)

1. 发布事务型模板。

   ![](../assets/accintegration-uc-4.png)

1. 现在，您需要编写与模板对应的JSON有效负载。

```
{
     "channel": "email",
     "eventType": "journey-event",
     "email": "Email address",
     "ctx": {
          "firstName": "First name", "purchaseOrderNumber": "Purchase order number"
     }
}
```

* 对于渠道，您需要键入“email”。
* 对于eventType，使用之前创建的事件类型的内部名称。
* 电子邮件地址将为变量，因此您可以键入任何标签。
* 在ctx下，个性化字段也是变量。

**Journey Orchestration**

1. 首先，您需要创建事件。 确保包含“purchaseOrderNumber”字段。

   ![](../assets/accintegration-uc-5.png)

1. 然后，您需要在Journey Orchestration中创建与营销活动模板对应的操作。 在 **操作类型** 下拉列表，选择 **Adobe Campaign Classic**.

   ![](../assets/accintegration-uc-6.png)

1. 单击 **有效负荷字段** 并粘贴之前创建的JSON。

   ![](../assets/accintegration-uc-7.png)

1. 对于电子邮件地址和两个个性化字段，请更改 **常量** to **变量**.

   ![](../assets/accintegration-uc-8.png)

1. 现在，创建新历程并从之前创建的事件开始。

   ![](../assets/accintegration-uc-9.png)

1. 添加操作，并将每个字段映射到Journey Orchestration中的正确字段。

   ![](../assets/accintegration-uc-10.png)

1. 添加 **结束** 活动并测试您的历程。

   ![](../assets/accintegration-uc-11.png)

1. 您现在可以发布历程。
