---
product: adobe campaign
title: toDecimal
description: 了解toDecimal函数
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 11d7013c-2190-4654-8466-920861c836f5
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '71'
ht-degree: 15%

---

# toDecimal {#toDecimal}

根据参数值的类型，将其转换为小数值。

## 类别

转化

## 函数语法

`toDecimal(<parameter>)`

## 参数

| 参数 | 描述 |
|--- |--- |
| 字符串 | 将字符串值转换为小数 |
| dateTime | 将日期转换为毫秒数（纪元毫秒） |
| 布尔 | 将布尔值转换为1（如果为true），0（如果为false） |
| 整数 | 转换为小数（示例）。：1变为1.0) |

## 签名和返回的类型

`toDecimal(<integer>)`

`toDecimal(<decimal>)`

`toDecimal(<string>)`

`toDecimal(<boolean>)`

返回小数。

## 示例

`toDecimal("4.0")`

返回4.0。
