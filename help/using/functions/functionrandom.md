---
product: adobe campaign
title: random
description: 了解函数随机性
feature: 历程
role: Data Engineer
level: Experienced
exl-id: c47dc5f0-ea69-4814-863b-e0e483ba7770
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '52'
ht-degree: 7%

---

# 随机 {#random}

生成一个介于0和1之间的随机数。

## 类别

数学

## 函数语法

`random(<parameters>)`

## 签名和返回的类型

`random()`

返回小数。

## 示例

`#{MarltonReservation.statistics.successRatio, defaultValue : random() * 100}`

解释：如果成功率没有值/为空，则将应用默认值，该值为介于0和1 * 100（即0到100）之间的随机数。
