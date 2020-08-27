---
title: 概括性
description: 了解高级表达式概述
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 10d4fd57e9a801dab2310b2b511bf99cf1d9170a
workflow-type: tm+mt
source-wordcount: '214'
ht-degree: 2%

---


# 概括性 {#concept_rcy_qj5_dgb}

## 括号和表达式优先级{#section_edf_fks_bgb}

括号可用于使复杂表达式更易读。 _(&lt;表达式>_ )等效 _于&lt;表达式_> 括号还可用于定义评估顺序和关联性。

将从左到右评估表达式。 必须应用算术运算符的相关性：乘法和除法优先于加法和减法。 要强加特定顺序，必须添加括号来限定操作。 例如：

<!--```5 + 2 * 10 = 25, and (5 + 2) * 10 = 70```-->

| 表达式 | 评估 |
|--- |--- |
| `4 + 2 * 10` | <ul><li>“*”优先于“+”:2 * 10被评估→ 20</li><li>4 + 20 → 24</li></ul> |
| `(4 + 2) * 10` | <ul><li>括号将更改优先级：(4 + 2)被评估→ 6</li><li> 6 * 10 → 60</li></ul> |

## 区分大小写{#section_lrb_xh5_dgb}

以下是不同的区分大小写规则：

* 所有运算符（和或等） 应该写成小写。 例如， _`<expression1>`并且`<expression2>`_ 是有效表达式，而表达式 _`<expression1>`AND`<expression2>`_ 则不是。
* 所有函数名称均区分大小写。 例如， _inSegment()_ 有效，而函 _数INSEGMENT()_ 无效。
* 字段引用和常量值区分大小写：它们不是语言的内置元素（与运算符和函数不同），是由最终用户创作的。

## 返回的表达式类型{#section_gyc_435_53b}

根据使用的上下文，表达式编辑器可以返回不同的值。

| 高级表达式编辑器使用 | 预期返回表达式类型 |
|--- |--- |
| 条件（数据源条件、日期条件） | 布尔 |
| 自定义计时器 | dateTimeOnly |
| 操作参数映射 | 任意 |
