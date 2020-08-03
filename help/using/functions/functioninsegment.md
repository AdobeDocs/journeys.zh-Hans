---
title: inSegment
description: 了解inSegment的功能
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
source-git-commit: eb4474313d3c0470448f9959ed757902ef0ecd2a
workflow-type: tm+mt
source-wordcount: '106'
ht-degree: 6%

---


# inSegment {#inSegment}

检查个人是否属于给定区段。

段名称必须是字符串常数。 它不能是字段引用或表达式。

区段在Adobe Experience Platform中 [定义](https://platform.adobe.com/segment/overview)。 表达式编辑器提供区段的自动完成列表。

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

## 签名和返回类型

`inSegment(<string>)`

返回布尔值。

## 示例

`inSegment("men over 50")`

说明：

如果旅程实例 **[!UICONTROL true]** 中的个人是名为“50岁以上的男性”的Adobe Experience Platform区段的一部分，则该函数将返回，否 **[!UICONTROL false]** 则。
