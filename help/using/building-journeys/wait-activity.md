---
product: adobe campaign
title: 等待活动
description: 了解等待活动
feature: 历程
role: User
level: Intermediate
exl-id: 819ff3c3-0e3e-4d86-b5d2-10c5b10d19e6
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '387'
ht-degree: 4%

---

# 等待活动{#section_rlm_nft_dgb}

如果要在路径中执行下一个活动之前等待，可以使用&#x200B;**[!UICONTROL Wait]**&#x200B;活动。 利用该活动，可定义执行下一个活动的时间。 提供了以下三个选项：

* [持续时间](#duration)
* [固定日期](#fixed_date)
* [自定义](#custom)

<!--* [Email send time optimization](#email_send_time_optimization)-->

## 关于等待活动{#about_wait}

下面是当您同时使用多个等待时，如何排定等待的优先级。 如果它们具有相同的时间配置和不同但重叠的条件，则位于上方的等待将是优先级。 例如，第一次等待的条件是“为女人”，而第二次并行等待的条件是“为VIP”。 第一个等待活动将按优先顺序排列

另请注意，如果两个不同的等待同时进行，则无论其垂直位置如何，发生在第一个等待的等待都将按优先级排列。 例如，如果高于1小时等待，低于30分钟等待，则30分钟后将处理30分钟等待。

如果要限制对特定群体的等待，可以定义条件。

>[!NOTE]
>
>最长等待时长为30天。
>
>在测试模式下，**[!UICONTROL Wait time in test]**&#x200B;参数允许您定义每个等待活动的持续时间。 默认时间为 10 秒。这样可以确保快速获得测试结果。 请参阅[此页面](../building-journeys/testing-the-journey.md)

## 持续等待{#duration}

选择在执行下一个活动之前等待的持续时间。

![](../assets/journey55.png)

## 修复了日期等待{#fixed_date}

选择执行下一个活动的日期。

![](../assets/journey56.png)

## 自定义等待{#custom}

利用此选项，可使用基于来自事件或数据源的字段的高级表达式，定义自定义日期，例如2020年7月12日下午5点。 它不允许您定义自定义持续时间，例如7天。 表达式编辑器中的表达式应提供dateTimeOnly格式。 请参阅[此页](../expression/expressionadvanced.md)。有关dateTimeOnly格式的更多信息，请参阅[此页面](../expression/data-types.md)。

>[!NOTE]
>
>您可以使用dateTimeOnly表达式或使用函数转换为dateTimeOnly。 例如：toDateTimeOnly(@{Event.offerOpened.activity.endTime})，事件中的字段格式为2016-08-12T09:46:06Z。
>
>历程的属性中需要&#x200B;**时区**。 因此，今天无法从接口直接指向完整的ISO-8601时间戳，该时间戳将时间和时区偏移混合在一起，如2016-08-12T09:46:06.982-05。 请参阅[此页](../building-journeys/timezone-management.md)。

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
