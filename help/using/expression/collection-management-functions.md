---
product: adobe campaign
title: 集合管理函数
description: 了解集合管理函数中的数据类型
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: e80b04fe-b2d3-4c1b-ba22-7e37a9ad1d57
source-git-commit: 579e5a0dbdc11369248c2683c399b090130a7262
workflow-type: tm+mt
source-wordcount: '604'
ht-degree: 1%

---

# 集合管理函数 {#collection-management-functions}

表达式语言还引入了一组查询集合的函数。

这些职能说明如下。 在以下示例中，我们使用包含集合的事件有效负载：

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

**函数“all(`<condition>`)”**

**[!UICONTROL all]**&#x200B;函数使用布尔表达式在给定集合上启用过滤器的定义。

```json
<listExpression>.all(<condition>)
```

例如，在所有应用程序用户中，您可以使用IOS 13(布尔表达式“IOS 13==使用的应用程序”)获取这些用户。 此函数的结果是包含与布尔表达式匹配项目的过滤列表（例如：应用程序用户1、应用程序用户34、应用程序用户432）。

在数据Source条件活动中，您可以检查&#x200B;**[!UICONTROL all]**&#x200B;函数的结果是否为null。 您还可以将此&#x200B;**[!UICONTROL all]**&#x200B;函数与其他函数（如&#x200B;**[!UICONTROL count]**）组合。 有关详细信息，请参阅[数据Source条件活动](../building-journeys/condition-activity.md#data_source_condition)。

**示例1：**

我们要检查用户是否已安装了应用程序的特定版本。 为此，我们将获得与版本为1.0的移动应用程序关联的所有推送通知令牌。然后，我们使用&#x200B;**[!UICONTROL count]**&#x200B;函数执行一个条件，以检查返回的令牌列表是否至少包含一个元素。

```json
count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all(currentEventField.application.version == "1.0").token}) > 0
```

结果为true。

**示例2：**

此处，我们使用&#x200B;**[!UICONTROL count]**&#x200B;函数来检查集合中是否有推送通知令牌。

```json
count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all().token}) > 0
```

结果将会是真。

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
>当&#x200B;**all()**&#x200B;函数中的筛选条件为空时，筛选器将返回列表中的所有元素。 **但是，为了计算集合的元素数，不需要all函数。**


```json
count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.token})
```

表达式的结果为&#x200B;**3**。

**示例3：**

在此处，我们检查个人在过去24小时内是否未收到任何通信。 我们使用基于集合的两个元素的两个表达式，过滤从ExperiencePlatform数据源检索到的体验事件集合。 特别是，该事件的时间戳会与&#x200B;**[!UICONTROL nowWithDelta]**&#x200B;函数返回的dateTime进行比较。

```json
count(#{ExperiencePlatform.MarltonExperience.experienceevent.all(
   currentDataPackField.directMarketing.sends.value > 0 and
   currentDataPackField.timestamp > nowWithDelta(-1, "days")).timestamp}) == 0
```

如果没有体验事件符合这两个条件，则结果将为true。

**示例4：**

在此处，我们要检查个人在过去7天内是否至少启动过一次应用程序，以便触发推送通知，邀请他们启动教程。

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
>**[!UICONTROL currentEventField]**&#x200B;仅在处理事件集合和&#x200B;**currentDataPackField**时可用
>处理数据源集合时。 处理具有&#x200B;**[!UICONTROL all]**、**[!UICONTROL first]**&#x200B;和&#x200B;**[!UICONTROL last]**的集合时，我们
>逐个循环集合的每个元素。 **[!UICONTROL currentEventField]**&#x200B;和&#x200B;**currentDataPackField**
>对应于正在循环的元素。

**函数“first(`<condition>`)”和“last(`<condition>`)”**

**[!UICONTROL first]**&#x200B;和&#x200B;**[!UICONTROL last]**&#x200B;函数还在返回满足筛选条件的列表的第一个/最后一个元素时，启用集合上的筛选条件的定义。

_`<listExpression>.first(<condition>)`_

_`<listExpression>.last(<condition>)`_

**示例1：**

此表达式返回与版本为1.0的移动应用程序关联的第一个推送通知令牌。

```json
@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.first(currentEventField.application.version == "1.0").token
```

结果为“token_1”。

**示例2：**

此表达式返回与版本为1.0的移动应用程序关联的最后一个推送通知令牌。

```json
@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.last&#8203;(currentEventField.application.version == "1.0").token}
```

结果为“token_2”。

>[!NOTE]
>
>体验事件将作为集合，以反向时间顺序从Adobe Experience Platform中进行检索，因此：
>
>* **[!UICONTROL first]**&#x200B;函数将返回最近的事件
>* **[!UICONTROL last]**&#x200B;函数将返回最早的一个。

**示例3：**

我们检查第一个（最新）DMA ID为非零值的Adobe Analytics事件是否具有等于602的值。

```json
#{ExperiencePlatform.AnalyticsProd_EvarsProps.experienceevent.first(
currentDataPackField.placeContext.geo.dmaID > 0).placeContext.geo.dmaID} == 602
```

**函数“at(`<index>`)”**

**[!UICONTROL at]**函数允许您根据索引引用集合中的特定元素。
索引0是集合的第一个索引。

_`<listExpression>`.at(`<index>`)_

**示例：**

此表达式返回列表的第二个推送通知令牌。

```json
@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.at(1).token}
```

结果为“token_2”。

**其他示例**

```json
#{ExperiencePlatform.ExperienceEventFieldGroup.experienceevent. all(currentDataPackField._aepgdcdevenablement2.purchase_event.receipt_nbr == "10-337-4016"). 
_aepgdcdevenablement2.purchase_event.productListItems. all(currentDataPackField.SKU == "AB17 1234 1775 19DT B4DR 8HDK 762").name}
```

```json
 #{ExperiencePlatform.ExperienceEventFieldGroup.experienceevent.last(
currentDataPackField.eventType == "commerce.productListAdds").productListItems.last(currentDataPackField.priceTotal >= 150).name}
```
