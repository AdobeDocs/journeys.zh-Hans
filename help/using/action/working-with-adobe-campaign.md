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
source-git-commit: 1e7765352ec91be50b51633927ab038d3492b71a
workflow-type: tm+mt
source-wordcount: '123'
ht-degree: 8%

---


# 使用 Adobe Campaign {#using_adobe_campaign_standard}

您可以使用Adobe Campaign标准的交易消息功能发送电子邮件、推送通知和短信。

[!DNL Journey Orchestration] 附带现成的操作，允许连接到Adobe Campaign标准。 下面是配置它的步骤：

1. 在列表 **[!UICONTROL Actions]** 中，单击内置的 **[!UICONTROL AdobeCampaignStandard]** 操作。 操作配置窗格将在屏幕右侧打开。

   ![](../assets/actioncampaign.png)

1. 复制您的Adobe Campaign标准实例URL并将其粘贴到字 **[!UICONTROL URL]** 段中。

1. 单击 **[!UICONTROL Test the instance URL]** 以测试实例的有效性。

设计旅程时，类别中将提供三个操作： **[!UICONTROL Action]** **[!UICONTROL Email]**、 **[!UICONTROL Push]**、 **[!UICONTROL SMS]** (请参阅 [](../building-journeys/using-adobe-campaign-actions.md))。

![](../assets/journey58.png)

如果您使用第三方系统发送消息，则需要添加和配置自定义操作。 请参阅[](../action/about-custom-action-configuration.md)。
