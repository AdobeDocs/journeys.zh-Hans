---
product: adobe campaign
title: 关于 Adobe Experience Platform 区段
description: 瞭解如何設定Adobe Experience Platform區段
feature: Journeys
role: User
level: Intermediate
exl-id: 94e1e3e3-9a46-41ca-bec1-f41287925372
source-git-commit: e5c0db2e1f85ea72fd54f91e4a26cc287377fb0e
workflow-type: tm+mt
source-wordcount: '362'
ht-degree: 10%

---

# 关于 Adobe Experience Platform 区段 {#about-segments}

如果您使用 [Adobe Experience Platform Segmentation Service](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html) 若要建立您的區段，您可以在中運用這些區段 [!DNL Journey Orchestration]. 由於有專屬的事件活動，您可以讓個人根據Adobe Experience Platform區段入口和出口，進入或前進歷程。 這也允許您使用簡單或進階運算式編輯器在歷程中建立複雜條件。

假设您拥有“白银客户”客户细分。通过此活动，您可以使所有新的白银客户进入历程，并向其发送一系列个性化消息。您也可以根據此區段輕鬆建置條件。

以下為可能性 [!DNL Journey Orchestration] 提供您區段：

* 存取Adobe Experience Platform區段清單。 另請參閱 [建立區段](../segment/creating-a-segment.md).
* 直接在中建立區段 [!DNL Journey Orchestration] 和使用「區段服務」建立區段的方式相同。 另請參閱 [建立區段](../segment/creating-a-segment.md).
* 使用簡單或進階運算式編輯器，在您的歷程條件中運用區段。 另請參閱 [在條件中使用區段](../segment/using-a-segment.md).
* 新增 **[!UICONTROL Segment qualification]** 歷程中的事件，以聆聽Adobe Experience Platform區段中設定檔的入口和出口。 另請參閱 [事件活動](../building-journeys/segment-qualification-events.md).

## Journey Orchestration中的評估方法 {#evaluation-method-in-journey-orchestration}

在Journey Orchestration中，對象是使用下列其中一種評估方法從區段定義產生：

* 串流區段 — 當新資料流入系統時，區段的對象清單會即時保持最新。
* 批次區段 — 區段的對象清單會根據過去一小時內送達的資料每小時更新。

系統會根據評估區段規則的複雜性和成本，針對每個區段定義來決定批次區段和串流區段之間的劃分。

您可以檢視中每個區段的評估方法 **[!UICONTROL Evaluation method]** 區段清單的欄。

在您首次定義區段後，設定檔只要符合資格，就會新增至對象。

從先前資料回填對象最長可能需要24小時。 回填對象後，對象會持續保持最新狀態，並隨時準備好進行目標定位。