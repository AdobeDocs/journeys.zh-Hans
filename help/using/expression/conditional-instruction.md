---
product: adobe campaign
title: 条件指令(if， then， else)
description: 了解条件指令
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 48fb4944-5b78-4ccd-9b9b-ffe0719e7c21
source-git-commit: 9c33474a72542b6ad1d1ae0854622dfd7575f2d9
workflow-type: tm+mt
source-wordcount: '161'
ht-degree: 0%

---

# 条件指令(if， then， else) {#section_cdz_lsk_w3b}

高级编辑器中支持条件指令(if， then， else)。 它允许定义更复杂的表达式。 它由以下元素组成：

* **[!UICONTROL if]**：首先计算的条件。
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

`<expression1>` 必须返回 **布尔型**.

`<expression2>` 和 `<expression3>` 必须具有相同类型或兼容类型。 支持的签名和返回的类型包括：

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
