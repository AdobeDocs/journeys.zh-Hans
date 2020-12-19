---
product: adobe campaign
solution: Journey Orchestration
title: 等待活动
description: 了解等待活动
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '384'
ht-degree: 3%

---


# 等待活动{#section_rlm_nft_dgb}

如果要在路径中执行下一个活动之前等待，可以使用&#x200B;**[!UICONTROL Wait]**&#x200B;活动。 它允许您定义执行下一个活动的时刻。 有四个选项可用：

* [持续时间](#duration)
* [固定日期](#fixed_date)
* [自定义](#custom)

<!--* [Email send time optimization](#email_send_time_optimization)-->

## 关于等待活动{#about_wait}

以下是在您同时使用多个等待时，如何排定等待的优先级。 如果它们具有相同的时间配置和不同但重叠的条件，则上述位置的等待将是优先顺序。 例如，第一次等待的条件是“女人”，而第二次并行等待的条件是“VIP”。 第一个等待活动将优先

另请注意，如果两个不同的等待是并行的，则无论其垂直位置如何，都将优先排列第一个出现的等待。 例如，如果上面有1小时的等待，下面有30分钟的等待，30分钟后，将处理30分钟的等待。

如果要将等待限制到特定人群，可以定义一个条件。

>[!NOTE]
>
>最长等待时间为30天。
>
>在测试模式下，**[!UICONTROL Wait time in test]**&#x200B;参数允许您定义每个等待活动将持续的时间。 默认时间为 10 秒。这样可以确保快速获得测试结果。 请参阅[此页](../building-journeys/testing-the-journey.md)

## 等待持续时间{#duration}

选择执行下一个活动之前等待的持续时间。

![](../assets/journey55.png)

## 固定日期等待{#fixed_date}

选择执行下一个活动的日期。

![](../assets/journey56.png)

## 自定义等待{#custom}

通过此选项，您可以根据来自事件或数据源的字段，使用高级表达式定义自定义日期，例如2020年7月12日下午5点。 它不允许您定义自定义持续时间，例如，7天。 表达式编辑器中的表达式应提供dateTimeOnly格式。 请参阅[此页](../expression/expressionadvanced.md)。有关dateTimeOnly格式的详细信息，请参阅[此页](../expression/data-types.md)。

>[!NOTE]
>
>您可以利用dateTimeOnly表达式或使用函数转换为dateTimeOnly。 例如：```toDateTimeOnly(@{Event.offerOpened.activity.endTime})```,事件中的字段格式为2016-08-12T09:46:06Z。
>
>旅程属性中应显示&#x200B;**时区**。 因此，今天无法从接口直接指向完全ISO-8601时间戳混合时间和时区偏移，如2016-08-12T09:46:06.982-05。 请参阅[此页](../building-journeys/timezone-management.md)。

![](../assets/journey57.png)

<!--## Email send time optimization{#email_send_time_optimization}

>[!CAUTION]
>
>The email send time optimization capability is only available to customers who use the [Adobe Experience Platform Data Connector](https://docs.adobe.com/content/help/en/campaign-standard/using/developing/mapping-campaign-and-aep-data/aep-about-data-connector.html).

This type of wait uses a score calculated in the Adobe Experience Platform. The score calculates the propensity to click or open an email in the future based on past behavior. Note that the algorithm calculating the score needs a certain amount of data to work. As a result, when it does not have enough data, the default wait time will apply. At publication time, you’ll be notified that the default time applies.

>[!NOTE]
>
>The first event of your journey must have a namespace.
>
>This capability is only available after an **[!UICONTROL Email]** activity. You need to have Adobe Campaign Standard.

1. In the **[!UICONTROL Amount of time]** field, define the number of hours to consider to optimize email sending.
1. In the **[!UICONTROL Optimization type]** field, choose if the optimization should increase clicks or opens.
1. In the **[!UICONTROL Default time]** field, define the default time to wait if the predictive send time score is not available.

    >[!NOTE]
    >
    >Note that the send time score can be unavailable because there is not enough data to perform the calculation. In this case, you will be informed, at publication time, that the default time applies.

![](../assets/journey57bis.png)-->
