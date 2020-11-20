---
product: adobe campaign
solution: Journey Orchestration
title: 集合管理函数
description: 了解集合管理功能中的数据类型
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '582'
ht-degree: 1%

---


# 集合管理函数 {#collection-management-functions}

表达式语言还为查询集合引入了一组功能。

这些功能在下面进行说明。 在以下示例中，让我们使用包含集合的事件有效负荷：

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

该函 **[!UICONTROL all]** 数通过使用布尔表达式启用给定集合上的筛选器的定义。

```
<listExpression>.all(<condition>)
```

例如，在所有应用程序用户中，您都可以使用IOS 13(布尔表达式“已使用的应用程序== IOS 13”)获取这些用户。 此函数的结果是筛选列表，其中包含与布尔表达式匹配的项(例如：应用程序用户1、应用程序用户34、应用程序用户432)。

在“数据源条件”活动中，您可以检查函数的 **[!UICONTROL all]** 结果是否为null。 您还可以将此函数 **[!UICONTROL all]** 与其他函数(如 **[!UICONTROL count]**)组合。 有关详细信息，请参 [阅数据源条件活动](../building-journeys/condition-activity.md#data_source_condition)。

**示例1:**

我们希望检查用户是否已安装特定版本的应用程序。 为此，我们将获得与版本为1.0的移动应用程序关联的所有推送通知令牌。然后，我们使用该函数执行一个条件，以检查令牌的返回列表是否包含至少一个元素。 **[!UICONTROL count]**

```
count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all(currentEventField.application.version == "1.0").token}) > 0
```

结果是真的。

**示例 2:**

在此，我们使用 **[!UICONTROL count]** 该函数检查集合中是否有推送通知令牌。

```
count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all().token}) > 0
```

结果将是真的。

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
>当all()函数中的 **过滤条件** 为空时，过滤器将返回列表中的所有元素。 **但是，为了计算集合的元素数，不需要全部函数。**


```
count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.token})
```

The result of the expression is **3**.

**示例3:**

在此，我们检查过去24小时内是否有个人未收到任何通信。 我们使用两个基于两个事件的表达式来过滤从ExperiencePlatform数据源检索到的体验集合。 特别是，将事件的时间戳与函数返回的dateTime进行比 **[!UICONTROL nowWithDelta]** 较。

```
count(#{ExperiencePlatform.MarltonExperience.experienceevent.all(
   currentDataPackField.directMarketing.sends.value > 0 and
   currentDataPackField.timestamp > nowWithDelta(-1, "days")).timestamp}) == 0
```

如果没有与这两个条件匹配的体验事件，则结果将为真。

**示例4:**

这里，我们要检查个人在过去7天中是否至少启动了一次应用程序，例如触发推送通知，邀请他开始教程。

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
>处理数据源集合时。 在处理集合时， **[!UICONTROL all]**&#x200B;我们 **[!UICONTROL first]** 会 **[!UICONTROL last]**提供
>逐个循环访问集合的每个元素。 **[!UICONTROL currentEventField]** 和 **currentDataPackField**
>与所环绕的元素相对应。

**函数“first(`<condition>`)”和“last(`<condition>`)”**

该 **[!UICONTROL first]** 和函 **[!UICONTROL last]** 数还允许在返回满足筛选器的列表的第一个／最后一个元素时定义集合上的筛选器。

_`<listExpression>.first(<condition>)`_

_`<listExpression>.last(<condition>)`_

**示例1:**

此表达式返回与版本为1.0的移动应用程序关联的第一个推送通知令牌。

```
@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.first(currentEventField.application.version == "1.0").token
```

结果为“token_1”。

**示例 2:**

此表达式返回与版本为1.0的移动应用程序关联的最后一个推送通知令牌。

```
@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.last&#8203;(currentEventField.application.version == "1.0").token}
```

结果为“token_2”。

>[!NOTE]
>
>体验事件从Adobe Experience Platform以相反的时间顺序作为集合进行检索，因此：
>* **[!UICONTROL first]** 函数将返回最近的事件
>* **[!UICONTROL last]** 函数将返回最旧的函数。


**示例3:**

我们检查DMA ID值为非零的第一个（最新的）Adobe Analytics事件的值是否等于602。

```
#{ExperiencePlatform.AnalyticsProd_EvarsProps.experienceevent.first(
currentDataPackField.placeContext.geo.dmaID > 0).placeContext.geo.dmaID} == 602
```

**函数“at(`<index>`)”**

函 **[!UICONTROL at]** 数允许您根据索引引用集合中的特定元素。
索引0是集合的第一个索引。

_`<listExpression>`.at(`<index>`)_

**示例:**

此表达式返回列表的第二个推送通知令牌。

```
@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.at(1).token}
```

结果为“token_2”。