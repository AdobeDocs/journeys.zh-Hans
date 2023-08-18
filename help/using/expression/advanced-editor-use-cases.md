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

# 高级表达式示例

高级表达式编辑器可用于创建条件，以允许您在历程中筛选用户。 通过这些条件，可按时间、日期、位置、持续时间或操作（例如购买或放弃购物车）定位用户，以便在历程中重新定位他们。

>[!NOTE]
>
>事件以@开头，数据源以#开头。

## 基于体验事件构建条件

高级表达式编辑器必须对时间序列执行查询，例如消息的购买或过去点击列表。 无法使用简单编辑器执行此类查询。

体验事件将作为集合，以反向时间顺序从Adobe Experience Platform中进行检索，因此：

* 第一个函数将返回最近的事件
* last函数将返回最早的函数。

例如，假设您想定位过去7天内放弃购买购物车的客户，以便在客户接近商店时发送消息，提供有关他们想要的店内商品的优惠。

**您需要生成以下条件：**

首先，定位浏览在线商店但在过去7天内未完成订单的客户。

<!--**This expression looks for a specified value in a string value:**

`In (“addToCart”, #{field reference from experience event})`-->

**此表达式将查找过去7天内为该用户指定的所有事件：**

然后，它选择未转换为completePurchase的所有购物车事件。

>[!NOTE]
>
>要在表达式中快速插入字段，请双击编辑器左侧面板中的字段。

指定的时间戳将用作日期时间值，第二个时间戳是天数。

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

此表达式返回布尔值。

**现在，让我们构建一个表达式，检查产品是否有库存**

* 在库存中，此表达式查找产品的数量字段，并指定它应大于0。

`#{Inventory.fieldgroup3.quantity} > 0`

* 在右边，指定必要的值，这里，我们需要检索存储的位置，该位置是从事件“EndaysLumaStudio”的位置映射的：

`#{ArriveLumaStudio._acpevangelists1.location.location}`

* 并使用函数指定SKU `first` 要检索最新的“addToCart”交互，请执行以下操作：

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

从该位置，您可以在历程中添加其他路径（产品不在商店中）并发送包含参与选件的通知。 相应地配置消息并使用个性化数据增强消息目标。

## 使用高级表达式编辑器进行字符串处理的示例

**条件**

此条件仅检索在“Arlington”中触发的地理围栏事件：

```json
        @{GeofenceEntry
                    .placeContext
                    .POIinteraction
                    .POIDetail
                    .name} == "Arlington"
```

解释：这是一种严格的字符串比较（区分大小写），相当于在使用简单模式下的查询 `equal to` 替换为 `Is sensitive` 已选中。

相同的查询 `Is sensitive` 取消选中将在高级模式下生成以下表达式：

```json
        equalIgnoreCase(@{GeofenceEntry
                        .placeContext
                        .POIinteraction
                        .POIDetail
                        .name}, "Arlington")
```

**操作中**

以下表达式允许您在操作个性化字段中定义CRM ID：

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

说明：此示例使用 `substr` 和 `lastIndexOf` 用于移除在移动设备应用程序启动事件中传递的CRM ID所包含的大括号函数。

有关如何使用高级表达式编辑器的更多信息，请关注 [此视频](https://experienceleague.adobe.com/docs/platform-learn/tutorials/journey-orchestration/create-a-journey.html).
