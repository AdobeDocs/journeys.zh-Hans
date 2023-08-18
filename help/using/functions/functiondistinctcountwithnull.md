---
product: adobe campaign
title: distinctCountWithNull
description: 了解函数distinctCountWithNull
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: b8380d30-160e-45c2-b187-34eb42845923
source-git-commit: 9c33474a72542b6ad1d1ae0854622dfd7575f2d9
workflow-type: tm+mt
source-wordcount: '49'
ht-degree: 32%

---

# distinctCountWithNull {#distinctCountWithNull}

计算不同值（包括空值）的数量。

## 类别

聚合

## 函数语法

`distinctCountWithNull(<listAny>)`

## 参数

| 参数 | 类型 |
|-----------|------------------|
| 列表 | listString |
| 列表 | listBoolean |
| 列表 | listInteger |
| 列表 | listDecimal |
| 列表 | listDuration |
| 列表 | listDateTime |
| 列表 | listDateTimeOnly |
| 列表 | listDateOnly |

## 签名和返回的类型

`distinctCountWithNull(<listAny>)`

返回整数。

## 示例

`distinctCountWithNull([10,2,10,null])`

返回3。
