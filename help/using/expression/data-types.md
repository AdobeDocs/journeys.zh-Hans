---
product: adobe campaign
solution: Journey Orchestration
title: 数据类型
description: 了解高级表达式中的数据类型
translation-type: tm+mt
source-git-commit: f755f92d0479e2889dd7ed6dfa5e72d52c25634f
workflow-type: tm+mt
source-wordcount: '614'
ht-degree: 4%

---


# 数据类型 {#concept_gp3_rj5_dgb}

从技术上讲，常数始终包含数据类型。 在文本表达式中，我们只指定值。 数据类型可从值（例如字符串、整数、小数等）推断出来。 对于日期时间等特定情况，我们使用专门的函数来表示。

以下各节提供了有关不同数据类型表达式及其表示方式的信息。

## 字符串 {#string}

**说明**

常用字符序列。 除了来自环境的隐式大小（如可用内存量）之外，它没有任何特定大小。

JSON格式：字符串

序列化格式：UTF-8

**文本表示**

```"<value>"```

```'<value>'```

**示例**

```"hello world"```

```'hello world'```

## 整数 {#integer}

**说明**

从-2^63到2^63-1的整数值。

JSON格式：数字

**文本表示**

```<integer value>```

**示例**

```42```

## 小数 {#decimal}

**说明**

小数。 它表示浮动值：

* 多次类型的最大正有限值，(2-2^-52)x2^1023
* 多次型最小正常值，2-1022
* 类型多次的最小正非零值，2 p-1074

JSON格式：数字

序列化格式：使用“.” 作为小数分隔符。

**文本表示**

```<integer value>.<integer value>```

**示例**

```3.14```

## 布尔 {#boolean}

**说明**

布尔值写小写：true或false

JSON格式：布尔值

**文本表示**

```true```

```false```

**示例**

```true```

## dateTimeOnly {#date-time-only}

**说明**

表示没有时区的日期时间，视为年月日时（分钟）（毫秒）。

它不存储或表示时区。 相反，它是日期的描述，与墙上钟显示的当地时间相结合。

如果没有其他信息（如偏移或时区），它不能表示时间线上的即时。

序列化格式：ISO-8601扩展的偏移日期时间格式。

它使用DateTimeFormatter ISO_LOCAL_DATE_TIME反序列化和序列化值。 [了解详情](https://docs.oracle.com/javase/8/docs/api/java/time/format/DateTimeFormatter.html#ISO_LOCAL_DATE_TIME&quot;)

**文本表示**

```toDateTimeOnly("<dateTimeOnly in ISO-8601 format>")  ```

## dateTime {#date-time}

**说明**

日期时间常数，也考虑时区。 它表示一个距UTC有偏移的日期时间。

它可以即时查看，并附加偏移信息。 是在世界某个地方代表一个特定&quot;时刻&quot;的一种方式。

JSON格式：字符串。

它必须封装在toDateTime函数中。

序列化格式：ISO-8601扩展的偏移日期时间格式。

它使用DateTimeFormatter ISO_OFFSET_DATE_TIME反序列化和序列化值。 [了解详情](https://docs.oracle.com/javase/8/docs/api/java/time/format/DateTimeFormatter.html#ISO_OFFSET_DATE_TIME)

您还可以传递一个传递新纪元值的整数。 [阅读更多](https://www.epochconverter.com)

时区可以由偏移或时区代码指定(例如：欧洲／巴黎，Z —— 表示UTC)。

**文本表示**

```toDateTime("<dateTime in ISO-8601 format>")```

```toDateTime(<integer value of an epoch in milliseconds>)```

**示例**

```toDateTime("1977-04-22T06:00:00Z")```

```toDateTime("2011-12-03T15:15:30Z")```

```toDateTime("2011-12-03T15:15:30.123Z")```

```toDateTime("2011-12-03T15:15:30.123+02:00")```

```toDateTime("2011-12-03T15:15:30.123-00:20")```

```toDateTime(1560762190189)```

## 持续时间 {#duration}

**说明**

它表示基于时间的时间量，如“34.5秒”。 它以毫秒为单位来建模数量或时间。

支持的时间单元有：毫秒、秒、分钟、小时、天，其中一天等于24小时。 年份和月份不受支持，因为它们不是固定的时间。

JSON格式：字符串。

它必须封装在toDuration函数中。

序列化格式：要反序列化时区ID，它使用java函数java.time。

Duration.parse:接受的格式基于ISO-8601持续时间格式PnDTnHnMn.nS，其天数被认为正好24小时。 [了解详情](https://docs.oracle.com/javase/8/docs/api/java/time/Duration.html#parse-java.lang.CharSequence-)

**文本表示**

```toDuration("<duration in ISO-8601 format>")```

```toDuration(<duration in milliseconds>)```

**示例**

```toDuration("PT5S")``` 5秒内崩溃

```toDuration(500)``` 500毫秒的解析

```toDuration("PT20.345S")``` 解读为“20.345秒”

```toDuration("PT15M") ``` 解析为“15分钟”（其中一分钟为60秒）

```toDuration("PT10H") ``` 分析为“10小时”（其中1小时为3600秒）

```toDuration("P2D") ``` 分析为“2天”（其中一天为24小时或86400秒）

```toDuration("P2DT3H4M") ```“2天、3小时、4分钟”

```toDuration("P-6H3M") ``` “6小时+3分钟”的解读

```toDuration("-P6H3M")``` “6小时3分钟”的解析

```toDuration("-P-6H+3M") ``` 解析为“+6小时和-3分钟”

## list {#list}

**说明**

以逗号分隔的表达式列表，使用方括号作为分隔符。

不支持多态，因此列表中包含的所有表达式应具有相同类型。

**文本表示**

```[<expression>, <expression>, ... ]```

**示例**

```["value1","value2"]```

```[3,5]```

```[toDuration(500),toDuration(800)]```
