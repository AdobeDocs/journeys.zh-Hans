---
product: adobe campaign
title: 历程步骤共享概述
description: 历程步骤共享概述
feature: Journeys
role: User
level: Intermediate
exl-id: 95ca5fdb-38b7-47a0-b1a9-b1b26bf8e5f5
source-git-commit: bb07c0edaae469962ee3bf678664b4a0a83572fe
workflow-type: tm+mt
source-wordcount: '506'
ht-degree: 6%

---

# 历程步骤共享概述{#sharing-overview}

[!DNL Journey Orchestration] 自動將歷程績效資料傳送至Adobe Experience Platform，以便與其他資料結合進行分析。

>[!NOTE]
>
>此功能預設會在歷程步驟事件的所有執行個體上啟動。 您無法修改或更新在布建步驟事件期間建立的結構描述和資料集。 預設情況下，這些結構描述和資料集處於唯讀模式。

例如，您已設定傳送多封電子郵件的歷程。 此功能可讓您合併 [!DNL Journey Orchestration] 含有下游事件資料的資料，例如已發生的轉換次數、網站上發生的參與度或是商店中發生的交易數。 歷程資訊可以與Adobe Experience Platform上的資料結合，來自其他數位屬性或離線屬性，以提供更完整的效能檢視。

[!DNL Journey Orchestration] 自動建立必要的結構描述，並針對個人在歷程中執行的每個步驟，將資料集串流至Adobe Experience Platform。 步驟事件對應於在歷程中從某個節點移動到另一個節點的個人。 例如，在包含事件、條件和動作的歷程中，三個步驟事件會傳送至Adobe Experience Platform。

傳遞的XDM欄位清單很完整。 有些包含系統產生的程式碼，有些則具有人類看得懂的易記名稱。 範例包括歷程活動或步驟狀態的標籤：動作逾時或錯誤結束的次數。

>[!CAUTION]
>
>無法為即時設定檔服務開啟資料集。 請確定 **[!UICONTROL Profile]** 切換功能已關閉。

歷程會在資料發生時以串流方式傳送資料。 您可以使用查詢服務來查詢此資料。 您可以連線至Customer Journey Analytics或其他BI工具，以檢視與這些步驟相關的資料。

已建立下列結構描述：

* 的歷程步驟事件結構描述 [!DNL Journey Orchestration]  — 繫結至歷程中繼資料的歷程步驟事件。
* 具有歷程欄位的歷程結構描述 [!DNL Journey Orchestration]  — 說明歷程的歷程中繼資料。

![](../assets/sharing1.png)

![](../assets/sharing2.png)

傳遞的資料集如下：

* 歷程步驟事件
* 历程

![](../assets/sharing3.png)

傳遞至Adobe Experience Platform的XDM欄位清單的詳細資訊如下：

* [步骤事件字段列表](../building-journeys/sharing-field-list.md)
* [旧版步骤事件字段](../building-journeys/sharing-legacy-fields.md)

如需向Adobe Experience Platform報告步驟事件的詳細資訊，請觀看此影片 [教學課程影片](https://experienceleague.adobe.com/docs/journey-orchestration-learn/tutorials/reporting-step-events-to-adobe-experience-platform.html).

## 與Customer Journey Analytics整合{#integration-cja}

Journey Orchestration步驟事件可以連結到中的其他資料集 [Adobe Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=zh-Hans). 以下是一般工作流程：

* Customer Journey Analytics會擷取「歷程步驟事件」資料集。
* 此 **profileID** 相關聯「Journey Orchestration的歷程步驟事件結構描述」中的欄位定義為身分欄位。 在Customer Journey Analytics中，您可以將此資料集連結至任何與以人員為基礎的識別碼具有相同值的其他資料集。
* 如果您想要在Customer Journey Analytics中使用此資料集，如需跨管道歷程分析，請參閱此 [檔案](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/cross-channel.html).
