---
product: adobe campaign
solution: Journey Orchestration
title: countWithNull
description: 了解函数countWithNull
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# countWithNull {#countWithNull}

计算列表的所有元素，包括null值。

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

## 签名和返回类型

`countWithNull(<listAny>)`

返回整数。

## 示例

`count([10,2,10,null])`

返回4。
