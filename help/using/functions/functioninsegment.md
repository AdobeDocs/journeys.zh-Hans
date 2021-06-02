---
product: adobe campaign
title: inSegment
description: 了解inSegment的函数
feature: 历程
role: Data Engineer
level: Experienced
exl-id: 7f756ec5-d787-4024-aaf8-5b4f1d4ddece
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '150'
ht-degree: 6%

---

# inSegment {#inSegment}

检查个人是否属于给定区段。

>[!NOTE]
>
>您最多可以检索100个区段。

区段名称必须是字符串常量。 它不能是字段引用或表达式。

区段在[Adobe Experience Platform](https://platform.adobe.com/segment/overview)中定义。 表达式编辑器提供了自动完成的区段列表。

>[!NOTE]
>
>只有具有&#x200B;**Remilated**&#x200B;和&#x200B;**Existing**&#x200B;区段参与状态的个人才会被视为区段的成员。 有关如何评估区段的更多信息，请参阅[Segmentation Service文档](https://experienceleague.adobe.com/docs/experience-platform/segmentation/tutorials/evaluate-a-segment.html?lang=en#interpret-segment-results)。

## 类别

Adobe Experience Platform

## 函数语法

`inSegment(<parameter>)`

## 参数

| 参数 | 说明 | 类型 |
|--- |--- |--- |
| 区段 | 区段名称 | `<string>` |

## 签名和返回的类型

`inSegment(<string>)`

返回布尔值。

## 示例

`inSegment("men over 50")`

解释：

如果历程实例中的个人是名为“men over 50”的Adobe Experience Platform区段的一部分，则函数将返回&#x200B;**[!UICONTROL true]**，否则将返回&#x200B;**[!UICONTROL false]**。
