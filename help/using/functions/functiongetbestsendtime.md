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
source-git-commit: d6360d616199d597255610959432c7b93fd4e25c

---


# getBestSendTime {#getBestSendTime}

为向个人发送电子邮件提供最佳时间的预测时间。

此函数使用在平台中计算的得分。 分数会根据过去的行为计算将来单击或打开电子邮件的倾向。 请注意，计算得分的算法需要一定数量的数据才能工作。 因此，当它没有足够的数据时，将应用默认时间。 For more information, see [](../building-journeys/wait-activity.md).

要使用此函数，需要 [命名空](../event/selecting-the-namespace.md) 间。

>[!NOTE]
>
>请注意，如果没有足够的数据来执行计算，则最佳发送时间得分可能不可用。 在这种情况下，您将在发布时通知您，默认时间适用。

## 类别

Adobe Experience Platform

## 函数语法

`getBestSendTime(<parameters>)`

## 参数

| 参数 | 说明 | 类型 |
|--- |--- |--- |
| 时间 | 从当前时间开始考虑的小时数(最大：168)以优化电子邮件发送 | `<integer>` |
| 优化类型 | “打开”或“单击” | `<string>` |
| 默认等待时间（以小时为单位） | 如果预测发送时间得分不可用 | `<integer>` |

## 签名和返回类型

`getBestSendTime(<integer>,<string>,<integer>)`

返回dateTime。

## 示例

getBestSendTime(12,&quot;open&quot;,8)

说明：

该函数将返回在未来12小时内发送消息的最佳时间，以便优化旅程实例中个人打开消息的概率。 如果没有足够的数据来执行计算，则返回的时间是从当前时间开始的8小时。
