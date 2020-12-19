---
product: adobe campaign
solution: Journey Orchestration
title: notEqualWithIgnoreCase
description: 了解函数notEqualWithIgnoreCase
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# notEqualWithIgnoreCase {#notEqualWithIgnoreCase}

检查带有第二个参数字符串的第一个参数字符串是否不同，忽略大小写注意事项。

## 类别

字符串

## 函数语法

`notEqualWithIgnoreCase(<parameters>)`

## 参数

* 字符串

## 签名和返回类型

`notEqualWithIgnoreCase(<string>,<string>)`

返回布尔值。

## 示例

`notEqualWithIgnoreCase(@{iOSPushPermissionAllowed.device.model}, "iPad"))`
