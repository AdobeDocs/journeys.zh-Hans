---
product: adobe campaign
title: 定义有效负载字段
description: 瞭解如何定義裝載欄位
feature: Journeys
role: User
level: Intermediate
exl-id: 9d385b64-46cd-489b-9c18-352fa2a2dbba
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '299'
ht-degree: 5%

---

# 定义有效负载字段 {#concept_yrw_3qt_52b}

裝載定義可讓您選擇系統預期從歷程中的事件接收的資訊，以及識別與事件相關聯之人員的金鑰。 有效負載以Experience CloudXDM欄位定義為基礎。 如需XDM的詳細資訊，請參閱 [此頁面](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=zh-Hans).

1. 從清單中選取XDM結構描述，然後按一下 **[!UICONTROL Payload]** 欄位或位於 **[!UICONTROL Edit]** 圖示。

   ![](../assets/journey8.png)

   將顯示結構描述中定義的所有欄位。 欄位清單會因結構描述而異。 您可以搜尋特定欄位，或使用篩選器來顯示所有節點和欄位，或僅顯示選定的欄位。 根據結構描述定義，某些欄位可能是必填欄位並預先選定。 您無法取消選取它們。 依預設，會選取事件必須填寫的所有欄位，才能透過Journey Orchestration正確接收事件。

   >[!NOTE]
   >
   >請確定您已將「協調流程」Mixin新增至XDM結構描述。 這將確保您的結構描述包含使用的所有必要資訊 [!DNL Journey Orchestration].

   ![](../assets/journey9.png)

1. 選取您預期會從事件接收的欄位。 這些是業務使用者將在歷程中善用的欄位。 它們也必須包含用來識別與事件相關聯之人員的金鑰(請參閱 [此頁面](../event/defining-the-event-key.md))。

   ![](../assets/journey10.png)

   >[!NOTE]
   >
   >對於系統產生的事件， **[!UICONTROL eventID]** 欄位會自動新增到所選欄位清單中，以便 [!DNL Journey Orchestration] 可以識別事件。 推播事件的系統不應產生ID，而應使用有效負載預覽中可用的ID。 请参阅[此页](../event/previewing-the-payload.md)。

1. 選取完所需欄位後，按一下 **[!UICONTROL Save]** 或按 **[!UICONTROL Enter]**.

   ![](../assets/journey11.png)

   所選欄位的數量會出現在 **[!UICONTROL Payload]** 欄位。

   ![](../assets/journey12.png)
