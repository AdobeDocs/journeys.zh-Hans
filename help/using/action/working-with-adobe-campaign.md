---
title: 使用 Adobe Campaign
description: 了解Adobe Campaign操作
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
source-git-commit: 2a55139697347ade80959f60bf52bfde39e43eb9
workflow-type: tm+mt
source-wordcount: '282'
ht-degree: 2%

---


# 使用 Adobe Campaign {#using_adobe_campaign_standard}

您可以使用Adobe Campaign Standard的交易消息功能发送电子邮件、推送通知和短信。

[!DNL Journey Orchestration] 附带现成操作，允许与Adobe Campaign Standard建立连接。

必须发布Campaign Standard事务性消息及其关联事件，才能用于Journey Orchestration。 如果事件已发布，但消息未发布，则Journey Orchestration界面中将不显示该消息。 如果消息已发布，但其关联的事件不可用，则消息将显示在Journey Orchestration界面中，但将不可用。

>[!NOTE]
>
>为避免超载Adobe Campaign Standard事务消息传递，建议为 **Campaign Standard集成设** 置上限规则。
>
>阅读Adobe Campaign Standard产品说明，了解有关交易 [消息SLA的更多信息](https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html)。

下面是配置它的步骤：

1. 在列表 **[!UICONTROL Actions]** 中，单击内置的 **[!UICONTROL AdobeCampaignStandard]** 操作。 操作配置窗格将在屏幕右侧打开。

   ![](../assets/actioncampaign.png)

1. 复制您的Adobe Campaign Standard实例URL并将其粘贴到字 **[!UICONTROL URL]** 段中。

1. 单击 **[!UICONTROL Test the instance URL]** 以测试实例的有效性。

   >[!NOTE]
   >
   >此测试验证：
   >
   >* 主机为“.活动.adobe.com”或“.活动-沙箱。adobe.com”,
   >* URL开始与https,
   >* 与此Adobe Campaign Standard实例关联的ORG与Journey Orchestration的ORG相同。


设计旅程时，类别中将提供三个操作： **[!UICONTROL Action]** **[!UICONTROL Email]**、 **[!UICONTROL Push]**(请 **[!UICONTROL SMS]** 参阅使 [用Adobe Campaign操作](../building-journeys/using-adobe-campaign-actions.md))。 **反应事件** 还允许您对消息点击、打开等做出反应。 (请参阅 [反应事件](../building-journeys/reaction-events.md))。

![](../assets/journey58.png)

如果您使用第三方系统发送消息，则需要添加和配置自定义操作。 See [About custom action configuration](../action/about-custom-action-configuration.md).
