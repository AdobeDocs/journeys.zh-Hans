---
product: adobe campaign
title: toDateTime
description: 了解函数toDateTime
feature: 历程
role: Data Engineer
level: Experienced
exl-id: 0b8d1a82-a55a-4a4d-ad1b-35499d52b469
source-git-commit: 55928668cffca2f01c140a083f11ce8f57e2ee0d
workflow-type: tm+mt
source-wordcount: '94'
ht-degree: 6%

---

# toDateTime {#toDateTime}

根据参数的类型，将参数转换为日期时间值。

## 类别

转换

## 函数语法

`toDateTime(<parameters>)`

## 参数

| 参数 | 类型 |
|-----------|------------------|
| ISO-8601格式的日期时间 | 字符串 |
| 时区id | 字符串 |
| 不带时区的日期时间 | dateTimeOnly |
| 以毫秒为单位的纪元整数值 | 整数 |

>[!NOTE]
>
>时区ID必须是字符串常量。 它不能是字段引用或表达式。 有关数据类型的更多信息，请参阅[此页面](../expression/data-types.md)。

## 签名和返回的类型

`toDateTime(<string>)`

`toDateTime(<stringified time zone id>, <dateTimeOnly>)`

`toDateTime(<integer>)`

返回&#x200B;**dateTime**。

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

返回2016-08-18T23:17:59.123Z

`toDateTime(toDateTimeOnly("2016-08-18T23:17:59.123"),"UTC")`

返回2016-08-18T23:17:59.123Z

`toDateTime(1560762190189)`

返回2019-06-17T09:03:10.189Z

<!--`toDateTime ("2016-08-18T23:17:59.123", "UTC")`

Returns 2016-08-18T23:17:59.123Z.

`toDateTime("Z",2016,8,18,23,17,59)`

Returns 2016-08-18T23:17:59.000Z.

`toDateTime("Z",2016,8,18)`

Returns 2016-08-18T00:00:00.000Z.-->
