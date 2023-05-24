---
product: adobe campaign
title: 使用 Adobe Campaign
description: 瞭解Adobe Campaign動作
feature: Journeys
role: User
level: Intermediate
exl-id: c7e08542-fde8-4072-a697-42d35d6c58ba
source-git-commit: 545352efdcda80cb9940010c4587a20f53326085
workflow-type: tm+mt
source-wordcount: '302'
ht-degree: 4%

---

# 使用 Adobe Campaign Standard {#using_adobe_campaign_standard}

您可以使用Adobe Campaign Standard的「交易訊息」功能來傳送電子郵件、推播通知和簡訊。

[!DNL Journey Orchestration] 隨附立即可用的動作，可連線至Adobe Campaign Standard。

必須發佈Campaign Standard交易式訊息及其相關事件，才能在Journey Orchestration中使用。 如果事件已發佈，但訊息尚未發佈，則不會顯示在Journey Orchestration介面中。 如果訊息已發佈，但其關聯事件尚未發佈，則會顯示在Journey Orchestration介面中，但無法使用。

>[!NOTE]
>
>設定Adobe Campaign Standard整合後，Adobe Campaign Standard動作就會自動定義每5分鐘4000次呼叫的上限規則。 這與Adobe Campaign Standard交易式訊息的官方規模相對應。
>
>閱讀中有關交易式訊息傳送SLA的詳細資訊 [Adobe Campaign Standard產品說明](https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html).

以下是設定它的步驟：

1. 從 **[!UICONTROL Actions]** 清單中，按一下內建 **[!UICONTROL AdobeCampaignStandard]** 動作。 動作設定窗格會在畫面右側開啟。

   ![](../assets/actioncampaign.png)

1. 複製您的Adobe Campaign Standard執行個體URL並貼到 **[!UICONTROL URL]** 欄位。

1. 按一下 **[!UICONTROL Test the instance URL]** 以測試例項的有效性。

   >[!NOTE]
   >
   >此測試會驗證：
   >
   >主機為「.campaign.adobe.com」、「.campaign-sandbox.adobe.com」、「.campaign-demo.adobe.com」、「.ats.adobe.com」或「.adls.adobe.com」。
   >
   >URL以https開頭，
   >
   >與此Adobe Campaign Standard例項關聯的組織與Journey Orchestration的組織相同。

設計您的歷程時，三個動作將適用於 **[!UICONTROL Action]** 類別： **[!UICONTROL Email]**， **[!UICONTROL Push]**， **[!UICONTROL SMS]** (請參閱 [使用Adobe Campaign動作](../building-journeys/using-adobe-campaign-actions.md))。 **回應事件** 也可讓您對訊息點按、開啟等做出反應。 (請參閱 [回應事件](../building-journeys/reaction-events.md))。

![](../assets/journey58.png)

如果您使用協力廠商系統來傳送訊息，則需要新增及設定自訂動作。 另請參閱 [關於自訂動作組態](../action/about-custom-action-configuration.md).
