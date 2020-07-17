---
title: getBestSendTime
description: 了解函数getBestSendTime
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
source-git-commit: eb4474313d3c0470448f9959ed757902ef0ecd2a
workflow-type: tm+mt
source-wordcount: '239'
ht-degree: 2%

---


# getBestSendTime {#getBestSendTime}

为向个人发送电子邮件提供最佳时间的预测时间。

此函数使用在Adobe Experience Platform中计算的得分。 该得分会根据过去的行为计算将来单击或打开电子邮件的倾向。 请注意，计算得分的算法需要一定数量的数据才能工作。 因此，当它没有足够的数据时，将应用默认时间。 For more information, see [](../building-journeys/wait-activity.md).

要使用此函数，需 [要命名空间](../event/selecting-the-namespace.md) 。

>[!NOTE]
>
>请注意，如果没有足够的数据来执行计算，则最佳发送时间得分可能不可用。 在这种情况下，将在发布时通知您应用默认时间。

## 类别

Adobe Experience Platform

## 函数语法

`getBestSendTime(<parameters>)`

## 参数

| 参数 | 说明 | 类型 |
|--- |--- |--- |
| 时间 | 从当前时间开始考虑的小时数(最大： 168)优化电子邮件发送 | `<integer>` |
| 优化类型 | “打开”或“单击” | `<string>` |
| 默认等待时间（以小时为单位） | 如果预测发送时间得分不可用 | `<integer>` |

## 签名和返回类型

`getBestSendTime(<integer>,<string>,<integer>)`

返回dateTime。

## 示例

getBestSendTime(12,&quot;open&quot;,8)

说明：

该函数将在接下来的12小时内返回发送消息的最佳时间，以优化旅程实例中个人打开消息的概率。 如果没有足够的数据来执行计算，则返回的时间为当前时间的8小时。
