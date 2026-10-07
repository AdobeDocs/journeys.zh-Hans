---
product: adobe campaign
title: 条件指令(if， then， else)
description: 了解条件指令
feature: Journeys
role: Developer
level: Experienced
exl-id: 48fb4944-5b78-4ccd-9b9b-ffe0719e7c21
product_v2:
  - id: cf67d108-ecf9-4fde-af49-3a3c39083bc8
    internal-label: Journey Orchestration
feature_v2:
  - id: 7de3230f-9523-5ba5-8d5c-2313288b27ef
    internal-label: Journeys
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 255cd6677e7c9ebff63ea9a1028a042c19e63ecc
workflow-type: tm+mt
source-wordcount: '214'
ht-degree: 25%
---
# 条件指令(if， then， else) {#section_cdz_lsk_w3b}


>[!CAUTION]
>
>**希望了解 Adobe Journey Optimizer**？ 请单击[此处](https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer/using/ajo-home){target="_blank"}获取 Journey Optimizer 文档。
>
>
>_本文档参考已被 Journey Optimizer 取代的旧版 Journey Orchestration 资料。 如果您对访问 Journey Orchestration 或 Journey Optimizer 有任何疑问，请联系帐户团队。_


高级编辑器中支持条件指令(if， then， else)。 它允许定义更复杂的表达式。 它由以下元素组成：

* **[!UICONTROL if]**：首先要计算的条件。
* **[!UICONTROL then]**：条件评估结果为true时要评估的表达式。
* **[!UICONTROL else]**：条件评估结果为false时要评估的表达式。

>[!NOTE]
>
>所有表达式均需要括号。

```json
if  (<expression1>)
then
   (<expression2>)
else
   (<expression3>)
```

`<expression1>`必须返回&#x200B;**布尔值**。

`<expression2>`和`<expression3>`必须具有相同的类型或兼容的类型。 支持的签名和返回的类型包括：

```json
boolean,boolean : boolean
dateTime,dateTime : dateTime
dateTimeOnly,dateTimeOnly : dateTimeOnly
decimal,integer : decimal
integer,decimal : integer
integer,decimal : decimal
duration,duration : duration
string,string : string
listBoolean,listBoolean : listBoolean
listDateTime,listDateTime : listDateTime
listDateTimeOnly,listDateTimeOnly : listDateTimeOnly
listDateOnly,listDateOnly : listDateOnly
listDecimal,listDecimal : listDecimal
listInteger,listInteger : listInteger
listString,listString : listString
```

**用法**

条件指令允许您通过减少条件活动的数量来优化历程工作流。 例如，在同一操作活动中，您可以仅使用一个条件表达式为字段定义指定两个替代项。

操作活动的示例（用于预期字符串作为条件指令结果的字段）：

```json
if (startWithIgnoreCase(@{eventiOSPushPermissionAllowed.device.model}, 'iPad') or startWithIgnoreCase(@{eventiOSPushPermissionAllowed.device.model}, 'iOS'))
then
   ('apns')
else
   ('fcm')
```
