---
product: adobe campaign
solution: Journey Orchestration
title: 条件说明(if， then， else)
description: 了解条件说明
feature: Journeys
role: Data Engineer
level: Experienced
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '165'
ht-degree: 0%

---


# 条件指令(if， then， else){#section_cdz_lsk_w3b}

高级编辑器中支持条件指令（如果，则为else）。 它允许定义更复杂的表达式。 它由以下元素组成：

* **[!UICONTROL if]**:要首先计算的条件。
* **[!UICONTROL then]**:在条件评估结果为真的情况下要评估的表达式。
* **[!UICONTROL else]**:在条件评估结果为false时要评估的表达式。

>[!NOTE]
>
>所有表达式周围都需要括号。

```
if  (<expression1>)
then
   (<expression2>)
else
   (<expression3>)
```

`<expression1>` 必须返回 **布尔**。

`<expression2>` 并且 `<expression3>` 必须具有相同的类型或兼容类型。支持的签名和返回的类型有：

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

条件说明允许您通过减少条件活动数来优化旅程工作流。 例如，在同一操作活动内，您只能使用一个条件表达式为字段定义指定两个替代项。

操作活动的示例（对于需要作为条件指令结果的字符串的字段）：

```
if (startWithIgnoreCase(@{eventiOSPushPermissionAllowed.device.model}, 'iPad') or startWithIgnoreCase(@{eventiOSPushPermissionAllowed.device.model}, 'iOS'))
then
   ('apns')
else
   ('fcm')
```
