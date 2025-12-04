---
product: adobe campaign
title: toBool
description: 了解函数toBool
feature: Journeys
role: Developer
level: Experienced
exl-id: 490144c2-1ecd-4772-ab15-e23b1b7d8f0c
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '75'
ht-degree: 12%

---

# toBool {#toBool}

根据类型将参数值转换为布尔值。

* 从字符串：尝试将字符串值转换为布尔值；如果字符串值为“true”，则从“true”；否则从“false”
* 从数值：如果数值不等于0，则为true；否则为false

## 类别

转化

## 函数语法

`toBool(<parameter>)`

## 参数

* 小数
* 布尔
* 字符串
* 整数

## 签名和返回的类型

`toBool(<decimal>)`

`toBool(<boolean>)`

`toBool(<string>)`

`toBool(<integer>)`

返回布尔值。

## 示例

`toBool("true")`

`toBool(1)`

返回真。

`toBool("this is not a boolean")`

返回假。
