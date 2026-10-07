---
product: adobe campaign
title: containIgnoreCase
description: 了解函数containIgnoreCase
feature: Journeys
role: Developer
level: Experienced
exl-id: ebec646e-9dbb-4432-a430-ab69fb7d75cf
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
source-wordcount: '48'
ht-degree: 22%
---
# containIgnoreCase {#containIgnoreCase}

检查第二个参数字符串是否包含在第一个参数字符串中，而不考虑大小写。

## 类别

字符串

## 函数语法

`containIgnoreCase(<parameters>)`

## 参数

| 参数 | 类型 |
|-----------|------------------|
| 字符串 | 字符串 |
| 搜索字符串 | 字符串 |

## 签名和返回的类型

`containIgnoreCase(<string>,<string>)`

返回布尔值。

## 示例

`containIgnoreCase("rowing is great", "GREAT")`

返回真。
