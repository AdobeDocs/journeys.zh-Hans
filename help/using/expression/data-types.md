---
product: adobe campaign
title: 数据类型
description: 瞭解進階運算式中的資料型別
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 343f61b8-2315-4971-8b2b-6aa815bd9ced
source-git-commit: 5225045f02fb1b2a8505756d9d7f6f60a32b3ed6
workflow-type: tm+mt
source-wordcount: '637'
ht-degree: 5%

---

# 数据类型 {#concept_gp3_rj5_dgb}

技術上，常數一律包含資料型別。 在常值運算式中，我們僅指定值。 資料型別可從值推斷（例如字串、整數、小數等）。 對於日期時間等特定情況，我們會使用專用功能進行表示。

以下各節提供有關不同資料型別運算式及其表示方式的資訊。

## 字符串 {#string}

**描述**

常見的字元順序。 除了來自環境的隱含大小（例如可用的記憶體數量）之外，它沒有任何特定大小。

JSON格式：字串

序列化格式： UTF-8

**常值表示法**

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

從–2^63到2^63-1的整數值。

JSON格式：數字

**常值表示法**

```json
<integer value>
```

**示例**

```json
42
```

## 小數 {#decimal}

**描述**

小数. 它代表一個浮點數值：

* 型別double的最大正有限值，(2-2^-52)x2^1023
* 型別double的最小正常數值，2-1022
* 型別double的最小正非零值，2 p-1074

JSON格式：數字

序列化格式：使用「。」 做為小數分隔符號。

**常值表示法**

```json
<integer value>.<integer value>
```

**示例**

```json
3.14
```

## 布尔 {#boolean}

**描述**

布林值會寫入小寫： true或false

JSON格式：布林值

**常值表示法**

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

只代表沒有時區的日期，以年 — 月 — 日檢視。

這是日期的說明，用於生日。

JSON格式：字串。

格式為：YYYY-MM-DD (ISO-8601)，例如：「2021-03-11」。

可封裝在toDateOnly函式中。

它會使用DateTimeFormatter ISO_LOCAL_DATE_TIME將值還原序列化及序列化。 [了解详情](https://datatracker.ietf.org/doc/html/rfc3339#section-5.6)

**常值表示法**

```json
date("<dateOnly in ISO-8601 format>")  
```

**示例**

```json
date("2021-02-19")
```

## dateTimeOnly {#date-time-only}

**描述**

代表沒有時區的日期時間，以年 — 月 — 日 — 小時 — 分鐘 — 秒 — 毫秒的方式檢視。

JSON格式：字串。

它不會儲存或表示時區。 相反地，它是日期的描述（如生日所用），與牆上時鐘所顯示的當地時間相結合。

若沒有位移或時區等額外資訊，就無法表示時間軸上的瞬間。

可封裝在toDateTimeOnly函式中。

序列化格式：ISO-8601延伸位移日期 — 時間格式。

它會使用DateTimeFormatter ISO_LOCAL_DATE_TIME將值還原序列化及序列化。 [了解详情](https://docs.oracle.com/javase/8/docs/api/java/time/format/DateTimeFormatter.html#ISO_LOCAL_DATE_TIME&quot;)

**常值表示法**

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

日期時間常數，也會考量時區。 它表示與UTC有偏移的日期時間。

它可視為具有位移之其他資訊的即時狀態。 這是一種表示世界上某個地方特定「時刻」的方式。

JSON格式：字串。

可封裝在toDateTime函式中。

序列化格式：ISO-8601延伸位移日期 — 時間格式。

它使用DateTimeFormatter ISO_OFFSET_DATE_TIME將值還原序列化和序列化。 [了解详情](https://docs.oracle.com/javase/8/docs/api/java/time/format/DateTimeFormatter.html#ISO_OFFSET_DATE_TIME)

您也可以傳遞傳遞epoch值的整數。 [了解详情](https://www.epochconverter.com)

時區可由位移或時區代碼指定（例如：歐洲/巴黎、Z — 表示UTC）。

**常值表示法**

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

## 持續時間 {#duration}

**描述**

這代表以時間為基礎的時間量，例如「34.5秒」。 它會以毫秒為單位模擬時間量或時間量。

支援的臨時單位為：毫秒、秒、分鐘、小時、天，其中一天等於24小時。 不支援年份和月份，因為它們不是固定時間量。

JSON格式：字串。

它必須封裝在toDuration函式中。

序列化格式：若要將時區ID還原序列化，會使用java函式java.time。

Duration.parse：接受的格式是以ISO-8601期間格式PnDTnHnMn.nS為基礎，天數被視為剛好24小時。 [了解详情](https://docs.oracle.com/javase/8/docs/api/java/time/Duration.html#parse-java.lang.CharSequence-)

**常值表示法**

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

以逗號分隔的運算式清單，使用方括弧做為分隔符號。

不支援多型，因此清單中包含的所有運算式都應該有相同的型別。

**常值表示法**

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
