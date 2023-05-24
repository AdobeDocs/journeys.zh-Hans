---
product: adobe campaign
title: 使用高级表达式编辑器
description: 了解如何构建高级表达式
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 724ae59e-d1b5-4de9-b140-d37064e22ac6
source-git-commit: a5d063784b278120b61f8d2641264baf40e34a90
workflow-type: tm+mt
source-wordcount: '492'
ht-degree: 2%

---

# 進階運算式範例

進階運算式編輯器可用來建立條件，讓您在歷程中篩選使用者。 這些條件可讓您定位使用者時間、日期、位置、持續時間或動作，例如購買或放棄購物車，以便在歷程中重新定位他們。

>[!NOTE]
>
>事件以@開頭，資料來源以#開頭。

## 在體驗事件上建立條件

進階運算式編輯器必須對時間序列執行查詢，例如購買清單或訊息的過去點按。 無法使用簡單編輯器執行此類查詢。

體驗事件會以相反時間順序的集合形式從Adobe Experience Platform中擷取，因此：

* 第一個函式將傳回最近的事件
* 最後一個函式會傳回最舊的函式。

例如，假設您想要將目標定位為過去7天內放棄購物車的客戶，以便在客戶接近商店時傳送訊息，提供他們想要的店內商品優惠。

**您需要建置下列條件：**

首先，鎖定瀏覽了線上商店但在過去7天內未完成訂單的客戶。

<!--**This expression looks for a specified value in a string value:**

`In (“addToCart”, #{field reference from experience event})`-->

**此運算式會尋找此使用者在過去7天中指定的所有事件：**

然後它會選取所有未轉換為completePurchase的addtocart事件。

>[!NOTE]
>
>若要在運算式中快速插入欄位，請連按兩下編輯器左側面板中的欄位。

指定的時間戳記會作為日期時間值，第二個是天數。

```json
        in( "addToCart", #{ExperiencePlatformDataSource
                        .ExperienceEventFieldGroup
                        .experienceevent
                        .all(
                        inLastDays(currentDataPackField.timestamp, 7 ))
                        .productData
                        .productInteraction})
        and
        not(in( "completePurchase", #{ExperiencePlatformDataSource
                        .ExperienceEventFieldGroup
                        .experienceevent
                        .all(
                        inLastDays(currentDataPackField.timestamp, 7 ))
                        .productData
                        .productInteraction}))
```

此運算式會傳回布林值。

**現在來建置運算式，檢查產品有庫存**

* 在「詳細目錄」中，此運算式會尋找產品的數量欄位，並指定數量欄位應大於0。

`#{Inventory.fieldgroup3.quantity} > 0`

* 在右側，會指定必要的值，在這裡，我們需要擷取從事件「EndaysLumaStudio」的位置對應的存放區位置：

`#{ArriveLumaStudio._acpevangelists1.location.location}`

* 並使用函式指定SKU `first` 若要擷取最近的「addToCart」互動：

   ```json
       #{ExperiencePlatformDataSource
                       .ExperienceEventFieldGroup
                       .experienceevent
                       .first(
                       currentDataPackField
                       .productData
                       .productInteraction == "addToCart"
                       )
                       .SKU}
   ```

從那裡，您可以在歷程中為產品不在商店時新增另一個路徑，並傳送包含參與選件的通知。 適當地設定訊息，並使用個人化資料來增強訊息目標。

## 使用進階運算式編輯器的字串操作範例

**條件**

此條件只會擷取「Arlington」中觸發的地理圍欄事件：

```json
        @{GeofenceEntry
                    .placeContext
                    .POIinteraction
                    .POIDetail
                    .name} == "Arlington"
```

說明：這是嚴格的字串比較（區分大小寫），等同於使用的簡單模式中的查詢 `equal to` 替換為 `Is sensitive` 已核取。

相同的查詢 `Is sensitive` 取消核取將在進階模式下產生下列運算式：

```json
        equalIgnoreCase(@{GeofenceEntry
                        .placeContext
                        .POIinteraction
                        .POIDetail
                        .name}, "Arlington")
```

**在動作中**

下列運算式可讓您在動作個人化欄位中定義CRM ID：

```json
substr(
   @{MobileAppLaunch
   ._myorganization
   .identification
   .crmid},
   1, 
   lastIndexOf(
     @{MobileAppLaunch
     ._myorganization
     .identification
     .crmid},
     '}'
   )
)
```

說明：此範例使用 `substr` 和 `lastIndexOf` 移除括住透過行動應用程式啟動事件傳遞之CRM ID的大括弧函式。

如需如何使用進階運算式編輯器的詳細資訊，請觀看 [此影片](https://experienceleague.adobe.com/docs/platform-learn/tutorials/journey-orchestration/create-a-journey.html).
