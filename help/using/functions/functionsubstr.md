---
product: adobe campaign
title: substr
description: 瞭解函式substr
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: dda01de5-b865-4323-ac36-2e3d90d213ee
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '64'
ht-degree: 18%

---

# substr {#substr}

傳回開始索引和結束索引之間字串運算式的子字串。 如果未定義結束索引，則它介於開始索引和結束索引之間。

## 类别

字符串

## 函式語法

`substr(<parameters>)`

## 参数

| 参数 | 类型 |
|-------------|----------|
| 字符串 | 字符串 |
| beginIndex | 整数 |
| endIndex | 整数 |

## 簽章和傳回的型別

`substr(<string>,<beginIndex>)`

`substr(<string>,<beginIndex>,<endIndex>)`

傳回字串。

## 示例

`substr("Hello World",6)`

傳回「World」。

`substr("Hello World", 0, 5)`

傳回「Hello」。
