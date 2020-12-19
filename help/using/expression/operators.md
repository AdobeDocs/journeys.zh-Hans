---
product: adobe campaign
solution: Journey Orchestration
title: 运算符
description: 了解高级表达式中的运营商
translation-type: tm+mt
source-git-commit: 062b4648e2eb3a4270f9c09e4478d541209e1247
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---



# 运算符 {#concept_wd5_pj5_dgb}

操作符有两种：一元运算符和二进制运算符。 有左一元运算符和右一元运算符。

```
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

以下是受支持操作符的列表:

## 逻辑{#logical}

### 和

```
<expression1> and <expression2>
```

&lt;表达式1>和&lt;表达式2>都必须是布尔值。 结果为布尔型。

示例:

```
3.14 > 2 and 3.15 < 1
```

### 或者



```
<expression1> or <expression2>
```

&lt;表达式1>和&lt;表达式2>都必须是布尔值。 结果为布尔型。

示例:

```
3.14 > 2 or 3.15 < 1
```

### 不



```
not <expression>
```

&lt;expression> 必须是布尔型。结果为布尔型。

示例:

```
not 3.15 < 1
```

## 比较{#comparison}

### 为null



```
<expression> is null
```

结果为布尔型。

请注意，null表示表达式没有评估值。

示例:

```
@{BarBeacon.location} is null
```

### 不是null



```
<expression> is not null
```

结果为布尔型。

请注意，null表示表达式没有评估值。

示例:

```
@ is not null
```

### 空



```
<expression> has null
```

&lt;expression> 一定是列表。结果为布尔型。

用于标识列表是否至少包含一个null值。

示例:

```
["foo", "bar", null] has null --  returns true.
```

```
["foo", "bar", ""] has null -- returns false because "" is not considered as null.
```

### ==



```
<expression1> == <expression2>
```

&lt;表达式1>和&lt;表达式2>必须具有相同的数据类型。 结果为布尔型。

示例:

```
3.14 == 42
```

```
"foo" == "bar"
```

### !=



```
<expression1> != <expression2>
```

&lt;表达式1>和&lt;表达式2>必须具有相同的数据类型。 结果为布尔型。

示例:

```
3.14 != 42
```

```
"foo" != "bar"
```

### >



```
<expression1> > <expression2>
```

可以将日期时间与日期时间进行比较。

只能将Datetime与DatetimeOnly进行比较。

整数或十进制都可以与整数或十进制进行比较。

任何其他组合都被禁止。

结果为布尔型。

示例:

```
3.14 > 42
```

### >=



```
<expression1> >= <expression2>
```

可以将日期时间与日期时间进行比较。

只能将Datetime与DatetimeOnly进行比较。

整数或十进制都可以与整数或十进制进行比较。

任何其他组合都被禁止。

结果为布尔型。

示例:

```
42 >= 3.14
```

### &lt;>



```
<expression1> < <expression2>
```

可以将日期时间与日期时间进行比较。

只能将Datetime与DatetimeOnly进行比较。

整数或十进制都可以与整数或十进制进行比较。

任何其他组合都被禁止。

结果为布尔型。

示例:

```
42 < 3.14
```

### &lt;>



```
<expression1> <= <expression2>
```

可以将日期时间与日期时间进行比较。

只能将Datetime与DatetimeOnly进行比较。

整数或十进制都可以与整数或十进制进行比较。

任何其他组合都被禁止。

结果为布尔型。

示例:

```
42 <= 3.14
```

## 算术{#arithmetic}

### +



```
<expression1> + <expression2>
```

两个表达式都必须是数字（整数或小数）。

结果也是数字。

示例:

```
1 + 2 -- returns 3
```

### -



```
<expression1> - <expression2>
```

两个表达式都必须是数字（整数或小数）。

结果也是数字。

示例:

```
2 - 1 -- returns 1
```

### /



```
<expression1> / <expression2>
```

两个表达式都必须是数字（整数或小数）。

结果也是数字。

&lt;expression2> 不得等于0（返回0）。

示例:

```
4 / 2 -- returns 2
```

### *



```
<expression1> * <expression2>
```

两个表达式都必须是数字（整数或小数）。

结果也是数字。

示例:

```
3 * 4 -- returns 12
```

### %



```
<expression1> % <expression2>
```

两个表达式都必须是数字（整数或小数）。

结果也是数字。

示例:

```
3 % 2 -- returns 1.
```

## 数学 {#math}

### 数字



```
<expression> is numeric
```

表达式的类型为整数或十进制。

示例:

```
@ is numeric
```

### integer



```
<expression> is integer
```

表达式的类型是整数。

示例:

```
@ is integer
```

### 小数



```
<expression> is decimal
```

表达式类型为十进制。

示例:

```
@ is decimal
```

## 字符串 {#string}

### +



```
<string> + <expression>
```

```
<expression> + <string>
```

它连接两个表达式。

一个表达式必须是链式字符串。

示例:

```
"the current time is " + (now()) -- returns "the current time is 2019-09-23T09:30:06.693Z"
```

```
(now()) + " is the current time" -- returns "2019-09-23T09:30:06.693Z is the current time"
```

```
"a" + "b" + "c" + 1234 -- returns "abc1234".
```

## 日期 {#date}

### +



```
<expression + <duration>
```

在dateTime、dateTimeOnly或duration后追加持续时间。

示例:

```
toDateTime("2011-12-03T15:15:30Z") + toDuration("PT15M") -- returns 2011-12-03T15:30:30Z
```

```
toDateTimeOnly("2011-12-03T15:15:30") + toDuration("PT15M") -- returns 2011-12-03T15:30:30
```

```
now() + toDuration("PT1H") -- returns a dateTime (with UTC time zone) one hour later from current time
```

```
toDuration("PT1H") + toDuration("PT1H") -- returns  PT2H
```
