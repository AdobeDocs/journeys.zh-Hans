---
product: adobe campaign
solution: Journey Orchestration
title: 使用 Adobe Campaign
description: 了解Adobe Campaign操作
translation-type: tm+mt
source-git-commit: 723c30865a5039bd68a8ac2e45d4c87a760e694d
workflow-type: tm+mt
source-wordcount: '300'
ht-degree: 4%

---


# 使用 Adobe Campaign {#using_adobe_campaign_standard}

您可以使用Adobe Campaign Standard的交易消息功能发送电子邮件、推送通知和短信。

[!DNL Journey Orchestration] 附带现成操作，允许与Adobe Campaign Standard建立连接。

必须发布Campaign Standard事务性消息及其关联事件，才能用于Journey Orchestration。 如果事件已发布，但消息未发布，则Journey Orchestration界面中将不显示该消息。 如果消息已发布，但其关联的事件不可用，则消息将显示在Journey Orchestration界面中，但将不可用。

>[!NOTE]
>
>Adobe Campaign Standard交易消息传递在给定实例的渠道中每小时最大可发送50 000条消息。 为降低过载风险，建议您为Campaign Standard集成设置&#x200B;**上限规则**。
>
>请阅读[Adobe Campaign Standard产品说明](https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html)中有关事务消息SLA的更多信息。

下面是配置它的步骤：

1. 在&#x200B;**[!UICONTROL Actions]**&#x200B;列表中，单击内置&#x200B;**[!UICONTROL AdobeCampaignStandard]**&#x200B;操作。 操作配置窗格将在屏幕右侧打开。

   ![](../assets/actioncampaign.png)

1. 复制您的Adobe Campaign Standard实例URL并将其粘贴到&#x200B;**[!UICONTROL URL]**&#x200B;字段中。

1. 单击&#x200B;**[!UICONTROL Test the instance URL]**&#x200B;以测试实例的有效性。

   >[!NOTE]
   >
   >此测试验证：
   >
   >主机为“.活动.adobe.com”、“.活动-沙箱。adobe.com”或“活动-demo.adobe.com”
   >
   >URL开始与https,
   >
   >与此Adobe Campaign Standard实例关联的ORG与Journey Orchestration的ORG相同。

设计旅程时，**[!UICONTROL Action]**&#x200B;类别中将提供以下三个操作：**[!UICONTROL Email]**、**[!UICONTROL Push]**、**[!UICONTROL SMS]**(请参阅[使用Adobe Campaign操作](../building-journeys/using-adobe-campaign-actions.md))。 **反** 应甚至允许您对消息点击、打开等做出反应。(请参阅[反应事件](../building-journeys/reaction-events.md))。

![](../assets/journey58.png)

如果您使用第三方系统发送消息，则需要添加和配置自定义操作。 请参阅[关于自定义操作配置](../action/about-custom-action-configuration.md)。
