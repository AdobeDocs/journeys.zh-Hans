---
product: adobe campaign
solution: Journey Orchestration
title: random
description: 了解函数随机性
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '51'
ht-degree: 5%

---


# random {#random}

生成0到1之间的随机数。

## 类别

数学

## 函数语法

`random(<parameters>)`

## 签名和返回类型

`random()`

返回十进制。

## 示例

`#{MarltonReservation.statistics.successRatio, defaultValue : random() * 100}`

说明：如果成功率没有值／为null，则将应用默认值，并将是介于0和1 * 100（即0到100）之间的随机数。
