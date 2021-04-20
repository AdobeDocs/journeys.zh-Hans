---
product: adobe campaign
solution: Journey Orchestration
title: inSegment
description: 了解inSegment的功能
feature: Journeys
role: Data Engineer
level: Experienced
translation-type: tm+mt
source-git-commit: a99ad6a589bcd1f3083eabbcac35dd5c0497093d
workflow-type: tm+mt
source-wordcount: '153'
ht-degree: 5%

---


# inSegment {#inSegment}

检查个人是否属于给定区段。

>[!NOTE]
>
>您最多可以检索100个区段。

段名称必须是字符串常量。 它不能是字段引用或表达式。

区段在[Adobe Experience Platform](https://platform.adobe.com/segment/overview)中定义。 表达式编辑器提供了区段的自动完成列表。

>[!NOTE]
>
>只有具有&#x200B;**已实现**&#x200B;和&#x200B;**现有**&#x200B;区段参与状态的个人才会被视为区段的成员。 有关如何评估区段的详细信息，请参阅[分段服务文档](https://experienceleague.adobe.com/docs/experience-platform/segmentation/tutorials/evaluate-a-segment.html?lang=en#interpret-segment-results)。

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
