---
product: adobe campaign
title: filter
description: 瞭解函式篩選器
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 3c1c188c-0ffd-44c5-b1b3-1758ed12235e
source-git-commit: a9a129b1949d64c4a412d3ea4002b32e3563ea96
workflow-type: tm+mt
source-wordcount: '109'
ht-degree: 10%

---

# filter{#filter}

傳回listObject，其中物件的索引鍵屬性符合其中一個指定的索引鍵值。

## 类别

列表

## 函式語法

`filter(<parameters>)`

## 参数

| 参数 | 类型 | 描述 |
|-----------|------------------|------------------|
| listToFilter | listObject | 要篩選的物件清單。 它必須是欄位參考。 |
| keyAttributeName | 字符串 | 指定清單物件中的屬性名稱，用來作為篩選的索引鍵 |
| keyValueList | list | 用於篩選的索引鍵值陣列 |

## 簽章和傳回的型別

`filter(listObject, string, listString)`

`filter(listObject, string, listInteger)`

`filter(listObject, string, listDecimal)`

`filter(listObject, string, listDateTime)`

`filter(listObject, string, listDateTimeOnly)`

`filter(listObject, string, listDateOnly)`

`filter(listObject, string, listDuration)`

`filter(listObject, string, listBoolean)`

傳回listObject。

## 示例

以下是在傳入事件「myevent」中傳遞的裝載範例：

```json
"productListItems": [{
   "id": "product1",
   "name": "the product 1",
   "price": 20
},{
   "id": "product2",
   "name": "the product 2",
   "price": 30
},{
   "id": "product3",
   "name": "the product 3",
   "price": 50
}]
```

您可以使用下列運算式：

```json
filter(
 @{myevent.productListItems},
 "id", 
 ["product2", "product3", "product4"]
)
```

傳回listObject，其中包含以&quot;product2&quot;和&quot;product3&quot;作為id的兩個物件。
