---
product: adobe campaign
solution: Journey Orchestration
title: 使用高级表达式编辑器
description: 了解如何构建高级表达式
feature: 历程
role: 数据工程师
level: 富有经验
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '498'
ht-degree: 2%

---


# 高级表达式示例

高级表达式编辑器可用于创建条件，以便在您的旅程中过滤用户。 这些条件使您能够按时间、日期、地点、持续时间或诸如购买或放弃购物车等操作目标用户，以便在旅程中重新定位用户。

>[!NOTE]
>
>事件带@的开始，带#的数据源。

## 在体验事件上构建条件

高级表达式编辑器是对时间系列执行查询(如购买列表或过去对消息的单击)的必备工具。 无法使用简单的编辑器执行此类查询。

体验事件从Adobe Experience Platform中以收藏的形式按时间顺序反向检索，因此：

* first函数将返回最近的事件
* 最后一个函数将返回最旧的函数。

例如，假设您希望在过去7天内目标客户放弃购物车，以便在客户接近商店时发送消息，并优惠他想要在商店购买的商品。

**您需要构建以下条件：**

首先，目标客户浏览了在线商店，但在过去7天内没有完成订单。

<!--**This expression looks for a specified value in a string value:**

`In (“addToCart”, #{field reference from experience event})`-->

**此表达式查找此用户在过去7天内指定的所有事件:**

然后，它选择所有未转换为completePurchase的addtocart事件。

>[!NOTE]
>
>要在表达式中快速插入字段，请按住多次单击编辑器左面板中的字段。

指定的时间戳用作日期时间值，第二个是天数。

```
        In( “addToCart”, #{ExperiencePlatformDataSource
                        .ExperienceEventFieldGroup
                        .experienceevent
                        .all(
                        inLastDays(currentDataPackField.timestamp, 7 ))
                        .productData
                        .productInteraction})
        And
        Not(In( “completePurchase”, #{ExperiencePlatformDataSource
                        .ExperienceEventFieldGroup
                        .experienceevent
                        .all(
                        inLastDays(currentDataPackField.timestamp, 7 ))
                        .productData
                        .productInteraction})
```

此表达式返回一个布尔值。

**现在，让我们构建一个表达式检查，检查产品是否有现车**

* 在库存中，此表达式查找产品的数量字段并指定它应大于0。

`#{Inventory.fieldgroup3.quantity} > 0`

* 在右侧，指定了必要的值，此处，我们需要检索存储的位置，该位置是从事件“ArriveLumaStudio”的位置映射的：

`#{ArriveLumaStudio._acpevangelists1.location.location}`

* 然后指定SKU，使用函数`first`检索最新的“addToCart”交互：

   ```
       #{ExperiencePlatformDataSource
                       .ExperienceEventFieldGroup
                       .experienceevent
                       .first(
                       currentDataPackField
                       .productData
                       .productInteraction == “addToCart”
                       )
                       .SKU}
   ```

从此处，您可以在产品不在商店时的旅程中添加其他路径，并通过参与优惠发送通知。 相应地配置消息并使用个性化数据增强消息目标。

## 使用高级表达式编辑器处理字符串的示例

**条件**

此条件仅检索在“Arlington”中触发的地理事件:

```
        @{GeofenceEntry
                    .placeContext
                    .POIinteraction
                    .POIDetail
                    .name} == "Arlington"
```

解释：这是严格的字符串比较（区分大小写），等同于在选中`Is sensitive`且使用`equal to`的简单模式下的查询。

取消选中`Is sensitive`的同一查询将在高级模式下生成以下表达式:

```
        equalIgnoreCase(@{GeofenceEntry
                        .placeContext
                        .POIinteraction
                        .POIDetail
                        .name}, "Arlington")
```

**实际操作**

以下表达式允许您在操作个性化字段中定义CRM ID:

```
    substr(@{MobileAppLaunch
            ._myorganization
            .identification
            .crmid}, 1, 
            lastIndexOf(@{MobileAppLaunch
                        ._myorganization
                        .identification
                        .crmid}
                         }
                         ))
```

解释：此示例使用`substr`和`lastIndexOf`函数删除花括号，这些花括号括住随移动应用程序启动事件传递的CRM ID。

有关如何使用高级表达式编辑器的详细信息，请观看[此视频](https://docs.adobe.com/content/help/en/platform-learn/tutorials/journey-orchestration/create-a-journey.html)。
