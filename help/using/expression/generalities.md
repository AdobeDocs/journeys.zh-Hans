---
product: adobe campaign
title: 概述
description: 瞭解進階運算式一般性
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: ba474219-7c9e-4f93-8e9c-16c317131614
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '214'
ht-degree: 5%

---

# 概述 {#concept_rcy_qj5_dgb}

## 括弧與運算式優先順序{#section_edf_fks_bgb}

括弧可用來讓複雜的運算式更容易閱讀。 _(&lt;expression>)_ 等同於 _&lt;expression>_. 括弧也可用來定義評估順序和關聯性。

運算式將由左至右評估。 必須套用算術運運算元的關聯性：乘法和除法優先於加法和減法。 為了強制特定順序，必須新增括弧以分隔操作。 例如：

<!--```5 + 2 * 10 = 25, and (5 + 2) * 10 = 70```-->

| 表达式 | 评估 |
|--- |--- |
| `4 + 2 * 10` | <ul><li>&#39;*&#39;優先順序高於&#39;+&#39;：2 * 10→20計算</li><li>4 + 20 → 24</li></ul> |
| `(4 + 2) * 10` | <ul><li>括弧會變更優先順序： (4 + 2)的評估值→6</li><li> 6 * 10 → 60</li></ul> |

## 区分大小写{#section_lrb_xh5_dgb}

以下是不同的區分大小寫規則：

* 所有運運算元（和、或等） 應該寫成小寫。 例如， _`<expression1>`和`<expression2>`_ 是有效的運算式，但運算式 _`<expression1>`和`<expression2>`_ 不是。
* 所有函式名稱都區分大小寫。 例如， _inSegment()_ 是有效的，而函式 _INSEGMENT()_ 不是。
* 欄位參照和常數值區分大小寫：它們不是語言的內建元素（與運運算元和函式相反），而是由一般使用者編寫。

## 傳回的運算式型別{#section_gyc_435_53b}

根據使用內容，運算式編輯器可傳回不同的值。

| 進階運算式編輯器使用方式 | 預期傳回的運算式型別 |
|--- |--- |
| 條件（資料來源條件、日期條件） | 布尔 |
| 自訂計時器 | dateTimeOnly |
| 動作引數對應 | 任何 |
