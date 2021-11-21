---
product: adobe campaign
title: 使用 Adobe Campaign
description: 了解Adobe Campaign操作
feature: Journeys
role: User
level: Intermediate
exl-id: c7e08542-fde8-4072-a697-42d35d6c58ba
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '302'
ht-degree: 4%

---

# 使用 Adobe Campaign Standard {#using_adobe_campaign_standard}

您可以使用Adobe Campaign Standard的事务性消息传送功能发送电子邮件、推送通知和短信。

[!DNL Journey Orchestration] 附带一个现成的操作，该操作允许与Adobe Campaign Standard连接。

必须发布Campaign Standard事务型消息及其关联事件，才能在Journey Orchestration中使用。 如果事件已发布但消息未显示，则该事件将不会显示在Journey Orchestration界面中。 如果消息已发布，但未发布其关联事件，则它将在Journey Orchestration界面中可见，但将不可用。

>[!NOTE]
>
>设置Adobe Campaign Standard集成后，将为Adobe Campaign Standard操作自动定义每秒13个调用的上限规则。 这对应于Adobe Campaign Standard事务型消息传递的官方规模。
>
>有关事务性消息传递SLA的更多信息，请参阅 [Adobe Campaign Standard产品描述](https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html).

以下是配置该插件的步骤：

1. 从 **[!UICONTROL Actions]** 列表，单击内置 **[!UICONTROL AdobeCampaignStandard]** 操作。 操作配置窗格将在屏幕右侧打开。

   ![](../assets/actioncampaign.png)

1. 复制Adobe Campaign Standard实例URL并将其粘贴到 **[!UICONTROL URL]** 字段。

1. 单击 **[!UICONTROL Test the instance URL]** 来测试实例的有效性。

   >[!NOTE]
   >
   >此测试验证：
   >
   >主机为“.campaign.adobe.com”、“.campaign-sandbox.adobe.com”、“.campaign-demo.adobe.com”、“.ats.adobe.com”或“.adls.adobe.com”。
   >
   >URL以https开头，
   >
   >与此Adobe Campaign Standard实例关联的组织与Journey Orchestration的组织相同。

设计历程时，可在 **[!UICONTROL Action]** 类别： **[!UICONTROL Email]**, **[!UICONTROL Push]**, **[!UICONTROL SMS]** (请参阅 [使用Adobe Campaign操作](../building-journeys/using-adobe-campaign-actions.md))。 **反应事件** 还允许您对消息的点击、打开等做出反应。 (请参阅 [反应事件](../building-journeys/reaction-events.md))。

![](../assets/journey58.png)

如果您使用第三方系统来发送消息，则需要添加和配置自定义操作。 请参阅 [关于自定义操作配置](../action/about-custom-action-configuration.md).
