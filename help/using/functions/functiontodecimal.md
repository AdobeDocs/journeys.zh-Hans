---
product: adobe campaign
title: toDecimal
description: 了解toDecimal函数
feature: Journeys
role: Developer
level: Experienced
exl-id: 11d7013c-2190-4654-8466-920861c836f5
product_v2:
  - id: cf67d108-ecf9-4fde-af49-3a3c39083bc8
    internal-label: Journey Orchestration
feature_v2:
  - id: 7de3230f-9523-5ba5-8d5c-2313288b27ef
    internal-label: Journeys
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 255cd6677e7c9ebff63ea9a1028a042c19e63ecc
workflow-type: tm+mt
source-wordcount: '76'
ht-degree: 14%
---
# toDecimal {#toDecimal}

根据类型将参数值转换为十进制值。

## 类别

转化

## 函数语法

`toDecimal(<parameter>)`

## 参数

| 参数 | 说明 |
|--- |--- |
| 字符串 | 将字符串值转换为小数 |
| dateTime | 将日期转换为毫秒数（纪元毫秒） |
| 布尔 | 如果为true，则将布尔值转换为1；如果为false，则将布尔值转换为0 |
| 整数 | 转换为小数（示例： 1变为1.0） |

## 签名和返回的类型

`toDecimal(<integer>)`

`toDecimal(<decimal>)`

`toDecimal(<string>)`

`toDecimal(<boolean>)`

返回小数。

## 示例

`toDecimal("4.0")`

返回4.0。
