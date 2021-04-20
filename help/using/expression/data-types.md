---
product: adobe campaign
solution: Journey Orchestration
title: 数据类型
description: 了解高级表达式中的数据类型
feature: Journeys
role: Data Engineer
level: Experienced
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '562'
ht-degree: 4%

---


# 数据类型 {#concept_gp3_rj5_dgb}

从技术上讲，常量始终包含数据类型。 在文本表达式中，我们只指定值。 数据类型可从值（例如字符串、整数、小数等）推断出来。 对于日期时间等特定情况，我们使用专门的函数进行表示。

以下各节提供了有关不同数据类型表达式及其表示方式的信息。

## 字符串{#string}

**说明**

常用字符序列。 除了来自环境的隐式大小（如可用内存量）之外，它没有任何特定大小。

JSON格式：字符串

序列化格式：UTF-8

**文本表示**

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

## 整数{#integer}

**说明**

从–2^63到2^63-1的整数值。

JSON格式：数字

**文本表示**

```
<integer value>
```

**示例**

```
42
```

## 小数{#decimal}

**说明**

小数。 它表示浮动值：

* 类型多次的最大正有限值，(2-2^-52)x2^1023
* 类型多次的最小正常值，2-1022
* 类型多次的最小正非零值，2 p-1074

JSON格式：数字

序列化格式：使用“。” 作为小数分隔符。

**文本表示**

```
<integer value>.<integer value>
```

**示例**

```
3.14
```

## 布尔值{#boolean}

**说明**

写入小写的布尔值：true或false

JSON格式：布尔值

**文本表示**

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

## dateTimeOnly {#date-time-only}

**说明**

表示没有时区的日期时间，被视为年月 — 小时 — 分钟 — 毫秒。

它不存储或表示时区。 相反，它是对日期的描述，与墙上钟上显示的本地时间相结合。

如果没有其他信息（如偏移或时区），它不能表示时间线上的即时。

序列化格式：ISO-8601扩展的偏移日期时间格式。

它使用DateTimeFormatter ISO_LOCAL_DATE_TIME反序列化和序列化值。 [了解详情](https://docs.oracle.com/javase/8/docs/api/java/time/format/DateTimeFormatter.html#ISO_LOCAL_DATE_TIME&quot;)

**文本表示**

```
toDateTimeOnly("<dateTimeOnly in ISO-8601 format>")  
```

## dateTime {#date-time}

**说明**

同时考虑时区的日期时间常数。 它表示一个距UTC偏移的日期时间。

该偏移可被视为具有该偏移的附加信息的即时。 这是一种在世界某个地方代表一个特定“时刻”的方式。

JSON格式：字符串。

它必须封装在toDateTime函数中。

序列化格式：ISO-8601扩展的偏移日期时间格式。

它使用DateTimeFormatter ISO_OFFSET_DATE_TIME反序列化和序列化值。 [了解详情](https://docs.oracle.com/javase/8/docs/api/java/time/format/DateTimeFormatter.html#ISO_OFFSET_DATE_TIME)

您还可以传递传递一个传递新纪元值的整数。 [阅读更多](https://www.epochconverter.com)

时区可以由偏移或时区代码指定(例如：欧洲/巴黎，Z — 表示UTC)。

**文本表示**

```
toDateTime("<dateTime in ISO-8601 format>")
```

```
toDateTime(<integer value of an epoch in milliseconds>)
```

**示例**

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

## 持续时间{#duration}

**说明**

它表示基于时间的时间量，如“34.5秒”。 它以毫秒为单位来建模数量或时间。

支持的时间单位为：毫秒、秒、分钟、小时、天，其中一天等于24小时。 年份和月份不受支持，因为它们不是固定的时间。

JSON格式：字符串。

它必须封装在toDuration函数中。

序列化格式：要反序列化时区ID，它使用java函数java.time。

Duration.parse:接受的格式基于ISO-8601持续时间格式PnDTnHnMn.nS，其天数被认为正好24小时。 [了解详情](https://docs.oracle.com/javase/8/docs/api/java/time/Duration.html#parse-java.lang.CharSequence-)

**文本表示**

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

## 列表{#list}

**说明**

以逗号分隔的表达式列表，使用方括号作为分隔符。

不支持多态，因此列表中包含的所有表达式应具有相同的类型。

**文本表示**

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
