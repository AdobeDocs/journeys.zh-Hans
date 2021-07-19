---
product: adobe campaign
title: 函数
description: 了解函数
feature: 历程
role: Data Engineer
level: Experienced
exl-id: b514d2e9-1444-46d5-a1ac-3591e62807c1
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '168'
ht-degree: 74%

---

# 函数 {#concept_p1r_qj5_dgb}

一个函数可以具有不同的签名（一组不同的有序参数）。 函数签名可以具有0-N表达式作为有序参数。

`<function name>`(`<expression as param 1>`、  `<expression as param 2>`、...、 `<expression as param N>`)

每个函数都具有特定的返回类型。

以下是受支持的函数的列表。

## 主要函数

| 类别 | 函数 |
|-------------|-----------------------|
| Adobe Experience Platform | [inSegment](../functions/functioninsegment.md) |
| 聚合 | [avg](../functions/functionavg.md) |
| 聚合 | [count](../functions/functioncount.md) |
| 聚合 | [countOnlyNull](../functions/functioncountonlynull.md) |
| 聚合 | [countWithNull](../functions/functioncountwithnull.md) |
| 聚合 | [distinctCount](../functions/functiondistinctcount.md) |
| 聚合 | [distinctCountWithNull](../functions/functiondistinctcountwithnull.md) |
| 聚合 | [max](../functions/functionmax.md) |
| 聚合 | [min](../functions/functionmin.md) |
| 聚合 | [sum](../functions/functionsum.md) |
| 转化 | [toBool](../functions/functiontobool.md) |
| 转化 | [toDateTime](../functions/functiontodatetime.md) |
| 转化 | [toDateTimeOnly](../functions/functiontodatetimeonly.md) |
| 转化 | [toDecimal](../functions/functiontodecimal.md) |
| 转化 | [toDuration](../functions/functiontoduration.md) |
| 转化 | [toInteger](../functions/functiontointeger.md) |
| 转化 | [toString](../functions/functiontostring.md) |
| 日期 | [currentTimeInMillis](../functions/functioncurrenttimeinmillis.md) |
| 日期 | [inLastDays](../functions/functioninlastdays.md) |
| 日期 | [inLastHours](../functions/functioninlasthours.md) |
| 日期 | [inLastMonths](../functions/functioninlastmonths.md) |
| 日期 | [inLastYears](../functions/functioninlastyears.md) |
| 日期 | [inNextDays](../functions/functioninnextdays.md) |
| 日期 | [inNextHours](../functions/functioninnexthours.md) |
| 日期 | [inNextMonths](../functions/functioninnextmonths.md) |
| 日期 | [inNextYears](../functions/functioninnextyears.md) |
| 日期 | [now](../functions/functionnow.md) |
| 日期 | [nowWithDelta](../functions/functionnowwithdelta.md) |
| 日期 | [setHours](../functions/functionsethours.md) |
| 日期 | [setDays](../functions/functionsetdays.md) |
| 列表 | [distinct](../functions/functiondistinct.md) |
| 列表 | [distinctCount](../functions/functiondistinctcount.md) |
| 列表 | [在 ](../functions/functionin.md) |
| 列表 | [listSize](../functions/functionlistsize.md) |
| 列表 | [serializeList](../functions/functionserializelist.md) |
| 列表 | [sort](../functions/functionsort.md) |
| 数学 | [random](../functions/functionrandom.md) |
| 数学 | [round](../functions/functionround.md) |
| 字符串 | [concat](../functions/functionconcat.md) |
| 字符串 | [contain](../functions/functioncontain.md) |
| 字符串 | [containWithIgnoreCase](../functions/functioncontainwithignorecase.md) |
| 字符串 | [endWith](../functions/functionendwith.md) |
| 字符串 | [endWithIgnoreCase](../functions/functionendwithignorecase.md) |
| 字符串 | [equalWithIgnoreCase](../functions/functionequalignorecase.md) |
| 字符串 | [indexOf](../functions/functionindexof.md) |
| 字符串 | [isEmpty](../functions/functionisempty.md) |
| 字符串 | [isNotEmpty](../functions/functionisnotempty.md) |
| 字符串 | [lastIndexOf](../functions/functionlastindexof.md) |
| 字符串 | [length](../functions/functionlength.md) |
| 字符串 | [lower](../functions/functionlower.md) |
| 字符串 | [matchRegExp](../functions/functionmatchregexp.md) |
| 字符串 | [notEqualWithIgnoreCase](../functions/functionnotequalignorecase.md) |
| 字符串 | [replace](../functions/functionreplace.md) |
| 字符串 | [replaceAll](../functions/functionreplaceall.md) |
| 字符串 | [startWith](../functions/functionstartwith.md) |
| 字符串 | [startWithIgnoreCase](../functions/functionstartwithignorecase.md) |
| 字符串 | [substr](../functions/functionsubstr.md) |
| 字符串 | [trim](../functions/functiontrim.md) |
| 字符串 | [upper](../functions/functionupper.md) |
| 字符串 | [uuid](../functions/functionuuid.md) |
