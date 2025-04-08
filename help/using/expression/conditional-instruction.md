---
product: adobe campaign
title: 条件指令(if， then， else)
description: 了解条件指令
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 48fb4944-5b78-4ccd-9b9b-ffe0719e7c21
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '206'
ht-degree: 0%

---

# 条件指令(if， then， else) {#section_cdz_lsk_w3b}


>[!CAUTION]
>
>**正在查找Adobe Journey Optimizer**？ 单击[此处](https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer/using/ajo-home){target="_blank"}获取Journey Optimizer文档。
>
>
>_本文档参考已被Journey Optimizer替换的旧版Journey Orchestration资料。 如果您对访问Journey Orchestration或Journey Optimizer有任何疑问，请联系您的帐户团队。_


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
