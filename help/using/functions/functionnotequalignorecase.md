---
product: adobe campaign
title: notEqualWithIgnoreCase
description: 了解函数notEqualWithIgnoreCase
feature: 历程
role: Data Engineer
level: Experienced
exl-id: d99601cf-2ba8-4150-afa7-df6b8af47bf6
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '38'
ht-degree: 15%

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
