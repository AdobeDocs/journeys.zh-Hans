---
title: toDecimal
description: 了解toDecimal的函数
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
source-git-commit: 939cde1f30a946ba4c20984dd72dcd1526d6e608
workflow-type: tm+mt
source-wordcount: '71'
ht-degree: 7%

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
| dateTime | 将日期转换为毫秒数（纪元毫秒） |
| 布尔 | 如果为true，则将布尔值转换为1；如果为false，则将布尔值转换为0 |
| 整数 | 转换为小数（示例）。: 1变为1.0) |

## 签名和返回类型

`toDecimal(<integer>)`

`toDecimal(<decimal>)`

`toDecimal(<string>)`

`toDecimal(<boolean>)`

返回十进制。

## 示例

`toDecimal("4.0")`

返回4.0。
