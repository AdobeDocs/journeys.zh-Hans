---
product: adobe campaign
title: 收藏集管理函数
description: 了解集合管理功能中的数据类型
feature: 历程
role: Data Engineer
level: Experienced
exl-id: e80b04fe-b2d3-4c1b-ba22-7e37a9ad1d57
source-git-commit: e0bf1a6f9c160b72da28feaca1ca52665f365630
workflow-type: tm+mt
source-wordcount: '585'
ht-degree: 2%

---

# 收藏集管理函数 {#collection-management-functions}

表达式语言还引入了一组用于查询集合的函数。

下面对这些函数进行了说明。 在以下示例中，让我们使用包含集合的事件有效负载：

```
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

**[!UICONTROL all]**&#x200B;函数可使用布尔表达式来定义给定集合上的过滤器。

```
<listExpression>.all(<condition>)
```

例如，在所有应用程序用户中，您可以使用IOS 13（布尔表达式“使用了IOS 13的应用程序”）获取==用户。 此函数的结果是包含与布尔表达式匹配的项目的过滤列表(例如：应用程序用户1、应用程序用户34、应用程序用户432)。

在“数据源条件”活动中，您可以检查&#x200B;**[!UICONTROL all]**&#x200B;函数的结果是否为null。 您还可以将此&#x200B;**[!UICONTROL all]**&#x200B;函数与其他函数（如&#x200B;**[!UICONTROL count]**）结合使用。 有关更多信息，请参阅[数据源条件活动](../building-journeys/condition-activity.md#data_source_condition)。

**示例 1:**

我们希望检查用户是否安装了特定版本的应用程序。 为此，我们会获取与版本为1.0的移动设备应用程序关联的所有推送通知令牌。然后，我们使用&#x200B;**[!UICONTROL count]**&#x200B;函数执行一个条件，以检查返回的令牌列表是否包含至少一个元素。

```
count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all(currentEventField.application.version == "1.0").token}) > 0
```

结果为true。

**示例 2:**

在此，我们使用&#x200B;**[!UICONTROL count]**&#x200B;函数检查集合中是否存在推送通知令牌。

```
count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all().token}) > 0
```

结果为true。

<!--Alternatively, you can check if there is no token in the collection:

   ```
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
>当&#x200B;**all()**&#x200B;函数中的筛选条件为空时，筛选器将返回列表中的所有元素。 **但是，为了计算集合的元素数，不需要全部函数。**


```
count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.token})
```

表达式的结果为&#x200B;**3**。

**示例 3:**

在本例中，我们会检查某个人在过去24小时内是否未收到任何通信。 我们使用两个基于集合两个元素的表达式，过滤从ExperiencePlatform数据源检索的体验事件集合。 特别是，事件的时间戳将与&#x200B;**[!UICONTROL nowWithDelta]**&#x200B;函数返回的dateTime进行比较。

```
count(#{ExperiencePlatform.MarltonExperience.experienceevent.all(
   currentDataPackField.directMarketing.sends.value > 0 and
   currentDataPackField.timestamp > nowWithDelta(-1, "days")).timestamp}) == 0
```

如果没有与这两个条件匹配的体验事件，则结果将为true。

**示例4:**

在此，我们要检查个人是否在过去7天内至少启动了一次应用程序，以便例如触发推送通知，邀请他启动教程。

```
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
>**[!UICONTROL currentEventField]** 仅在处理事件集合和currentDataPackField时 **可用**
>处理数据源集合时。 处理&#x200B;**[!UICONTROL all]**、**[!UICONTROL first]**&#x200B;和&#x200B;**[!UICONTROL last]**的集合时，我们
>逐个循环显示在集合的每个元素上。 **[!UICONTROL currentEventField]** 和 **currentDataPackField**
>对应于所环绕的元素。

**函数“first(`<condition>`)”和“last(`<condition>`)”**

**[!UICONTROL first]**&#x200B;和&#x200B;**[!UICONTROL last]**&#x200B;函数还允许在返回满足过滤器的列表的第一个/最后一个元素时对集合中的过滤器进行定义。

_`<listExpression>.first(<condition>)`_

_`<listExpression>.last(<condition>)`_

**示例 1:**

此表达式会返回与版本为1.0的移动设备应用程序关联的第一个推送通知令牌。

```
@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.first(currentEventField.application.version == "1.0").token
```

结果为“token_1”。

**示例 2:**

此表达式会返回与版本为1.0的移动设备应用程序关联的最后一个推送通知令牌。

```
@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.last&#8203;(currentEventField.application.version == "1.0").token}
```

结果为“token_2”。

>[!NOTE]
>
>体验事件是作为收藏集从Adobe Experience Platform中以时间顺序进行检索，因此：
>* **[!UICONTROL first]** 函数将返回最近的事件
>* **[!UICONTROL last]** 函数将返回最早的函数。


**示例 3:**

我们会检查DMA ID具有非零值的第一个（最近的）Adobe Analytics事件是否具有等于602的值。

```
#{ExperiencePlatform.AnalyticsProd_EvarsProps.experienceevent.first(
currentDataPackField.placeContext.geo.dmaID > 0).placeContext.geo.dmaID} == 602
```

**函数“at(`<index>`)”**

**[!UICONTROL at]**函数允许您根据索引引用集合中的特定元素。
索引0是集合的第一个索引。

_`<listExpression>`.at(`<index>`)_

**示例：**

此表达式会返回列表的第二个推送通知令牌。

```
@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.at(1).token}
```

结果为“token_2”。

**其他示例**

```
#{ExperiencePlatform.ExperienceEventFieldGroup.experienceevent. all(currentDataPackField._aepgdcdevenablement2.purchase_event.receipt_nbr == "10-337-4016"). 
_aepgdcdevenablement2.purchase_event.productListItems. all(currentDataPackField.SKU == "AB17 1234 1775 19DT B4DR 8HDK 762").name}
```

```
 #{ExperiencePlatform.ExperienceEventFieldGroup.experienceevent.last(
currentDataPackField.eventType == "commerce.productListAdds").productListItems.last(currentDataPackField.priceTotal >= 150).name}
```
