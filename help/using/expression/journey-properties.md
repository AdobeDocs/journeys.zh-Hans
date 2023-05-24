---
product: adobe campaign
title: 历程属性
description: 瞭解歷程屬性
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 798e4207-5bef-4002-9c1f-608bb6243e43
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '586'
ht-degree: 5%

---

# 歷程屬性 {#journey-properties}

在進階運算式編輯器中，您會找到 **歷程屬性** 類別，位於事件和資料來源類別下方。 此類別包含與給定設定檔的歷程相關的技術欄位。 这是系统从实时历程中检索到的信息，如历程 ID 或遇到的特定错误。

>[!NOTE]
>
>在簡單運算式編輯器中也可以使用歷程屬性。 檢視此 [區段](../building-journeys/condition-activity.md#about_condition)

![](../assets/journey-properties.png)

您會找到相關資訊，例如：

* 歷程版本：歷程uid、歷程版本uid、執行個體uid等。
* 錯誤：資料擷取、動作執行等。
* 目前步驟、上一個目前步驟等。
* 捨棄的設定檔

您可以使用這些欄位來建置運算式。 在歷程執行期間，將直接從歷程中擷取值。

以下是一些使用案例的範例：

* **記錄捨棄的設定檔**：您可以將上限規則從訊息中排除的所有設定檔傳送至協力廠商系統以進行記錄。 為此，您可以設定在發生逾時和錯誤時的路徑，並新增條件以篩選特定錯誤型別，例如：「透過上限規則來捨棄人員」。 然後，您可以透過自訂動作將已捨棄的設定檔推送到第三方系統。

* **發生錯誤時傳送警報**：每當訊息發生錯誤時，您可以傳送通知至協力廠商系統。 為此，您可以設定在發生錯誤時的路徑，新增條件和自訂動作。 例如，您可以在Slack頻道上傳送包含所遇到錯誤說明的通知。

* **改善報告中的錯誤** ：您可以為每個錯誤型別定義條件，而不是讓錯誤訊息只有一個路徑。 這可讓您調整報告並檢視所有錯誤型別資料。

## 欄位清單 {#journey-properties-fields}

| 类别 | 字段名称 | 标签 | 描述 |
|---|---|---|------------|
| 歷程版本 | journeyUID | 歷程識別碼 |  |
|  | journeyVersionUID | 歷程版本識別碼 |  |
|  | journeyVersionName | 歷程版本名稱 |  |
|  | journeyVersionDescription | 歷程版本說明 |  |
|  | journeyVersion | 歷程版本 |  |
| 歷程執行個體 | instanceUID | 歷程執行個體識別碼 | 執行個體的ID |
|  | externalKey | 外部金鑰 | 觸發歷程的個人識別碼 |
|  | organizationId | 組織識別碼 | 品牌組織 |
|  | sandboxName | 沙箱名稱 | 沙箱的名稱 |
| 标识 | profileId | 設定檔身分識別碼 | 歷程中設定檔的識別碼 |
|  | namespace | 設定檔身分名稱空間 | 歷程中設定檔的名稱空間（範例：ECID） |
| 目前節點 | currentNodeId | 目前節點識別碼 | 目前活動（節點）的識別碼 |
|  | currentNodeName | 目前節點名稱 | 目前活動的名稱（節點） |
| 上一個節點 | previousNodeId | 上一個節點識別碼 | 上一個活動（節點）的識別碼 |
|  | previousnodeName | 上一個節點名稱 | 上一個活動的名稱（節點） |
| 错误 | lastNodeUIDInError | 最後一個錯誤的節點識別碼 | 發生錯誤的最新活動（節點）的識別碼 |
|  | lastNodeNameInError | 最後一個錯誤的節點名稱 | 發生錯誤的最新活動（節點）名稱 |
|  | lastNodeTypeInError | 最後一個錯誤的節點型別 | 發生錯誤的最新活動（節點）的錯誤型別。 可能的型別：<ul><li>事件：事件、反應、SQ （範例：區段資格）</li><li>流量控制：結束、條件、等待</li><li>動作：ACS動作、跳轉、自訂動作</li></ul> |
|  | lastErrorCode | 上一個錯誤代碼 | 發生錯誤的最新活動（節點）的錯誤代碼。 可能的錯誤： <ul><li>HTTP錯誤代碼</li><li>上限</li><li>timedOut</li><li>錯誤(範例：發生非預期錯誤時的預設值。 不應該/極少數發生)</li></ul> |
|  | lastExecutedActionErrorCode | 最後執行動作的錯誤碼 | 發生錯誤的最新動作的錯誤碼 |
|  | lastDataFetchErrorCode | 上次資料擷取的錯誤碼 | 從資料來源擷取最新資料時的錯誤代碼 |
| 时间 | lastActionExecutionElapsedTime | 上次執行動作經過的時間 | 執行最新動作所花的時間 |
|  | lastDataFetchElapsedTime | 上次擷取資料經過的時間 | 從資料來源執行最新資料擷取所花的時間 |
