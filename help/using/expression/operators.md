---
product: adobe campaign
title: 操作员
description: 了解高级表达式中的运算符
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: fd86b6ab-76cf-4b35-9e87-f441e914f20b
source-git-commit: a0b6ab595bc16a75aa5a56a858900418e2381ab9
workflow-type: tm+mt
source-wordcount: '459'
ht-degree: 6%

---

# 操作员 {#concept_wd5_pj5_dgb}

运算符分为二类：一元运算符和二元运算符。 有左一元运算符和右一元运算符。

```json
    // left-hand unary operators
    <operator> <operand> // operand is an expression
    not (@{LobbyBeacon.endUserIDs._experience.emailid.id}=="example@adobe.com")

    // right-hand unary operators
    <operand> <operator> // operand is an expression
    @{LobbyBeacon.endUserIDs._experience.emailid.id} is not null

    // binary operators
    <operand1> <operator> <operand2>
    (@{LobbyBeacon.endUserIDs._experience.emailid.id}=="example1@adobe.com") or
    (@{LobbyBeacon.endUserIDs._experience.emailid.id}=="example2@adobe.com")
```

## 重要说明{#important-notes}

* 使用乘法(`*`)时，两个操作字段必须具有相同的类型，可以是整数或小数。 示例：
   * 以下示例是正确的： `3.0 * 4.0`
   * `3 * 4.0`将导致错误

## 逻辑  {#logical}

### 和

```json
<expression1> and <expression2>
```

&lt;expression1>和&lt;expression2>都必须是布尔值。 结果是布尔值。

示例：

```json
3.14 > 2 and 3.15 < 1
```

### 或



```json
<expression1> or <expression2>
```

&lt;expression1>和&lt;expression2>都必须是布尔值。 结果是布尔值。

示例：

```json
3.14 > 2 or 3.15 < 1
```

### 非



```json
not <expression>
```

&lt;expression>必须为布尔值。 结果是布尔值。

示例：

```json
not 3.15 < 1
```

## 比较 {#comparison}

### 为空



```json
<expression> is null
```

结果是布尔值。

请注意，null表示表达式没有计算值。

示例：

```json
@{BarBeacon.location} is null
```

### 不为null



```json
<expression> is not null
```

结果是布尔值。

请注意，null表示表达式没有计算值。

示例：

```json
@ is not null
```

### 为空



```json
<expression> has null
```

&lt;expression>必须为列表。 结果是布尔值。

用于标识列表是否包含至少一个null值。

示例：

```json
["foo", "bar", null] has null --  returns true.
```

```json
["foo", "bar", ""] has null -- returns false because "" is not considered as null.
```

### ==



```json
<expression1> == <expression2>
```

&lt;expression1>和&lt;expression2>必须具有相同的数据类型。 结果是布尔值。

示例：

```json
3.14 == 42
```

```json
"foo" == "bar"
```

### ！=



```json
<expression1> != <expression2>
```

&lt;expression1>和&lt;expression2>必须具有相同的数据类型。 结果是布尔值。

示例：

```json
3.14 != 42
```

```json
"foo" != "bar"
```

### >



```json
<expression1> > <expression2>
```

日期时间可以与日期时间进行比较。

只能将Datetimeonly与Datetimeonly进行比较。

整数或小数都可与整数或小数进行比较。

禁止任何其他组合。

结果是布尔值。

示例：

```json
3.14 > 42
```

### >=



```json
<expression1> >= <expression2>
```

日期时间可以与日期时间进行比较。

只能将Datetimeonly与Datetimeonly进行比较。

整数或小数都可与整数或小数进行比较。

禁止任何其他组合。

结果是布尔值。

示例：

```json
42 >= 3.14
```

### &lt;



```json
<expression1> < <expression2>
```

日期时间可以与日期时间进行比较。

只能将Datetimeonly与Datetimeonly进行比较。

整数或小数都可与整数或小数进行比较。

禁止任何其他组合。

结果是布尔值。

示例：

```json
42 < 3.14
```

### &lt;=



```json
<expression1> <= <expression2>
```

日期时间可以与日期时间进行比较。

只能将Datetimeonly与Datetimeonly进行比较。

整数或小数都可与整数或小数进行比较。

禁止任何其他组合。

结果是布尔值。

示例：

```json
42 <= 3.14
```

## 算术 {#arithmetic}

### +



```json
<expression1> + <expression2>
```

两个表达式都必须是数字（整数或小数）。

结果也是数字。

示例：

```json
1 + 2 -- returns 3
```

### -



```json
<expression1> - <expression2>
```

两个表达式都必须是数字（整数或小数）。

结果也是数字。

示例：

```json
2 - 1 -- returns 1
```

### /



```json
<expression1> / <expression2>
```

两个表达式都必须是数字（整数或小数）。

结果也是数字。

&lt;expression2>不能等于0（返回0）。

示例：

```json
4 / 2 -- returns 2
```

### *



```json
<expression1> * <expression2>
```

两个表达式都必须是数字（整数或小数）。

结果也是数字。

示例：

```json
3 * 4 -- returns 12
```

### %



```json
<expression1> % <expression2>
```

两个表达式都必须是数字（整数或小数）。

结果也是数字。

示例：

```json
3 % 2 -- returns 1.
```

## 数学 {#math}

### 是数字



```json
<expression> is numeric
```

表达式的类型为整数或小数。

示例：

```json
@ is numeric
```

### 为整数



```json
<expression> is integer
```

表达式的类型为integer。

示例：

```json
@ is integer
```

### 为小数



```json
<expression> is decimal
```

表达式的类型为小数。

示例：

```json
@ is decimal
```

## 字符串 {#string}

### +



```json
<string> + <expression>
```

```json
<expression> + <string>
```

它连接两个表达式。

一个表达式必须是链接字符串。

示例：

```json
"the current time is " + (now()) -- returns "the current time is 2019-09-23T09:30:06.693Z"
```

```json
(now()) + " is the current time" -- returns "2019-09-23T09:30:06.693Z is the current time"
```

```json
"a" + "b" + "c" + 1234 -- returns "abc1234".
```

## 日期 {#date}

### +



```json
<expression> + <duration>
```

将持续时间附加到dateTime、dateTimeOnly或duration。

示例：

```json
toDateTime("2011-12-03T15:15:30Z") + toDuration("PT15M") -- returns 2011-12-03T15:30:30Z
```

```json
toDateTimeOnly("2011-12-03T15:15:30") + toDuration("PT15M") -- returns 2011-12-03T15:30:30
```

```json
now() + toDuration("PT1H") -- returns a dateTime (with UTC time zone) one hour later from current time
```

```json
toDuration("PT1H") + toDuration("PT1H") -- returns  PT2H
```
