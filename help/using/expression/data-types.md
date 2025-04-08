---
product: adobe campaign
title: 数据类型
description: 了解高级表达式中的数据类型
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 343f61b8-2315-4971-8b2b-6aa815bd9ced
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '656'
ht-degree: 5%

---

# 数据类型 {#concept_gp3_rj5_dgb}


>[!CAUTION]
>
>**正在查找Adobe Journey Optimizer**？ 单击[此处](https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer/using/ajo-home){target="_blank"}获取Journey Optimizer文档。
>
>
>_本文档参考已被Journey Optimizer替换的旧版Journey Orchestration资料。 如果您对访问Journey Orchestration或Journey Optimizer有任何疑问，请联系您的帐户团队。_


从技术上讲，常量始终包含数据类型。 在文本表达式中，我们仅指定值。 可以从值推断数据类型（例如字符串、整数、小数等）。 对于日期时间等具体情况，我们使用专门的函数进行表示。

以下各部分提供了有关不同数据类型表达式及其表示方式的信息。

## 字符串 {#string}

**描述**

常用字符序列。 除来自环境的隐式大小（例如可用内存量）外，它没有任何特定大小。

JSON格式：字符串

序列化格式：UTF-8

**文本呈现**

```json
"<value>"
```

```json
'<value>'
```

**示例**

```json
"hello world"
```

```json
'hello world'
```

## 整数 {#integer}

**描述**

从–2^63到2^63-1的整数值。

JSON格式：数字

**文本呈现**

```json
<integer value>
```

**示例**

```json
42
```

## 小数 {#decimal}

**描述**

十进制数。 它表示一个浮动值：

* 双精度型的最大正有限值，(2-2^-52)x2^1023
* double类型的最小正正规值，2-1022
* double类型的最小正非零值，2 p-1074

JSON格式：数字

序列化格式：使用“。” 作为小数分隔符。

**文本呈现**

```json
<integer value>.<integer value>
```

**示例**

```json
3.14
```

## 布尔 {#boolean}

**描述**

布尔值写入小写： true或false

JSON格式：布尔型

**文本呈现**

```json
true
```

```json
false
```

**示例**

```json
true
```

## dateOnly {#date-only}

**描述**

表示不带时区的日期，以年 — 月 — 日形式查看。

它是日期的描述，用于生日。

json格式：字符串。

格式为：YYYY-MM-DD (ISO-8601)，例如：“2021-03-11”。

它可以封装在toDateOnly函数中。

它使用DateTimeFormatter ISO_LOCAL_DATE_TIME反序列化和序列化该值。 [了解详情](https://datatracker.ietf.org/doc/html/rfc3339#section-5.6)

**文本呈现**

```json
date("<dateOnly in ISO-8601 format>")  
```

**示例**

```json
date("2021-02-19")
```

## dateTimeOnly {#date-time-only}

**描述**

表示不带时区的日期时间，它以年 — 月 — 日 — 小时 — 分钟 — 秒 — 毫秒形式查看。

json格式：字符串。

它不存储或表示时区。 相反，它是对日期的描述（用于生日），与墙上时钟上显示的当地时间相结合。

如果没有偏移或时区等附加信息，它不能表示时间线上的瞬间。

它可以封装在toDateTimeOnly函数中。

序列化格式：ISO-8601扩展偏移日期时间格式。

它使用DateTimeFormatter ISO_LOCAL_DATE_TIME反序列化和序列化该值。 [了解详情](https://docs.oracle.com/javase/8/docs/api/java/time/format/DateTimeFormatter.html#ISO_LOCAL_DATE_TIME&quot;)

**文本呈现**

```json
date("<dateTimeOnly in ISO-8601 format>")  
```

**示例**

```json
date("2021-02-19T00.00.000")
date("2021-02-19T00.00")
```

## dateTime {#date-time}

**描述**

日期时间常量，也会考虑时区。 它表示一个日期时间，带有与UTC的偏移。

它可以被视为带有偏移量附加信息的即时时刻。 这是一种在世界特定地点表示特定“时刻”的方式。

json格式：字符串。

它可以封装在toDateTime函数中。

序列化格式：ISO-8601扩展偏移日期时间格式。

它使用DateTimeFormatter ISO_OFFSET_DATE_TIME反序列化和序列化值。 [了解详情](https://docs.oracle.com/javase/8/docs/api/java/time/format/DateTimeFormatter.html#ISO_OFFSET_DATE_TIME)

您还可以传递一个传递epoch值的整数。 [了解详情](https://www.epochconverter.com)

时区可以通过偏移或时区代码指定（例如：欧洲/巴黎，Z — 表示UTC）。

**文本呈现**

```json
toDateTime("<dateTime in ISO-8601 format>")
```

```json
date("<dateTime in ISO-8601 format>")
```

```json
toDateTime(<integer value of an epoch in milliseconds>)
```

**示例**

```json
date("2021-02-19T00.00.000Z")
```

```json
toDateTime("1977-04-22T06:00:00Z")
```

```json
toDateTime("2011-12-03T15:15:30Z")
```

```json
toDateTime("2011-12-03T15:15:30.123Z")
```

```json
toDateTime("2011-12-03T15:15:30.123+02:00")
```

```json
toDateTime("2011-12-03T15:15:30.123-00:20")
```

```json
toDateTime(1560762190189)
```

## 持续时间 {#duration}

**描述**

它表示基于时间的时间量，如“34.5秒”。 它以毫秒为单位对时间量或时间量建模。

支持的临时单位为：毫秒、秒、分钟、小时、天，其中天等于24小时。 不支持年份和月份，因为它们不是固定时间。

json格式：字符串。

必须将其封装在toDuration函数中。

序列化格式：要反序列化时区ID，它使用java函数java.time。

Duration.parse：可接受的格式基于ISO-8601持续时间格式PnDTnHnMn.nS，天数被认为刚好是24小时。 [了解详情](https://docs.oracle.com/javase/8/docs/api/java/time/Duration.html#parse-java.lang.CharSequence-)

**文本呈现**

```json
toDuration("<duration in ISO-8601 format>")
```

```json
toDuration(<duration in milliseconds>)
```

**示例**

```json
toDuration("PT5S") -- parses as 5 seconds
```

```json
toDuration(500) -- parses as 500ms
```

```json
toDuration("PT20.345S") -- parses as "20.345 seconds"
```

```json
toDuration("PT15M") -- parses as "15 minutes" (where a minute is 60 seconds)
```

```json
toDuration("PT10H")  -- parses as "10 hours" (where an hour is 3600 seconds)
```

```json
toDuration("P2D") -- parses as "2 days" (where a day is 24 hours or 86400 seconds)
```

```json
toDuration("P2DT3H4M") -- parses as "2 days, 3 hours and 4 minutes"
```

```json
toDuration("P-6H3M") -- parses as "-6 hours and +3 minutes"
```

```json
toDuration("-P6H3M") -- parses as "-6 hours and -3 minutes"
```

```json
toDuration("-P-6H+3M") -- parses as "+6 hours and -3 minutes"
```

## list {#list}

**描述**

使用方括号作为分隔符的表达式逗号分隔列表。

不支持多态性，因此列表中包含的所有表达式都应具有相同的类型。

**文本呈现**

```json
[<expression>, <expression>, ... ]
```

**示例**

```json
["value1","value2"]
```

```json
[3,5]
```

```json
[toDuration(500),toDuration(800)]
```
