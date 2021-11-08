---
product: adobe campaign
title: 使用高级表达式编辑器
description: 了解如何构建高级表达式
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 724ae59e-d1b5-4de9-b140-d37064e22ac6
source-git-commit: 601bed30d3c414f03c60ef52c787372e778dee54
workflow-type: tm+mt
source-wordcount: '492'
ht-degree: 2%

---

# 高级表达式示例

高级表达式编辑器可用于创建条件，以便在历程中筛选用户。 这些条件允许您根据时间、日期、位置、持续时间或操作（如购买或放弃购物）来定位用户，以便在历程中重新定位用户。

>[!NOTE]
>
>事件以@开头，数据源以#开头。

## 基于体验事件构建条件

高级表达式编辑器对于对时间序列（如购买列表或对消息的过去点击）执行查询是强制性的。 无法使用简单编辑器执行此类查询。

体验事件是作为收藏集从Adobe Experience Platform中以时间顺序进行检索，因此：

* 第一个函数将返回最近的事件
* 最后一个函数将返回最早的一个函数。

例如，假设您想要定位过去7天内购物车放弃的客户，以便当客户接近商店时发送消息，并针对他想要的商店内商品提供优惠。

**您需要构建以下条件：**

首先，定位那些浏览了在线商店但在过去7天内未完成订单的客户。

<!--**This expression looks for a specified value in a string value:**

`In (“addToCart”, #{field reference from experience event})`-->

**此表达式会查找此用户在过去7天中指定的所有事件：**

然后，选择所有未转换为completePurchase的addtocart事件。

>[!NOTE]
>
>要在表达式中快速插入字段，请双击编辑器左侧面板中的字段。

指定的时间戳将用作日期时间值，第二个是天数。

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

此表达式返回一个布尔值。

**现在，让我们构建一个检查产品是否有现货的表达式**

* 在“库存”中，此表达式会查找产品的数量字段，并指定其应大于0。

`#{Inventory.fieldgroup3.quantity} > 0`

* 在右侧，指定了必需的值，在此，我们需要检索存储的位置，该位置是从事件“ArmiLumaStudio”的位置映射的：

`#{ArriveLumaStudio._acpevangelists1.location.location}`

* 然后，使用函数指定SKU `first` 要检索最近的“addToCart”交互，请执行以下操作：

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

从此处，您可以在历程中为（当产品不在商店时）添加其他路径，并通过参与选件发送通知。 相应地配置消息，并使用个性化数据来增强消息目标。

## 使用高级表达式编辑器处理字符串的示例

**条件**

此条件仅检索在“Arlington”中触发的地理围栏事件：

```json
        @{GeofenceEntry
                    .placeContext
                    .POIinteraction
                    .POIDetail
                    .name} == "Arlington"
```

解释：这是严格的字符串比较（区分大小写），等同于使用 `equal to` with `Is sensitive` 选中。

同一查询 `Is sensitive` 取消选中后，将在高级模式下生成以下表达式：

```json
        equalIgnoreCase(@{GeofenceEntry
                        .placeContext
                        .POIinteraction
                        .POIDetail
                        .name}, "Arlington")
```

**操作**

以下表达式允许您在操作个性化字段中定义CRM ID:

```json
    substr(@{MobileAppLaunch
            ._myorganization
            .identification
            .crmid}, 1, 
            lastIndexOf(@{MobileAppLaunch
                        ._myorganization
                        .identification
                        .crmid}
                         ))
```

解释：此示例使用 `substr` 和 `lastIndexOf` 用于删除与移动设备应用程序启动事件一起传递的CRM ID周围大括号的函数。

有关如何使用高级表达式编辑器的更多信息，请观看 [此视频](https://experienceleague.adobe.com/docs/platform-learn/tutorials/journey-orchestration/create-a-journey.html).
