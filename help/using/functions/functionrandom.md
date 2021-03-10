---
product: adobe campaign
solution: Journey Orchestration
title: random
description: 了解函数随机性
feature: 历程
role: 数据工程师
level: 富有经验
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '55'
ht-degree: 5%

---


# random {#random}

生成一个介于0和1之间的随机数。

## 类别

数学

## 函数语法

`random(<parameters>)`

## 签名和返回的类型

`random()`

返回十进制。

## 示例

`#{MarltonReservation.statistics.successRatio, defaultValue : random() * 100}`

解释：如果成功率没有值/为null，则将应用默认值，并将是介于0和1 * 100（即0到100）之间的随机数。
