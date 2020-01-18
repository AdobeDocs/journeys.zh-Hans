---
title: 集合管理功能
description: 了解集合管理功能中的数据类型
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 017d502e21605b3e0b8c61e5fea0b4f6a65d4470

---


# 集合管理功能 {#collection-management-functions}

表达式语言还引入了一组用于查询集合的函数。

这些功能如下所述。 在以下示例中，让我们使用包含集合的事件有效负荷：

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

该函 **[!UICONTROL all]**数通过使用布尔表达式来允许在给定集合上定义过滤器。

```
<listExpression>.all(<condition>)
```

例如，在所有应用程序用户中，您都可以获得使用IOS 13的用户（布尔表达式“app used == IOS 13”）。 此函数的结果是包含与布尔表达式匹配的项目的筛选列表(示例：app user 1, app user 34, app user 432)。

在“数据源条件”活动中，您可以检查函数的结 **[!UICONTROL all]**果是否为null。 您还可以将此函数**[!UICONTROL all]** 与其他函数（如）组合 **[!UICONTROL count]**。 有关详细信息，请参[阅数据源条件活动](../building-journeys/condition-activity.md#data_source_condition)。

**示例1:**

我们想检查用户是否已安装特定版本的应用程序。 为此，我们获得与版本为1.0的移动应用程序关联的所有推送通知令牌。然后，利用该函数执行一个条件， **[!UICONTROL count]**检查返回的令牌列表是否包含至少一个元素。

```
count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all(currentEventField.application.version == "1.0").token}) > 0
```

结果是真的。

**示例2:**

在此，我们使用 **[!UICONTROL count]**函数检查集合中是否存在推送通知令牌。

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

A query of experience events recorded on the platform may or may not include the current event that triggered the current Journey. This will depend on the relative processing time with which Journey Orchestration sees an event and started evaluating conditions, versus the time it takes for that event to be ingested into the platform. For example, when using the .all() syntax to query experience events from the platform, we recommend enforcing the exclusion of the current event (by requiring an
earlier timestamp) in order to only consider prior events.-->

>[!NOTE]
>
>当all()函数中的过 **滤条件为空** ，过滤器将返回列表中的所有元素。 **但是，要计算集合的元素数，不需要全部函数。**


```
count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.token})
```

表达结果为 **3**。

**示例3:**

在此，我们检查过去24小时内是否有人未收到任何通信。 我们使用两个基于两个元素的表达式来过滤从ExperiencePlatform数据源检索的体验事件集合。 特别是，将事件的时间戳与函数返回的dateTime进行比 **[!UICONTROL nowWithDelta]**较。

```
count(#{ExperiencePlatform.MarltonExperience.experienceevent.all(
   currentDataPackField.directMarketing.sends.value > 0 and
   currentDataPackField.timestamp > nowWithDelta(-1, "days")).timestamp}) == 0
```

如果没有与这两个条件匹配的体验事件，则结果为true。

**示例4:**

在此，我们要检查个人在过去7天中是否至少启动了一个应用程序，以便例如触发推送通知，邀请他开始教程。

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
>**[!UICONTROL currentEventField]**仅在操作事件集合和currentDataPackField时**&#x200B;可用&#x200B;**>操作数据源集合时。 在处理集合时，**[!UICONTROL all]**&#x200B;我们 **[!UICONTROL first]**会**[!UICONTROL last]**和
>循环。 **[!UICONTROL currentEventField]**和** currentDataPackField **>与所环绕的元件相对应。

**函数“first(`<condition>`)”和“last(`<condition>`)”**

该和 **[!UICONTROL first]**函**[!UICONTROL last]** 数还允许在返回满足筛选器的列表的第一个／最后一个元素时定义集合上的筛选器。

_`<listExpression>.first(<condition>)`_

_`<listExpression>.last(<condition>)`_

**示例1:**

此表达式返回与版本为1.0的手机应用程序关联的第一个推送通知令牌。

```
@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.first(currentEventField.application.version == "1.0").token
```

结果是“token_1”。

**示例2:**

此表达式返回与版本为1.0的手机应用程序关联的最后一个推送通知令牌。

```
@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.last&#8203;(currentEventField.application.version == "1.0").token}
```

结果是“token_2”。

>[!NOTE]
>
>体验事件从Experience Platform中以相反的时间顺序作为集合检索，因此：
>* **[!UICONTROL first]**函数将返回最近的事件
>* **[!UICONTROL last]**函数将返回最旧的函数。


**示例3:**

我们检查DMA ID值为非零的第一个（最新的）Adobe Analytics事件是否具有等于602的值。

```
#{ExperiencePlatform.AnalyticsProd_EvarsProps.experienceevent.first(
currentDataPackField.placeContext.geo.dmaID > 0).placeContext.geo.dmaID} == 602
```

**函数“at(`<index>`)”**

该函 **[!UICONTROL at]**数允许您根据索引引用集合中的特定元素。
索引0是集合的第一个索引。

_`<listExpression>`.at(`<index>`)_

**例如：**

此表达式返回列表的第二个推送通知令牌。

```
@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.at(1).token}
```

结果是“token_2”。