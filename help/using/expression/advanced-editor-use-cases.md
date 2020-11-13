---
title: 使用高级表达式编辑器
description: 了解如何构建高级表达式
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: benzaama
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: 2af6e632461a8c01451f96c121469c9a32ae7f32
workflow-type: tm+mt
source-wordcount: '494'
ht-degree: 2%

---


# 高级表达式示例

高级表达式编辑器可用于创建条件，以便在旅程中过滤用户。 通过这些条件，您可以按时间、日期、地点、持续时间或诸如购买或放弃购物车等操作目标用户，以便在旅程中重新定位用户。

>[!NOTE]
>
>事件开始带@，数据源带#。

## 在体验事件上构建条件

高级表达式编辑器是对时间序列执行查询(如购买列表或过去单击消息)的必备工具。 无法使用简单编辑器执行此类查询。

体验事件从Adobe Experience Platform以相反的时间顺序作为集合进行检索，因此：

* 第一个函数将返回最近的事件
* 最后一个函数将返回最旧的函数。

例如，假设您希望在过去7天内目标客户放弃购物车，以便在客户接近商店时发送消息，并且优惠他想要在商店内的商品。

**您需要构建以下条件：**

首先，目标客户浏览了在线商店，但在过去7天内未完成订单。

<!--**This expression looks for a specified value in a string value:**

`In (“addToCart”, #{field reference from experience event})`-->

**此表达式查找此用户在过去7天中指定的所有事件:**

然后，它选择所有未转换为completePurchase的addtocart事件。

>[!NOTE]
>
>要快速在表达式中插入字段，请多次单击编辑器左面板中的字段。

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

此表达式返回布尔值。

**现在，让我们构建一个表达式检查产品是否已库存**

* 在库存中，此表达式查找产品的数量字段并指定它应大于0。

`#{Inventory.fieldgroup3.quantity} > 0`

* 在右侧，指定了必要的值，此处，我们需要检索商店的位置，该位置从事件“ArriveLumaStudio”的位置进行映射：

`#{ArriveLumaStudio._acpevangelists1.location.location}`

* 然后指定SKU，使用该函 `first` 数检索最近的“addToCart”交互：

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

从此处，您可以在产品不在商店的旅程中添加其他路径，并通过参与优惠发送通知。 相应地配置消息，并使用个性化数据来增强消息目标。

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

说明：这是严格字符串比较（区分大小写），等同于在简单模式下使用选中项的 `equal to` 查询 `Is sensitive` 符。

未选中的同一查询 `Is sensitive` 将在高级模式下生成以下表达式:

```
        equalIgnoreCase(@{GeofenceEntry
                        .placeContext
                        .POIinteraction
                        .POIDetail
                        .name}, "Arlington")
```

**实际操作情况**

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

说明：此示例使用 `substr` 和函 `lastIndexOf` 数删除花括号，该花括号用于将随移动应用程序启动事件传递的CRM ID括起来。

有关如何使用高级表达式编辑器的更多信息，请观 [看此视频](https://docs.adobe.com/content/help/en/platform-learn/tutorials/journey-orchestration/create-a-journey.html)。
