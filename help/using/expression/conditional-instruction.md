---
title: 条件说明(if, then, else)
description: 了解条件说明
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: b852c08a488a1bec02b8b31a1fccf1a8773b99af
workflow-type: tm+mt
source-wordcount: '161'
ht-degree: 0%

---


# 条件说明(if, then, else) {#section_cdz_lsk_w3b}

高级编辑器中支持条件指令（如果，则为else）。 它允许定义更复杂的表达式。 它由以下元素组成：

* **[!UICONTROL if]**:要先评估的条件。
* **[!UICONTROL then]**:条件评估结果为真时要评估的表达式。
* **[!UICONTROL else]**:在条件评估结果为false时要评估的表达式。

>[!NOTE]
>
>括号在所有表达式周围。

```
if  (<expression1>)
then
   (<expression2>)
else
   (<expression3>)
```

`<expression1>` 必须返回 **布尔**。

`<expression2>` 并且 `<expression3>` 必须具有相同的类型或兼容类型。 支持的签名和返回类型包括：

```
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
listDecimal,listDecimal : listDecimal
listInteger,listInteger : listInteger
listString,listString : listString
```

**使用情况**

条件说明允许您通过减少条件活动数来优化旅程工作流。 例如，在同一操作活动内，您只能使用一个条件表达式为字段定义指定两个替代选项。

操作活动的示例（对于需要作为条件指令结果的字符串的字段）:

```
if (startWithIgnoreCase(@{eventiOSPushPermissionAllowed.device.model}, 'iPad') or startWithIgnoreCase(@{eventiOSPushPermissionAllowed.device.model}, 'iOS'))
then
   ('apns')
else
   ('fcm')
```
