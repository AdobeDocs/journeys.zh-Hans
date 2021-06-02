---
product: adobe campaign
title: countWithNull
description: 了解函数countWithNull
feature: 历程
role: Data Engineer
level: Experienced
exl-id: ea72dc20-8183-4661-8e08-ddb4f3727d3d
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '48'
ht-degree: 27%

---

# countWithNull {#countWithNull}

计算列表的所有元素，包括空值。

## 类别

聚合

## 函数语法

`countWithNull(<listAny>)`

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

## 签名和返回的类型

`countWithNull(<listAny>)`

返回整数。

## 示例

`count([10,2,10,null])`

返回4。
