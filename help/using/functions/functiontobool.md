---
product: adobe campaign
solution: Journey Orchestration
title: toBool
description: 了解toBool的函数
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '74'
ht-degree: 5%

---


# toBool {#toBool}

根据参数值的类型，将参数值转换为布尔值。

* 从字符串：尝试将字符串值转换为布尔值，如果字符串值为“true”，则从“true”转换为false，否则从“true”转换为“false”
* 从数字：如果数值不等于0，则为true；否则为false

## 类别

转换

## 函数语法

`toBool(<parameter>)`

## 参数

* 小数
* 布尔
* 字符串
* 整数

## 签名和返回类型

`toBool(<decimal>)`

`toBool(<boolean>)`

`toBool(<string>)`

`toBool(<integer>)`

返回布尔值。

## 示例

`toBool("true")`

`toBool(1)`

返回true。

`toBool("this is not a boolean")`

返回false。
