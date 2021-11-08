---
product: adobe campaign
title: toDateOnly
description: 了解函数toDateOnly
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 19a4b7f8-5636-4b8f-b81f-28ff7da99671
source-git-commit: 5225045f02fb1b2a8505756d9d7f6f60a32b3ed6
workflow-type: tm+mt
source-wordcount: '52'
ht-degree: 21%

---

# toDateOnly{#toDateOnly}

将参数值转换为仅限日期的值。

## 类别

转化

## 函数语法

`toDateOnly(<parameters>)`

## 参数

| 参数 | 类型 |
|-----------|------------------|
| 日期格式（XDM日期格式） | 字符串 |
| 日期 | 日期 |

## 签名和返回的类型

`toDateOnly(<date>)`

`toDateOnly(<string>)`

不考虑时区而返回日期时间。

## 示例

`toDateOnly("2016-08-18")`

返回表示2016-08-18的dateOnly对象。
