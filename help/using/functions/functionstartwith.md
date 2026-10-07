---
product: adobe campaign
title: startWith
description: 了解函数startWith
feature: Journeys
role: Developer
level: Experienced
exl-id: bf0e75d6-cc7c-4a76-b215-8735eb62163b
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
source-wordcount: '43'
ht-degree: 25%
---
# startWith {#startWith}

如果第二个参数是第一个参数的前缀，则返回true。

## 类别

字符串

## 函数语法

`startWith(<parameters>)`

## 参数

| 参数 | 类型 |
|-------------|--------|
| 字符串 | 字符串 |
| 前缀 | 字符串 |

## 签名和返回的类型

`startWith(<string>,<string>)`

返回布尔值。

## 示例

`startWith("Hello World", "Hello")`

返回真。

`startWith("Hello World", "World")`

返回假。
