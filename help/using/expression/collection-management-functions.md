---
product: adobe campaign
title: 收藏集管理函数
description: 瞭解集合管理函式中的資料型別
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: e80b04fe-b2d3-4c1b-ba22-7e37a9ad1d57
source-git-commit: 579e5a0dbdc11369248c2683c399b090130a7262
workflow-type: tm+mt
source-wordcount: '584'
ht-degree: 2%

---

# 收藏集管理函数 {#collection-management-functions}

運算式語言也引入了一組查詢集合的函式。

這些函式說明如下。 在下列範例中，讓我們使用包含集合的事件裝載：

```json
                { 
   "_experience":{ 
      "campaign":{ 
         "message":{ 
            "profile":{ 
               "pushNotificationTokens":[ 
                  { 
                     "token":"token_1",
                     "application":{ 
                        "_id":"APP1",
                        "name":"MarltonMobileApp",
                        "version":"1.0"
                     }
                  },
                  { 
                     "token":"token_2",
                     "application":{ 
                        "_id":"APP2",
                        "name":"MarketplaceApp",
                        "version":"1.0"
                     }
                  },
                  { 
                     "token":"token_3",
                     "application":{ 
                        "_id":"APP3",
                        "name":"VendorApp",
                        "version":"2.0"
                     }
                  }
               ]
            }
         }
      }
   },
   "timestamp":"1536160728"
}
```

**函式&quot;all(`<condition>`)」**

此 **[!UICONTROL all]** 函式可使用布林運算式來定義指定集合上的篩選器。

```json
<listExpression>.all(<condition>)
```

例如，在所有應用程式使用者中，您可以使用IOS 13 (布林值運算式「IOS 13==使用的應用程式」)來取得使用者。 此函式的結果是篩選的清單，其中包含符合布林運算式的專案（例如：應用程式使用者1、應用程式使用者34、應用程式使用者432）。

在資料來源條件活動中，您可以檢查結果是否為 **[!UICONTROL all]** 函式是否為null。 您也可以合併此專案 **[!UICONTROL all]** 函式與其他函式，例如 **[!UICONTROL count]**. 如需詳細資訊，請參閱 [資料來源條件活動](../building-journeys/condition-activity.md#data_source_condition).

**示例 1:**

我們要檢查使用者是否已安裝特定版本的應用程式。 為此，我們會取得與行動應用程式（1.0版）相關的所有推播通知權杖。然後，我們使用執行條件 **[!UICONTROL count]** 函式來檢查傳回的Token清單是否至少包含一個元素。

```json
count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all(currentEventField.application.version == "1.0").token}) > 0
```

結果為真。

**示例 2:**

在此處，我們使用 **[!UICONTROL count]** 函式來檢查集合中是否有推播通知權杖。

```json
count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all().token}) > 0
```

結果將會是true。

<!--Alternatively, you can check if there is no token in the collection:

   ```json
   count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all().token}) == 0
   ```

The result will be false.

Here we use the count function in a condition to count the number of push notification tokens in the event.

`count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all().token})`

The result is true.

Note that when the condition in the **all()** function is empty, the filter will return all the elements in the list. Hence, the expression above is equivalent to:

`count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.application.name})`

In both cases, the result of the expression is **3**.

A query of experience events recorded on the Adobe Experience Platform may or may not include the current event that triggered the current Journey. This will depend on the relative processing time with which [!DNL Journey Orchestration] sees an event and started evaluating conditions, versus the time it takes for that event to be ingested into the Adobe Experience Platform. For example, when using the .all() syntax to query experience events from the Adobe Experience Platform, we recommend enforcing the exclusion of the current event (by requiring an
earlier timestamp) in order to only consider prior events.-->

>[!NOTE]
>
>當篩選條件位於 **all()** 函式為空，則篩選條件會傳回清單中的所有元素。 **不過，若要計算集合的元素數量，不需要all函式。**


```json
count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.token})
```

運算式的結果為 **3**.

**示例 3:**

在此處，我們會檢查個人在過去24小時內是否未收到任何通訊。 我們會使用兩個運算式，根據集合的兩個元素，篩選從ExperiencePlatform資料來源擷取的體驗事件集合。 尤其是，事件的時間戳記會與傳回的dateTime比較， **[!UICONTROL nowWithDelta]** 函式。

```json
count(#{ExperiencePlatform.MarltonExperience.experienceevent.all(
   currentDataPackField.directMarketing.sends.value > 0 and
   currentDataPackField.timestamp > nowWithDelta(-1, "days")).timestamp}) == 0
```

如果沒有符合這兩個條件的體驗事件，則結果為true。

**示例 4:**

在此處，我們想檢查個人在過去7天內是否至少啟動過一次應用程式，以便觸發推播通知，邀請他們啟動教學課程。

```json
count(
 #{ExperiencePlatform.AnalyticsData.experienceevent.all(
 nowWithDelta(-7,"days") <= currentDataPackField.timestamp
 and currentDataPackField.application.firstLaunches.value > 0
)._id}) > 0
```

<!--**"All + Count" example 4:** here we use the count function in a boolean expression to see if there is push notification tokens in the collection.

`count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all().application.name}) > 0`

The result will be:

`true`

Alternatively, you can check if there is NO token in the collection:

`count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all().application.name}) =0`

The result will be:

`false`-->

>[!NOTE]
>
>**[!UICONTROL currentEventField]** 僅適用於操控事件集合和 **currentDataPackField**
>操控資料來源集合時。 處理集合時使用 **[!UICONTROL all]**， **[!UICONTROL first]** 和 **[!UICONTROL last]**，我們
>逐一在集合的每個元素上回圈。 **[!UICONTROL currentEventField]** 和 **currentDataPackField**
>與正在循環的元素相對應。

**函式&quot;first(`<condition>`)」和「last(`<condition>`)」**

此 **[!UICONTROL first]** 和 **[!UICONTROL last]** 函式也會在集合上啟用篩選的定義，同時傳回符合篩選的清單的第一個/最後一個元素。

_`<listExpression>.first(<condition>)`_

_`<listExpression>.last(<condition>)`_

**示例 1:**

此運算式會傳回與版本為1.0的行動應用程式關聯的第一個推播通知權杖。

```json
@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.first(currentEventField.application.version == "1.0").token
```

結果為&quot;token_1&quot;。

**示例 2:**

此運算式會傳回與版本為1.0的行動應用程式相關的最後一個推播通知權杖。

```json
@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.last&#8203;(currentEventField.application.version == "1.0").token}
```

結果為「token_2」。

>[!NOTE]
>
>體驗事件會以相反時間順序的集合形式從Adobe Experience Platform中擷取，因此：
>
>* **[!UICONTROL first]** 函式將傳回最近的事件
>* **[!UICONTROL last]** 函式會傳回最舊的一個。


**示例 3:**

我們會檢查第一個（最新） DMA ID為非零值的Adobe Analytics事件是否具有等於602的值。

```json
#{ExperiencePlatform.AnalyticsProd_EvarsProps.experienceevent.first(
currentDataPackField.placeContext.geo.dmaID > 0).placeContext.geo.dmaID} == 602
```

**函式&quot;at(`<index>`)」**

此 **[!UICONTROL at]** 函式可讓您根據索引來參照集合中的特定元素。
索引0是集合的第一個索引。

_`<listExpression>`.at(`<index>`)_

**示例：**

此運算式會傳回清單的第二個推播通知Token。

```json
@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.at(1).token}
```

結果為「token_2」。

**其他範例**

```json
#{ExperiencePlatform.ExperienceEventFieldGroup.experienceevent. all(currentDataPackField._aepgdcdevenablement2.purchase_event.receipt_nbr == "10-337-4016"). 
_aepgdcdevenablement2.purchase_event.productListItems. all(currentDataPackField.SKU == "AB17 1234 1775 19DT B4DR 8HDK 762").name}
```

```json
 #{ExperiencePlatform.ExperienceEventFieldGroup.experienceevent.last(
currentDataPackField.eventType == "commerce.productListAdds").productListItems.last(currentDataPackField.priceTotal >= 150).name}
```
