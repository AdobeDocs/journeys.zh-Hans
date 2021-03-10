---
product: adobe campaign
solution: Journey Orchestration
title: inSegment
description: 了解inSegment的功能
feature: 历程
role: 数据工程师
level: 富有经验
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '110'
ht-degree: 7%

---


# inSegment {#inSegment}

检查个人是否属于给定区段。

段名称必须是字符串常量。 它不能是字段引用或表达式。

区段在[Adobe Experience Platform](https://platform.adobe.com/segment/overview)中定义。 表达式编辑器提供了区段的自动完成列表。

>[!NOTE]
>
>您最多可以检索100个区段。

## 类别

Adobe Experience Platform

## 函数语法

`inSegment(<parameter>)`

## 参数

| 参数 | 说明 | 类型 |
|--- |--- |--- |
| 细分 | 区段名称 | `<string>` |

## 签名和返回的类型

`inSegment(<string>)`

返回布尔值。

## 示例

`inSegment("men over 50")`

解释：

如果旅程实例中的个人是名为“men over 50”的Adobe Experience Platform区段的一部分，则此函数将返回&#x200B;**[!UICONTROL true]**，否则返回&#x200B;**[!UICONTROL false]**。
