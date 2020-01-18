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
source-git-commit: 017d502e21605b3e0b8c61e5fea0b4f6a65d4470

---


# 等待活动{#section_rlm_nft_dgb}

如果要在执行路径中的下一个活动之前等待，则可以使用活 **[!UICONTROL Wait]**动。 它允许您定义执行下一个活动的时间。 有四个选项可用：

* [持续时间](#duration)
* [固定日期](#fixed_date)
* [自定义](#custom)
* [电子邮件发送时间优化](#email_send_time_optimization)

## 关于等待活动{#about_wait}

以下是在您同时使用多个等待时，如何排定等待的优先级。 如果它们具有相同的时间配置和不同但重叠的条件，则上述位置的等待将是优先顺序的等待。 例如，第一次等待的条件是“作为女性”，而第二次等待的条件是“作为VIP”。 将优先处理第一个等待活动

另请注意，如果两个不同的等待是并行的，则无论其垂直位置如何，都将对最先发生的等待进行排序。 例如，如果1小时的等待时间在上方，30分钟的等待时间在下面，30分钟之后，30分钟的等待时间将被处理。

如果要将等待限制到特定人群，可以定义一个条件。

>[!NOTE]
>
>最长等待时间为30天。
>
>在测试模式下，所有等待活动都会自动设置为最后5秒。 这样，您就可以快速访问测试结果。

## 持续等待{#duration}

选择执行下一个活动之前等待的持续时间。

![](../assets/journey55.png)

## 修复了等待日期{#fixed_date}

选择执行下一个活动的日期。 定义固定日期时，必须指定时区。 请参见 [](../building-journeys/timezone-management.md)。

![](../assets/journey56.png)

## 自定义等待{#custom}

通过此选项，您可以使用基于来自事件或数据源的字段的高级表达式定义自定义日期，例如2020年7月12日下午5点。 它不允许您定义自定义持续时间，例如7天。 表达式编辑器中的表达式应提供dateTimeOnly格式。 请参见 [](../expression/expressionadvanced.md)。有关dateTimeOnly格式的详细信息，请参阅 [](../expression/data-types.md)

>[!NOTE]
>
>您可以利用dateTimeOnly表达式或使用函数转换为dateTimeOnly。 例如：toDateTimeOnly(@{Event.offerOpened.activity.endTime})，事件中的字段为2016-08-12T09:46:06格式。
>
>时 **** 区应位于自定义等待配置窗格的其他位置。 因此，如2016-08-12T09:46:06.982-05那样，今天不可能从界面直接指向完全ISO-8601时间戳混合时间和时区偏移。 请参见 [](../building-journeys/timezone-management.md)。

![](../assets/journey57.png)

## 电子邮件发送时间优化{#email_send_time_optimization}

>[!CAUTION]
>
>电子邮件发送时间优化功能仅适用于使用Adobe Campaign Standard Data service功能的客户。

此类等待使用在平台中计算的得分。 分数会根据过去的行为计算将来单击或打开电子邮件的倾向。 请注意，计算得分的算法需要一定数量的数据才能工作。 因此，当它没有足够的数据时，将应用默认的等待时间。 在发布时，您会收到默认时间的通知。

>[!NOTE]
>
>旅程的第一个事件必须有一个命名空间。
>
>此功能仅在活动后可 **[!UICONTROL Email]**用。 您需要安装Adobe Campaign Standard。

1. 在字段 **[!UICONTROL Amount of time]**中，定义要考虑优化电子邮件发送的小时数。
1. 在字段 **[!UICONTROL Optimization type]**中，选择优化应增加单击还是打开。
1. 在“默 **认时间** ”字段中，定义当预测发送时间得分不可用时要等待的默认时间。

   >[!NOTE]
   >
   >请注意，发送时间得分可能不可用，因为没有足够的数据来执行计算。 在这种情况下，您将在发布时通知您，默认时间适用。

![](../assets/journey57bis.png)
