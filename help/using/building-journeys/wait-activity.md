---
title: 等待活动
description: 了解等待活动
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
source-git-commit: 92bd110c4c91c459c8074184bdb486733ab5f3d7
workflow-type: tm+mt
source-wordcount: '590'
ht-degree: 1%

---


# 等待活动{#section_rlm_nft_dgb}

如果要在路径中执行下一个活动之前等待，可以使用 **[!UICONTROL Wait]** 活动。 它允许您定义执行下一个活动的时刻。 有四个选项可用：

* [持续时间](#duration)
* [固定日期](#fixed_date)
* [自定义](#custom)
* [电子邮件发送时间优化](#email_send_time_optimization)

## 关于等待活动{#about_wait}

以下是在您同时使用多个等待时，如何排定等待的优先级。 如果它们具有相同的时间配置和不同但重叠的条件，则上述位置的等待将是优先顺序。 例如，第一次等待的条件是“女人”，而第二次并行等待的条件是“VIP”。 第一个等待活动将优先

另请注意，如果两个不同的等待是并行的，则无论其垂直位置如何，都将优先排列第一个出现的等待。 例如，如果上方等待1小时，下方等待30分钟，则在30分钟后，将处理30分钟的等待。

如果要将等待限制到特定人群，可以定义一个条件。

>[!NOTE]
>
>最长等待时间为30天。
>
>在测试模式下， **[!UICONTROL Wait time in test]** 该参数允许您定义每个等待活动将持续的时间。 默认时间为 10 秒。这样可以确保快速获得测试结果。 See [](../building-journeys/testing-the-journey.md)

## 持续时间等待{#duration}

选择执行下一个活动之前等待的持续时间。

![](../assets/journey55.png)

## 修复了日期等待{#fixed_date}

选择执行下一个活动的日期。

![](../assets/journey56.png)

## 自定义等待{#custom}

通过此选项，您可以根据来自事件或数据源的字段，使用高级表达式定义自定义日期，例如2020年7月12日下午5点。 它不允许您定义自定义持续时间，例如，7天。 表达式编辑器中的表达式应提供dateTimeOnly格式。 请参见 [](../expression/expressionadvanced.md)。有关dateTimeOnly格式的详细信息，请参阅 [](../expression/data-types.md)。

>[!NOTE]
>
>您可以利用dateTimeOnly表达式或使用函数转换为dateTimeOnly。 例如：toDateTimeOnly(@{事件.offerOpened.活动.endTime}),事件中的字段为2016-08-12T09:46:06。
>
>您 **旅程的属** 性中应包含时区。 因此，今天无法从接口直接指向完全ISO-8601时间戳混合时间和时区偏移，如2016-08-12T09:46:06.982-05。 请参见 [](../building-journeys/timezone-management.md)。

![](../assets/journey57.png)

## 电子邮件发送时间优化{#email_send_time_optimization}

>[!CAUTION]
>
>电子邮件发送时间优化功能仅适用于使用Adobe Experience Platform数据连 [接器的客户](https://docs.adobe.com/content/help/en/campaign-standard/using/developing/mapping-campaign-and-aep-data/aep-about-data-connector.html)。

这种等待使用在Adobe Experience Platform计算的得分。 该得分会根据过去的行为计算将来单击或打开电子邮件的倾向。 请注意，计算得分的算法需要一定数量的数据才能工作。 因此，当数据不足时，将应用默认等待时间。 发布时，将通知您默认时间已应用。

>[!NOTE]
>
>旅程的第一个事件必须有命名空间。
>
>此功能仅在活动后可 **[!UICONTROL Email]** 用。 你得有Adobe Campaign Standard。

1. 在字段 **[!UICONTROL Amount of time]** 中，定义要考虑优化电子邮件发送的小时数。
1. 在字段 **[!UICONTROL Optimization type]** 中，选择优化应增加单击还是打开次数。
1. 在字 **[!UICONTROL Default time]** 段中，定义预测发送时间得分不可用时的默认等待时间。

   >[!NOTE]
   >
   >请注意，发送时间得分可能不可用，因为没有足够的数据来执行计算。 在这种情况下，将在发布时通知您应用默认时间。

![](../assets/journey57bis.png)
