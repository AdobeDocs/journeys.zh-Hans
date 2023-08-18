---
product: adobe campaign
title: inSegment
description: 了解inSegment中的函数
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

区段名称必须是字符串常量。 它不能是字段引用，也不能是表达式。

区段在下文中定义： [Adobe Experience Platform](https://platform.adobe.com/segment/overview). 表达式编辑器提供自动完成的区段列表。

区段可以具有三种状态：

* 现有：实体继续位于区段中。
* 已实现：实体正在进入分部。
* 退出：实体正在退出区段。

仅具有 **已实现** 和 **现有** 区段参与状态将被视为区段的成员。 有关如何评估区段的更多信息，请参阅 [Segmentation Service文档](https://experienceleague.adobe.com/docs/experience-platform/segmentation/tutorials/evaluate-a-segment.html?lang=en#interpret-segment-results).

`IF inSegment('segmentName') == true` 表示您拥有segmentMembership且状态为entered/existing。

`ELSE inSegment('segmentName') == false` 表示您具有已退出状态的segmentMembership。

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

解释:

函数将返回 **[!UICONTROL true]** 如果旅程实例中的个人是名为“50岁以上的男性”的Adobe Experience Platform区段的一部分， **[!UICONTROL false]** 否则。
