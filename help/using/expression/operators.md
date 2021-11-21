---
product: adobe campaign
title: 操作员
description: 了解高级表达式中的运算符
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: fd86b6ab-76cf-4b35-9e87-f441e914f20b
source-git-commit: 5225045f02fb1b2a8505756d9d7f6f60a32b3ed6
workflow-type: tm+mt
source-wordcount: '435'
ht-degree: 6%

---

# 操作员 {#concept_wd5_pj5_dgb}

有两种运算符：一元运算符和二进制运算符。 有左一元运算符和右一元运算符。

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

以下是支持的运算符列表：

## 逻辑  {#logical}

### 和

```json
<expression1> and <expression2>
```

两者兼有 &lt;expression1> 和 &lt;expression2> 必须是布尔值。 结果为布尔值。

示例：

```json
3.14 > 2 and 3.15 < 1
```

### 或



```json
<expression1> or <expression2>
```

两者兼有 &lt;expression1> 和 &lt;expression2> 必须是布尔值。 结果为布尔值。

示例：

```json
3.14 > 2 or 3.15 < 1
```

### not



```json
not <expression>
```

&lt;expression> 必须是布尔值。 The result is boolean.

示例：

```json
not 3.15 < 1
```

## 比较 {#comparison}

### is null



```json
<expression> is null
```

结果为布尔值。

Note that null means the expression has no evaluated value.

示例：

```json
@{BarBeacon.location} is null
```

### 不为空



```json
<expression> is not null
```

结果为布尔值。

Note that null means the expression has no evaluated value.

示例：

```json
@ is not null
```

### 具有null



```json
<expression> has null
```

&lt;expression> 必须是列表。 结果为布尔值。

用于标识列表至少包含一个空值。

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

两者兼有 &lt;expression1> 和 &lt;expression2> 必须具有相同的数据类型。 结果为布尔值。

示例：

```json
3.14 == 42
```

```json
"foo" == "bar"
```

### !=



```json
<expression1> != <expression2>
```

两者兼有 &lt;expression1> 和 &lt;expression2> 必须具有相同的数据类型。 结果为布尔值。

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

可以将日期时间与日期时间进行比较。

可以将Datetimeonly与Datetimeonly进行比较。

Both integer or decimal can be compared with both integer or decimal.

Any other combination is forbidden.

结果为布尔值。

示例：

```json
3.14 > 42
```

### >=



```json
<expression1> >= <expression2>
```

可以将日期时间与日期时间进行比较。

可以将Datetimeonly与Datetimeonly进行比较。

可以将整数或小数都与整数或小数进行比较。

禁止任何其他组合。

结果为布尔值。

示例：

```json
42 >= 3.14
```

### &lt;



```json
<expression1> < <expression2>
```

可以将日期时间与日期时间进行比较。

可以将Datetimeonly与Datetimeonly进行比较。

Both integer or decimal can be compared with both integer or decimal.

禁止任何其他组合。

结果为布尔值。

示例：

```json
42 < 3.14
```

### &lt;=



```json
<expression1> <= <expression2>
```

可以将日期时间与日期时间进行比较。

可以将Datetimeonly与Datetimeonly进行比较。

可以将整数或小数都与整数或小数进行比较。

禁止任何其他组合。

结果为布尔值。

示例：

```json
42 <= 3.14
```

## 算术 {#arithmetic}

### +



```json
<expression1> + <expression2>
```

两个表达式都必须为数字（整数或小数）。

结果也是数字。

示例：

```json
1 + 2 -- returns 3
```

### -



```json
<expression1> - <expression2>
```

Both expressions must be numeric (integer or decimal).

结果也是数字。

示例：

```json
2 - 1 -- returns 1
```

### /



```json
<expression1> / <expression2>
```

两个表达式都必须为数字（整数或小数）。

结果也是数字。

&lt;expression2> 不得等于0（返回0）。

示例：

```json
4 / 2 -- returns 2
```

### *



```json
<expression1> * <expression2>
```

Both expressions must be numeric (integer or decimal).

结果也是数字。

示例：

```json
3 * 4 -- returns 12
```

### %



```json
<expression1> % <expression2>
```

两个表达式都必须为数字（整数或小数）。

结果也是数字。

示例：

```json
3 % 2 -- returns 1.
```

## 数学 {#math}

### 表示数值



```json
<expression> is numeric
```

表达式的类型为整数或小数。

示例：

```json
@ is numeric
```

### 是整数



```json
<expression> is integer
```

The type of the expression is integer.

示例：

```json
@ is integer
```

### 小数



```json
<expression> is decimal
```

表达式的类型为十进制。

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

It concatenates two expressions.

One expression must be a chained string.

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

将持续时间附加到dateTime、dateTimeOnly或持续时间。

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
