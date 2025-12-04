---
product: adobe campaign
title: toDateOnly
description: 了解函数toDateOnly
feature: Journeys
role: Developer
level: Experienced
exl-id: 2d7b132e-5ee0-4fa0-bacc-ce4c6ec7e794
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '54'
ht-degree: 16%

---

# toDateOnly{#toDateOnly}

将参数值转换为仅日期值。

## 类别

转化

## 函数语法

`toDateOnly(<parameters>)`

## 参数

| 参数 | 类型 |
|-----------|------------------|
| ISO-8601或“YYYY-MM-DD”格式的日期（XDM日期格式） | 字符串 |
| 日期 | 日期 |

## 签名和返回的类型

`toDateOnly(<date>)`

`toDateOnly(<string>)`

返回不考虑时区的日期时间。

## 示例

`toDateOnly("2016-08-18")`

返回表示2016-08-18的dateOnly对象。
