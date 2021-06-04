---
product: adobe campaign
title: 使用 Adobe Campaign
description: 了解Adobe Campaign操作
feature: 历程
role: Business Practitioner
level: Intermediate
exl-id: c7e08542-fde8-4072-a697-42d35d6c58ba
source-git-commit: 04aa7d95c2f12fe03497efe74f2ab8bd1a270b5b
workflow-type: tm+mt
source-wordcount: '736'
ht-degree: 2%

---

# 使用 Adobe Campaign {#using_adobe_campaign}

## 使用Adobe Campaign Standard {#using_adobe_campaign_standard}

您可以使用Adobe Campaign Standard的事务性消息传送功能发送电子邮件、推送通知和短信。

[!DNL Journey Orchestration] 附带一个现成的操作，该操作允许与Adobe Campaign Standard连接。

必须发布Campaign Standard事务型消息及其关联事件，才能在Journey Orchestration中使用。 如果事件已发布但消息未显示，则该事件将不会显示在Journey Orchestration界面中。 如果消息已发布，但未发布其关联事件，则它将在Journey Orchestration界面中可见，但将不可用。

>[!NOTE]
>
>设置Adobe Campaign Standard集成后，将为Adobe Campaign Standard操作自动定义每秒13个调用的上限规则。 这对应于Adobe Campaign Standard事务型消息传递的官方规模。
>
>有关事务性消息传递SLA的更多信息，请参阅[Adobe Campaign Standard产品说明](https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html)。

以下是配置该插件的步骤：

1. 在&#x200B;**[!UICONTROL Actions]**&#x200B;列表中，单击内置的&#x200B;**[!UICONTROL AdobeCampaignStandard]**&#x200B;操作。 操作配置窗格将在屏幕右侧打开。

   ![](../assets/actioncampaign.png)

1. 复制Adobe Campaign Standard实例URL并将其粘贴到&#x200B;**[!UICONTROL URL]**&#x200B;字段中。

1. 单击&#x200B;**[!UICONTROL Test the instance URL]**&#x200B;以测试实例的有效性。

   >[!NOTE]
   >
   >此测试验证：
   >
   >主机为“.campaign.adobe.com”、“.campaign-sandbox.adobe.com”、“.campaign-demo.adobe.com”、“.ats.adobe.com”或“.adls.adobe.com”。
   >
   >URL以https开头，
   >
   >与此Adobe Campaign Standard实例关联的组织与Journey Orchestration的组织相同。

设计历程时，**[!UICONTROL Action]**&#x200B;类别中将提供三个操作：**[!UICONTROL Email]**、**[!UICONTROL Push]**、**[!UICONTROL SMS]**(请参阅[使用Adobe Campaign操作](../building-journeys/using-adobe-campaign-actions.md))。 **Reactions** eventwill还允许您对消息点击、打开等做出反应。（请参阅[Reactions事件](../building-journeys/reaction-events.md)）。

![](../assets/journey58.png)

如果您使用第三方系统来发送消息，则需要添加和配置自定义操作。 请参阅[关于自定义操作配置](../action/about-custom-action-configuration.md)。

## 使用Adobe Campaign v7/v8 {#using_adobe_campaign_v7_v8}

此集成适用于从21.1版本开始的Adobe Campaign Classic v7和Adobe Campaign v8。 它允许您使用Adobe Campaign事务型消息传送功能发送电子邮件、推送通知和短信。

Journey Orchestration实例和Campaign实例之间的连接是在预配时Adobe设置的。

此[部分](../usecase/campaign-v7-v8-use-case.md)中提供了端到端用例。

对于配置的每个操作，历程设计器面板中都提供了一个操作活动。 请参阅此[部分](../building-journeys/using-adobe-campaign-actions.md)。

### 重要说明

* 没有消息限制。 根据我们当前的促销活动SLA，我们将可发送的消息数量限制为50,000/小时。 因此，历程编排仅应用于单一用例（单个事件，而不是区段）。

* 您需要在每个要使用的模板的画布上配置一个操作。 您需要在Journey Orchestration中为要从Adobe Campaign使用的每个模板配置一个操作。

* 我们建议您使用为此集成托管的专用消息中心实例，以避免影响您可能正在进行的任何其他Campaign操作。 营销服务器可以是托管的，也可以是内部部署的。 所需的内部版本为21.1发行候选版本或更高版本。

* 没有验证有效负载或Campaign消息是否正确。

* 您不能将促销活动操作与区段鉴别事件结合使用。

### 先决条件

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

### 配置操作

在Journey Orchestration中，您需要为每个事务型消息配置一个操作。 请执行以下步骤：

1. 创建新操作。 请参阅此[部分](../action/action.md)。
1. 输入名称和描述。
1. 在&#x200B;**Action type**&#x200B;字段中，选择&#x200B;**Adobe Campaign Classic**。
1. 单击&#x200B;**有效负荷**&#x200B;字段，并粘贴与Campaign消息对应的JSON有效负荷示例。 联系Adobe以获取此有效负载。
1. 根据要在历程画布上映射不同字段，将其调整为静态字段或变量字段。 某些字段(例如电子邮件地址和个性化字段(ctx)的渠道参数)，您可能希望定义为用于在历程上下文中映射的变量。
1. 单击&#x200B;**保存**。

![](../assets/accintegration1.png)


