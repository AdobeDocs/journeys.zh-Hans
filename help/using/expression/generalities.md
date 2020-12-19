---
product: adobe campaign
solution: Journey Orchestration
title: 概括性
description: 了解高级表达式概述
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# 概括性 {#concept_rcy_qj5_dgb}

## 括号和表达式优先级{#section_edf_fks_bgb}

括号可用于使复杂表达式更易读。 _(&lt;expression>)_ 等效于 _&lt;expression>_。括号还可用于定义评估顺序和关联性。

将从左到右评估表达式。 必须应用算术运算符的相关性：乘法和除法优先于加法和减法。 要强加特定顺序，必须添加括号来限定操作。 例如：

<!--```5 + 2 * 10 = 25, and (5 + 2) * 10 = 70```-->

| 表达式 | 评估 |
|--- |--- |
| `4 + 2 * 10` | <ul><li>“*”优先于“+”:2 * 10被评估→ 20</li><li>4 + 20→ 24</li></ul> |
| `(4 + 2) * 10` | <ul><li>括号将更改优先级：(4 + 2)被评估→ 6</li><li> 6 * 10→ 60</li></ul> |

## 区分大小写{#section_lrb_xh5_dgb}

以下是不同的区分大小写规则：

* 所有运算符（和或等） 应该写成小写。 例如，_`<expression1>`和`<expression2>`_&#x200B;是有效表达式，而表达式&#x200B;_`<expression1>`和`<expression2>`_&#x200B;则不是。
* 所有函数名称均区分大小写。 例如，_inSegment()_&#x200B;有效，而函数&#x200B;_INSEGMENT()_&#x200B;无效。
* 字段引用和常量值区分大小写：它们不是语言的内置元素（与运算符和函数不同），是由最终用户创作的。

## 返回的表达式类型{#section_gyc_435_53b}

根据使用的上下文，表达式编辑器可以返回不同的值。

| 高级表达式编辑器使用 | 预期返回表达式类型 |
|--- |--- |
| 条件（数据源条件、日期条件） | 布尔 |
| 自定义计时器 | dateTimeOnly |
| 操作参数映射 | 任意 |
