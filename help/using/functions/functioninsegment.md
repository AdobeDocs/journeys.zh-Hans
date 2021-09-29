---
product: adobe campaign
title: inSegment
description: 了解inSegment的函数
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 7f756ec5-d787-4024-aaf8-5b4f1d4ddece
source-git-commit: e56e6f5dcb8a4680851858355ac18a70bd832b73
workflow-type: tm+mt
source-wordcount: '195'
ht-degree: 6%

---

# inSegment {#inSegment}

检查个人是否属于给定区段。

>[!NOTE]
>
>您最多可以检索100个区段。

区段名称必须是字符串常量。 它不能是字段引用或表达式。

区段在[Adobe Experience Platform](https://platform.adobe.com/segment/overview)中定义。 表达式编辑器提供了自动完成的区段列表。

区段可以具有三种状态：

* 现有：实体继续在分部中。
* 已实现：实体正在输入区段。
* 退出：实体正在退出区段。

只有具有&#x200B;**Remilated**&#x200B;和&#x200B;**Existing**&#x200B;区段参与状态的个人才会被视为区段的成员。 有关如何评估区段的更多信息，请参阅[Segmentation Service文档](https://experienceleague.adobe.com/docs/experience-platform/segmentation/tutorials/evaluate-a-segment.html?lang=en#interpret-segment-results)。

`IF inSegment('segmentName') == true` 表示您拥有已输入/现有状态的segmentMembership。

`ELSE inSegment('segmentName') == false` 表示您具有退出状态的segmentMembership。

## 类别

Adobe Experience Platform

## 函数语法

`inSegment(<parameter>)`

## 参数

| 参数 | 描述 | 类型 |
|--- |--- |--- |
| 区段 | 区段名称 | `<string>` |

## 签名和返回的类型

`inSegment(<string>)`

返回布尔值。

## 示例

`inSegment("men over 50")`

解释：

如果历程实例中的个人是名为“men over 50”的Adobe Experience Platform区段的一部分，则函数将返回&#x200B;**[!UICONTROL true]**，否则将返回&#x200B;**[!UICONTROL false]**。
