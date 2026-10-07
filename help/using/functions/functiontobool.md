---
product: adobe campaign
title: toBool
description: 了解函数toBool
feature: Journeys
role: Developer
level: Experienced
exl-id: 490144c2-1ecd-4772-ab15-e23b1b7d8f0c
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
