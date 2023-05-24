---
product: adobe campaign
title: 關於Journey Orchestration事件的ExperienceEvent結構
description: 瞭解用於Journey Orchestration事件的ExperienceEvent結構描述
feature: Journeys
role: User
level: Intermediate
exl-id: ffec0d42-8632-4806-97df-da2a2372ca53
source-git-commit: 3a0fc5cd6b7bc4177ab50986b11b020a11a72c9b
workflow-type: tm+mt
source-wordcount: '725'
ht-degree: 4%

---

# 關於的ExperienceEvent結構描述 [!DNL Journey Orchestration] 事件

[!DNL Journey Orchestration] 事件是指透過串流擷取傳送至Adobe Experience Platform的XDM體驗事件。

因此，設定事件的重要先決條件 [!DNL Journey Orchestration] 您是否熟悉Adobe Experience Platform的Experience Data Model （或XDM）、如何組成XDM Experience Event結構描述，以及如何將XDM格式的資料串流到Adobe Experience Platform。

## 的結構描述需求 [!DNL Journey Orchestration] 事件

設定事件的第一步 [!DNL Journey Orchestration] 是用來確保您定義了XDM結構描述來代表事件，並建立了一個資料集來記錄Adobe Experience Platform上的事件例項。 擁有事件的資料集並非絕對必要，但將事件傳送至特定資料集可讓您維護使用者的事件歷史記錄，以供日後參考及分析，因此總是對的。 如果您還沒有適合事件的結構描述和資料集，這兩項工作都可以在Adobe Experience Platform網頁介面中完成。

![](../assets/schema1.png)

任何將用於以下專案的XDM結構描述 [!DNL Journey Orchestration] 事件應符合下列要求：

* 結構描述必須是XDM ExperienceEvent類別。

   ![](../assets/schema2.png)

* 對於系統產生的事件，結構描述必須包含Orchestration eventID mixin。 [!DNL Journey Orchestration] 使用此欄位來識別歷程中使用的事件。

   ![](../assets/schema3.png)

* 宣告身分欄位以識別事件的主旨。 如果未指定身分，則可使用身分對應。 不建议采取此做法。

   ![](../assets/schema4.png)

* 如果您希望此資料稍後可在歷程中查詢，請標籤設定檔的結構描述和資料集。

   ![](../assets/schema5.png)

   ![](../assets/schema6.png)

* 您可以隨意加入資料欄位，以擷取您要與事件一起加入的任何其他內容資料，例如關於使用者的資訊、產生事件的裝置、位置或與事件相關的任何其他有意義的情況。

   ![](../assets/schema7.png)

   ![](../assets/schema8.png)

## 利用架构关系{#leverage_schema_relationships}

Adobe Experience Platform 让您可以定义架构之间的关系，以便将一个数据集用作另一个数据集的查询表。

假設您的品牌資料模型有一個擷取購買資料的結構描述。 您也有產品目錄的結構描述。 您可以在購買結構描述中擷取產品ID，並使用關係從產品目錄中查詢更完整的產品詳細資訊。 舉例來說，這可讓您為所有購買筆記型電腦的客戶建立區段，而無須明確列出所有筆記型電腦ID，或擷取異動系統中的每個單一產品詳細資訊。

若要定義關係，來源結構描述中必須有專用欄位，在此案例中是購買結構描述中的產品ID欄位。 此欄位需要參考目的地結構描述中的產品ID欄位。 必須為設定檔啟用來源和目的地資料表，而且目的地結構描述必須將該通用欄位定義為其主要身分。

以下是已為設定檔啟用的產品目錄結構，產品ID已定義為主要身分。

![](../assets/schema9.png)

以下是產品ID欄位中定義的購買結構描述。

![](../assets/schema10.png)

>[!NOTE]
>
>進一步瞭解 [Experience Platform檔案](https://experienceleague.adobe.com/docs/platform-learn/tutorials/schemas/configure-relationships-between-schemas.html?lang=en).

在Journey Orchestration中，您可以善用連結表格中的所有欄位：

* 設定單一事件時， [瞭解詳情](../event/experience-event-schema.md#unitary_event_configuration)
* 在歷程中使用條件時， [瞭解詳情](../event/experience-event-schema.md#journey_conditions_using_event_context)
* 在自訂動作個人化中， [瞭解詳情](../event/experience-event-schema.md#custom_action_personalization_with_journey_event_context)

### 單一事件設定{#unitary_event_configuration}

連結的結構描述欄位可在單一事件設定中使用：

* 瀏覽事件設定畫面中的事件結構描述欄位時。
* 定義系統產生事件的條件時。

![](../assets/schema11.png)

連結的欄位無法使用：

* 在事件索引鍵公式中
* 在事件id條件中（規則型事件）

若要瞭解如何設定單一事件，請參閱此 [頁面](../event/about-creating.md).

### 使用事件內容的歷程條件{#journey_conditions_using_event_context}

您可以使用查詢表格中的資料，連結至歷程中使用的事件，以進行條件建置（運算式編輯器）。

在歷程中新增條件、編輯運算式，並在運算式編輯器中展開事件節點。

![](../assets/schema12.png)

若要瞭解如何定義歷程條件，請參閱此 [頁面](../building-journeys/condition-activity.md).

### 使用歷程事件內容進行動作個人化{#custom_action_personalization_with_journey_event_context}

設定歷程動作活動的動作引數時，可使用連結的欄位。

![](../assets/schema13.png)

若要瞭解如何使用自訂動作，請參閱此 [頁面](../building-journeys/using-custom-actions.md).

