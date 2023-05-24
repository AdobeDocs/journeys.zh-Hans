---
product: adobe campaign
title: toDateTime
description: 瞭解函式toDateTime
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 0b8d1a82-a55a-4a4d-ad1b-35499d52b469
source-git-commit: 2aa73498f44f22a70bb2268afca7d1a62e434542
workflow-type: tm+mt
source-wordcount: '93'
ht-degree: 11%

---

# toDateTime {#toDateTime}

根據引數的型別，將其轉換為日期時間值。

## 类别

转化

## 函式語法

`toDateTime(<parameters>)`

## 参数

| 参数 | 类型 |
|-----------|------------------|
| ISO-8601格式的日期時間 | 字符串 |
| 時區id | 字符串 |
| 沒有時區的日期時間 | dateTimeOnly |
| 紀元的整數值（以毫秒為單位） | 整数 |

>[!NOTE]
>
>時區ID必須是字串常數。 它不能是欄位參考或運算式。 如需資料型別的詳細資訊，請參閱 [此頁面](../expression/data-types.md).

## 簽章和傳回的型別

`toDateTime(<string>)`

`toDateTime(<stringified time zone id>, <dateTimeOnly>)`

`toDateTime(<integer>)`

傳回 **dateTime**.

<!--`toDateTime(<year>,<month>,<dayOfMonth>,<hour>,<minute>,<second>)`

Returns a date time with default time zone UTC.

`toDateTime(<year>,<month>,<dayOfMonth>)`
`toDateTime(<stringified timeZone>,<year>,<month>,<dayOfMonth>)`
`toDateTime(<timeZone>,<year>,<month>,<dayOfMonth>)`

Return a datetime where hour, minute and second set to 0.

`toDateTime(<stringified timeZone>,<year>,<month>,<dayOfMonth>,<hour>,<minute>,<second>)`
`toDateTime(<string>)`
`toDateTime(<string>,<integer>)`
`toDateTime(<stringified timeZone>,<dateTimeOnly)`

`toDateTime(<timeZone>,<integer>)`

Return a datetime.

-->

## 示例

`toDateTime ("2016-08-18T23:17:59.123Z")`

傳回2016-08-18T23:17:59.123赫

`toDateTime(toDateTimeOnly("UTC", "2016-08-18T23:17:59.123"))`

傳回2016-08-18T23:17:59.123赫

`toDateTime(1560762190189)`

傳回2019-06-17T09:03:10.189盎司

<!--`toDateTime ("2016-08-18T23:17:59.123", "UTC")`

Returns 2016-08-18T23:17:59.123Z.

`toDateTime("Z",2016,8,18,23,17,59)`

Returns 2016-08-18T23:17:59.000Z.

`toDateTime("Z",2016,8,18)`

Returns 2016-08-18T00:00:00.000Z.-->
