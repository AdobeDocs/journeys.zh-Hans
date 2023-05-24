---
product: adobe campaign
title: 使用 Adobe Campaign 操作
description: 瞭解Adobe Campaign動作
feature: Journeys
role: User
level: Intermediate
exl-id: b2e5c333-d0d8-4fe1-a6b8-5f2e6b3624a4
source-git-commit: a9a129b1949d64c4a412d3ea4002b32e3563ea96
workflow-type: tm+mt
source-wordcount: '895'
ht-degree: 5%

---

# 使用 Adobe Campaign Standard {#using_campaign_action}

如果您有Adobe Campaign Standard，則可使用下列現成的動作活動： **[!UICONTROL Email]**， **[!UICONTROL Push]** 和 **[!UICONTROL SMS]**.

>[!NOTE]
>
>為此，您需要設定內建動作。 请参见[此页面](../action/working-with-adobe-campaign.md)。

您可為這些管道中的每一個選取Adobe Campaign Standard交易式傳訊 **範本**. 事實上， [!DNL Journey Orchestration] 不是訊息傳送解決方案。 對於內建電子郵件、簡訊和推播頻道，我們仰賴「交易式傳訊」來執行訊息傳送。 這表示如果您想在歷程中使用特定訊息範本，則必須在Adobe Campaign Standard中發佈。 請參閱 [此頁面](https://experienceleague.adobe.com/docs/campaign-standard/using/communication-channels/transactional-messaging/getting-started-with-transactional-msg.html?lang=zh-Hans) 以瞭解如何使用此功能。

>[!NOTE]
>
>必須發佈Campaign Standard交易式訊息及其相關事件，才能在Journey Orchestration中使用。 如果事件已發佈，但訊息尚未發佈，則不會顯示在Journey Orchestration介面中。 如果訊息已發佈，但其關聯事件尚未發佈，則會顯示在Journey Orchestration介面中，但無法使用。

![](../assets/journey59.png)

您可以使用事件（也稱為即時）或設定檔交易式訊息範本。

>[!NOTE]
>
>當我們傳送即時交易式訊息(rtEvent)或因自訂動作而透過協力廠商系統路由訊息時，疲勞、封鎖清單或取消訂閱管理需要特定設定。 例如，如果「unsubscribe」屬性儲存在Adobe Experience Platform或協力廠商系統中，則必須在傳送訊息之前新增條件，以檢查此條件。

當您選取範本時，訊息裝載中預期的所有欄位都會顯示在下方的活動設定窗格中。 **[!UICONTROL Address]** 和 **[!UICONTROL Personalization Data]**. 您需要將每個欄位與您要使用的欄位對應（從事件或資料來源）。 您也可以使用進階運算式編輯器來手動傳遞值、對擷取的資訊執行資料操作（例如將字串轉換為大寫）或使用「if， then， else」等函式。 请参阅[此页](../expression/expressionadvanced.md)。

![](../assets/journey60.png)

## 電子郵件和簡訊 {#section_asc_51g_nhb}

對象 **[!UICONTROL Email]** 和 **[!UICONTROL SMS]**，則引數相同。

>[!NOTE]
>
>對於電子郵件，如果您使用設定檔交易式範本，則會透過Campaign Standard立即處理取消訂閱機制。 您只需新增 **[!UICONTROL Unsubscription link]** 範本中的內容區塊([瞭解更多](https://experienceleague.adobe.com/docs/campaign-standard/using/communication-channels/transactional-messaging/getting-started-with-transactional-msg.html?lang=zh-Hans))。 如果您使用以事件為基礎的範本(rtEvent)，則需要在訊息中新增連結，在URL引數中傳遞人員的電子郵件，並指向取消訂閱的登陸頁面。 您需要建立此登入頁面，並確保將人員取消訂閱的決策傳送至Adobe。

首先，您需要選擇異動訊息範本。 请参见[此页面](../building-journeys/about-action-activities.md)。

有兩種類別可供使用： **[!UICONTROL Address]** 和 **[!UICONTROL Personalization Data]**.

您可以輕鬆定義在何處擷取 **[!UICONTROL Address]** 或 **[!UICONTROL Personalization Data]** 使用介面。 您可以瀏覽事件和可用資料來源的欄位。 您也可以將進階運算式編輯器用於更進階的使用案例，例如使用需要傳遞引數或執行操作的資料來源。 请参阅[此页](../expression/expressionadvanced.md)。

**[!UICONTROL Address]**

>[!NOTE]
>
>此類別只有在您選取「事件」交易式訊息時才會顯示。 對於「設定檔」訊息，請 **[!UICONTROL Address]** 欄位會由系統自動從Adobe Campaign Standard中擷取。

這些是系統需要知道訊息傳送位置的欄位。 如果是電子郵件範本，則為電子郵件地址。 如果是簡訊，則為行動電話號碼。

![](../assets/journey61.png)

**[!UICONTROL Personalization Data]**

>[!NOTE]
>
>您無法在個人化資料中傳遞集合。 如果交易式電子郵件或簡訊需要集合，則無法運作。 另請注意，個人化資料具有預期的格式（例如：字串、小數等）。 您必須注意遵守這些預期的格式。

這些是Adobe Campaign Standard訊息預期的欄位。 這些欄位可用於個人化訊息、套用條件式格式或挑選特定訊息變體。

![](../assets/journey62.png)

## 推送 {#section_im3_hvf_nhb}

在使用推送活動之前，您的行動應用程式需要與Campaign Standard一起設定以傳送推送通知。 使用此 [文章](https://helpx.adobe.com/cn/campaign/kb/integrate-mobile-sdk.html) 以針對行動裝置採取必要的實作步驟。

首先，您需要從下拉式清單中選擇行動應用程式和交易式訊息。 请参阅[此页](../building-journeys/about-action-activities.md)。

![](../assets/journey62bis.png)

有兩種類別可供使用： **[!UICONTROL Target]** 和 **[!UICONTROL Personalization Data]**.

**[!UICONTROL Target]**

>[!NOTE]
>
>只有當您選取事件訊息時，才會顯示此類別。 對於設定檔訊息，請 **[!UICONTROL Target]** 系統會使用Adobe Campaign Standard執行的調解，自動擷取欄位。

在本節中，您需要定義 **[!UICONTROL Push platform]**. 下拉式清單可讓您選取 **[!UICONTROL Apple Push Notification Server]** (iOS)或 **[!UICONTROL Firebase Cloud Messaging]** (Android)。 您也可以從事件或資料來源選取特定欄位，或定義進階運算式。

您也需要定義 **[!UICONTROL Registration Token]**. 此運算式取決於權杖在事件裝載或其他中的定義方式 [!DNL Journey Orchestration] 資訊。 如果代號是在執行個體的集合中定義，則可以是簡單欄位或更複雜的運算式：

```
@{Event_push._experience.campaign.message.profileSnapshot.pushNotificationTokens.first().token}
```

**[!UICONTROL Personalization Data]**

>[!NOTE]
>
>您無法在個人化資料中傳遞集合。 如果交易式推送需要集合，則無法運作。 另請注意，個人化資料具有預期的格式（例如：字串、小數等）。 您必須注意遵守這些預期的格式。

這些是Adobe Campaign Standard訊息中使用的交易式範本預期的欄位。 這些欄位可用於個人化您的訊息、套用條件式格式或挑選特定的訊息變體。
