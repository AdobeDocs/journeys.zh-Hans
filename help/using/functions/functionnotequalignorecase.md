---
product: adobe campaign
solution: Journey Orchestration
title: notEqualWithIgnoreCase
description: 了解函数notEqualWithIgnoreCase
feature: 历程
role: 数据工程师
level: 富有经验
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '41'
ht-degree: 12%

---


# notEqualWithIgnoreCase {#notEqualWithIgnoreCase}

检查具有第二个参数字符串的第一个参数字符串是否不同，忽略大小写注意事项。

## 类别

字符串

## 函数语法

`notEqualWithIgnoreCase(<parameters>)`

## 参数

* 字符串

## 签名和返回的类型

`notEqualWithIgnoreCase(<string>,<string>)`

返回布尔值。

## 示例

`notEqualWithIgnoreCase(@{iOSPushPermissionAllowed.device.model}, "iPad"))`
