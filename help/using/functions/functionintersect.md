---
product: adobe campaign
title: intersect
description: 瞭解函式交集
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 19a4b7f8-5636-4b8f-b81f-28ff7da99671
source-git-commit: a9a129b1949d64c4a412d3ea4002b32e3563ea96
workflow-type: tm+mt
source-wordcount: '79'
ht-degree: 12%

---

# intersect{#intersect}

傳回兩個輸入清單中的通用值。 如果兩個清單之一為Null，則傳回空白清單。

## 类别

列表

## 函式語法

`intersect(<parameters>)`

## 参数

| 参数 | 类型 |
|-----------|------------------|
| 清單1 | list |
| 清單2 | list |

## 簽章和傳回的型別

`intersect(listString,listString)`： listString
`intersect(listDecimal,listDecimal)`： listDecimal
`intersect(listInteger,listInteger)`： listInteger
`intersect(listDateTime,listDateTime)`： listDateTime
`intersect(listDateTimeOnly,listDateTimeOnly)`： listDateTimeOnly
`intersect(listDateOnly,listDateOnly)`： listDateOnly
`intersect(listDuration,listDuration)`： listDuration
`intersect(listBoolean,listBoolean)`：listBoolean

傳回清單。

## 示例

```json
intersect(
    ["sports", "news", "documentary"],
    ["sports", "movies", "documentary"]
)
```

傳回 [&quot;sports&quot;， &quot;news&quot;]

```json
intersect(
    #{ExperienceDataPlatform.profile.interests},
    ["sports", "news", "documentary"]
)
```

傳回設定檔屬性與指定類別清單之間的通用專案。

```json
intersect(
    #{ExperienceDataPlatform.profile.interests},
        @{myEvent.sport_interests}
)
```

傳回設定檔屬性和指定事件欄位之間的通用專案。
