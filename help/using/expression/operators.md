---
product: adobe campaign
title: 操作员
description: 瞭解進階運算式中的運運算元
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: fd86b6ab-76cf-4b35-9e87-f441e914f20b
source-git-commit: a0b6ab595bc16a75aa5a56a858900418e2381ab9
workflow-type: tm+mt
source-wordcount: '457'
ht-degree: 7%

---

# 操作员 {#concept_wd5_pj5_dgb}

運運算元有兩種型別：一元運運算元和二進位運運算元。 有左側一元運運算元和右側一元運運算元。

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

* 使用乘法時(`*`)，則兩個作業欄位都必須有相同的型別，可以是整數或小數。 示例：
   * 以下範例是正確的： `3.0 * 4.0`
   * `3 * 4.0` 將導致錯誤

## 邏輯  {#logical}

### 和

```json
<expression1> and <expression2>
```

兩者 &lt;expression1> 和 &lt;expression2> 必須為布林值。 結果是布林值。

示例：

```json
3.14 > 2 and 3.15 < 1
```

### 或



```json
<expression1> or <expression2>
```

兩者 &lt;expression1> 和 &lt;expression2> 必須為布林值。 結果是布林值。

示例：

```json
3.14 > 2 or 3.15 < 1
```

### not



```json
not <expression>
```

&lt;expression> 必須為布林值。 結果是布林值。

示例：

```json
not 3.15 < 1
```

## 比較 {#comparison}

### 為null



```json
<expression> is null
```

結果是布林值。

請注意，null表示運算式沒有評估值。

示例：

```json
@{BarBeacon.location} is null
```

### 不是null



```json
<expression> is not null
```

結果是布林值。

請注意，null表示運算式沒有評估值。

示例：

```json
@ is not null
```

### 具有null



```json
<expression> has null
```

&lt;expression> 必須為清單。 結果是布林值。

用於識別清單是否包含至少一個Null值。

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

兩者 &lt;expression1> 和 &lt;expression2> 必須有相同的資料型別。 結果是布林值。

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

兩者 &lt;expression1> 和 &lt;expression2> 必須有相同的資料型別。 結果是布林值。

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

Datetime可以與Datetime比較。

Datetimeonly可與Datetimeonly比較。

整數或小數點都可與整數或小數點進行比較。

禁止任何其他組合。

結果是布林值。

示例：

```json
3.14 > 42
```

### >=



```json
<expression1> >= <expression2>
```

Datetime可以與Datetime比較。

Datetimeonly可與Datetimeonly比較。

整數或小數點都可與整數或小數點進行比較。

禁止任何其他組合。

結果是布林值。

示例：

```json
42 >= 3.14
```

### &lt;



```json
<expression1> < <expression2>
```

Datetime可以與Datetime比較。

Datetimeonly可與Datetimeonly比較。

整數或小數點都可與整數或小數點進行比較。

禁止任何其他組合。

結果是布林值。

示例：

```json
42 < 3.14
```

### &lt;=



```json
<expression1> <= <expression2>
```

Datetime可以與Datetime比較。

Datetimeonly可與Datetimeonly比較。

整數或小數點都可與整數或小數點進行比較。

禁止任何其他組合。

結果是布林值。

示例：

```json
42 <= 3.14
```

## 算術 {#arithmetic}

### +



```json
<expression1> + <expression2>
```

這兩個運算式都必須是數值（整數或小數）。

結果也是數字。

示例：

```json
1 + 2 -- returns 3
```

### -



```json
<expression1> - <expression2>
```

這兩個運算式都必須是數值（整數或小數）。

結果也是數字。

示例：

```json
2 - 1 -- returns 1
```

### /



```json
<expression1> / <expression2>
```

這兩個運算式都必須是數值（整數或小數）。

結果也是數字。

&lt;expression2> 不得等於0 （傳回0）。

示例：

```json
4 / 2 -- returns 2
```

### *



```json
<expression1> * <expression2>
```

這兩個運算式都必須是數值（整數或小數）。

結果也是數字。

示例：

```json
3 * 4 -- returns 12
```

### %



```json
<expression1> % <expression2>
```

這兩個運算式都必須是數值（整數或小數）。

結果也是數字。

示例：

```json
3 % 2 -- returns 1.
```

## 数学 {#math}

### 為數值



```json
<expression> is numeric
```

運算式的型別是整數或小數。

示例：

```json
@ is numeric
```

### 為整數



```json
<expression> is integer
```

運算式的型別是整數。

示例：

```json
@ is integer
```

### 為小數



```json
<expression> is decimal
```

運算式的型別是十進位。

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

它會串連兩個運算式。

一個運算式必須是鏈結字串。

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

將期間附加至dateTime、dateTimeOnly或duration。

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
