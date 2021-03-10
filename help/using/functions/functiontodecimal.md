---
product: adobe campaign
solution: Journey Orchestration
title: toDecimal
description: 了解toDecimal的函数
feature: 历程
role: 数据工程师
level: 富有经验
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '75'
ht-degree: 8%

---


# toDecimal {#toDecimal}

根据参数值的类型，将参数值转换为十进制值。

## 类别

转换

## 函数语法

`toDecimal(<parameter>)`

## 参数

| 参数 | 说明 |
|--- |--- |
| 字符串 | 将字符串值转换为十进制 |
| dateTime | 将日期转换为毫秒数（时间毫秒） |
| 布尔 | 如果为true，则将布尔值转换为1；如果为false，则将布尔值转换为0 |
| 整数 | 转换为小数（示例）。:1变为1.0) |

## 签名和返回的类型

`toDecimal(<integer>)`

`toDecimal(<decimal>)`

`toDecimal(<string>)`

`toDecimal(<boolean>)`

返回小数。

## 示例

`toDecimal("4.0")`

返回4.0。
