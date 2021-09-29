---
product: adobe campaign
title: 数据类型
description: 了解高级表达式中的数据类型
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 343f61b8-2315-4971-8b2b-6aa815bd9ced
source-git-commit: 0b4d925410e1ab4895f27455eb082dd9cc305cff
workflow-type: tm+mt
source-wordcount: '636'
ht-degree: 5%

---

# 数据类型 {#concept_gp3_rj5_dgb}

从技术上讲，常量始终包含数据类型。 在文本表达式中，我们仅指定值。 数据类型可以从值（例如，字符串、整数、小数等）推断。 对于日期时间等特定情况，我们使用专用函数来表示。

以下各节提供了有关不同数据类型表达式及其表示方式的信息。

## 字符串 {#string}

**描述**

常见字符序列。 除了来自环境的隐式大小（如可用内存量）之外，它没有任何特定大小。

JSON格式：字符串

序列化格式：UTF-8

**文字表示**

```
"<value>"
```

```
'<value>'
```

**示例**

```
"hello world"
```

```
'hello world'
```

## 整数 {#integer}

**描述**

从–2^63到2^63-1的整数值。

JSON格式：数值

**文字表示**

```
<integer value>
```

**示例**

```
42
```

## 小数 {#decimal}

**描述**

小数. 它表示浮动值：

* 双(2-2^-52)x2^1023型最大正有限值
* 双型、2-1022型的最小正常值
* 双型、2p-1074型最小正非零值

JSON格式：数值

序列化格式：使用“。” 作为小数分隔符。

**文字表示**

```
<integer value>.<integer value>
```

**示例**

```
3.14
```

## 布尔 {#boolean}

**描述**

小写的布尔值：true或false

JSON格式：布尔值

**文字表示**

```
true
```

```
false
```

**示例**

```
true
```

## dateOnly {#date-only}

**描述**

仅表示不带时区的日期（视为年月日）。

日期描述，用于生日。

JSON格式：字符串。

格式为：YYYY-MM-DD(ISO-8601)，例如：&quot;2021-03-11&quot;。

它可以封装在toDateOnly函数中。

它使用DateTimeFormatter ISO_LOCAL_DATE_TIME反序列化和序列化值。 [了解详情](https://datatracker.ietf.org/doc/html/rfc3339#section-5.6)

**文字表示**

```
date("<dateOnly in ISO-8601 format>")  
```

**示例**

```
date("2021-02-19")
```

## dateTimeOnly {#date-time-only}

**描述**

表示不带时区的日期时间，以年月日每小时分钟每秒的毫秒为单位进行查看。

JSON格式：字符串。

它不存储或表示时区。 相反，它是日期的描述，用于生日，与在墙上钟上看到的当地时间相结合。

如果没有其他信息（如偏移或时区），它无法在时间线上表示即时。

它可以封装在toDateTimeOnly函数中。

序列化格式：ISO-8601扩展的偏移日期时间格式。

它使用DateTimeFormatter ISO_LOCAL_DATE_TIME反序列化和序列化值。 [了解详情](https://docs.oracle.com/javase/8/docs/api/java/time/format/DateTimeFormatter.html#ISO_LOCAL_DATE_TIME&quot;)

**文字表示**

```
date("<dateTimeOnly in ISO-8601 format>")  
```

**示例**

```
date("2021-02-19T00.00.000")
date("2021-02-19T00.00")
```

## dateTime {#date-time}

**描述**

也考虑时区的日期时间常量。 它表示一个与UTC有偏移的日期时间。

它可以被视为具有偏移的附加信息的即时。 这是一种在世界某个地方代表一个特定“时刻”的方式。

JSON格式：字符串。

它可以封装在toDateTime函数中。

序列化格式：ISO-8601扩展的偏移日期时间格式。

它使用DateTimeFormatter ISO_OFFSET_DATE_TIME反序列化和序列化值。 [了解详情](https://docs.oracle.com/javase/8/docs/api/java/time/format/DateTimeFormatter.html#ISO_OFFSET_DATE_TIME)

您还可以传递传递传递新纪元值的整数。 [了解更多信息](https://www.epochconverter.com)

时区可以由偏移或时区代码指定(例如：欧洲/巴黎，Z — 表示UTC)。

**文字表示**

```
toDateTime("<dateTime in ISO-8601 format>")
```

```
date("<dateTime in ISO-8601 format>")
```

```
toDateTime(<integer value of an epoch in milliseconds>)
```

**示例**

```
date("2021-02-19T00.00.000Z")
```

```
toDateTime("1977-04-22T06:00:00Z")
```

```
toDateTime("2011-12-03T15:15:30Z")
```

```
toDateTime("2011-12-03T15:15:30.123Z")
```

```
toDateTime("2011-12-03T15:15:30.123+02:00")
```

```
toDateTime("2011-12-03T15:15:30.123-00:20")
```

```
toDateTime(1560762190189)
```

## 持续时间 {#duration}

**描述**

它表示基于时间的时长，如“34.5秒”。 它以毫秒为单位来建模数量或时间量。

支持的临时单元包括：一天等于24小时的毫秒、秒、分钟、小时、天。 年份和月份不受支持，因为它们不是固定的时间。

JSON格式：字符串。

它必须封装在toDuration函数中。

序列化格式：要反序列化时区ID，它使用java函数java.time。

持续时间.parse:所接受的格式以ISO-8601持续时间格式PnDTnHnMn.nS为基础，天数被认为恰好为24小时。 [了解详情](https://docs.oracle.com/javase/8/docs/api/java/time/Duration.html#parse-java.lang.CharSequence-)

**文字表示**

```
toDuration("<duration in ISO-8601 format>")
```

```
toDuration(<duration in milliseconds>)
```

**示例**

```
toDuration("PT5S") -- parses as 5 seconds
```

```
toDuration(500) -- parses as 500ms
```

```
toDuration("PT20.345S") -- parses as "20.345 seconds"
```

```
toDuration("PT15M") -- parses as "15 minutes" (where a minute is 60 seconds)
```

```
toDuration("PT10H")  -- parses as "10 hours" (where an hour is 3600 seconds)
```

```
toDuration("P2D") -- parses as "2 days" (where a day is 24 hours or 86400 seconds)
```

```
toDuration("P2DT3H4M") -- parses as "2 days, 3 hours and 4 minutes"
```

```
toDuration("P-6H3M") -- parses as "-6 hours and +3 minutes"
```

```
toDuration("-P6H3M") -- parses as "-6 hours and -3 minutes"
```

```
toDuration("-P-6H+3M") -- parses as "+6 hours and -3 minutes"
```

## list {#list}

**描述**

使用方括号作为分隔符的表达式列表（以逗号分隔）。

不支持多态性，因此列表中包含的所有表达式都应具有相同的类型。

**文字表示**

```
[<expression>, <expression>, ... ]
```

**示例**

```
["value1","value2"]
```

```
[3,5]
```

```
[toDuration(500),toDuration(800)]
```
