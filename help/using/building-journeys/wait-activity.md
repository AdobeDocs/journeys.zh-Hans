---
product: adobe campaign
title: 等待活动
description: 了解等待活动
feature: Journeys
role: User
level: Intermediate
exl-id: 819ff3c3-0e3e-4d86-b5d2-10c5b10d19e6
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '412'
ht-degree: 7%

---

# 等待活动{#section_rlm_nft_dgb}


>[!CAUTION]
>
>**正在查找Adobe Journey Optimizer**？ 单击[此处](https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer/using/ajo-home){target="_blank"}获取Journey Optimizer文档。
>
>
>_本文档参考已被Journey Optimizer替换的旧版Journey Orchestration资料。 如果您对访问Journey Orchestration或Journey Optimizer有任何疑问，请联系您的帐户团队。_



如果要等待再执行路径中的下一个活动，则可以使用&#x200B;**[!UICONTROL Wait]**&#x200B;活动。 这让您可以定义执行下一个活动的时刻。提供了三个选项：

* [持续时间](#duration)
* [自定义](#custom)
  <!--* [Email send time optimization](#email_send_time_optimization)-->

## 关于等待活动{#about_wait}

下面显示了当您同时使用多个等待时，如何区分等待的优先级。 如果它们具有相同的时间配置和不同但重叠的条件，则上面定位的等待将获得优先顺序。 例如，第一次等待的条件是“成为女性”，而第二次同时等待的条件是“成为VIP”。 第一个等待活动将得到优先处理。

另请注意，如果两个不同的等待是并行的，则优先处理第一个出现的等待，而不考虑其垂直位置。 例如，如果等待1小时以上，等待30分钟以下，则在30分钟后会处理30分钟等待。

>[!NOTE]
>
>最长等待时间为30天。
>
>在测试模式下，**[!UICONTROL Wait time in test]**&#x200B;参数允许您定义每个等待活动的持续时间。 默认时间为 10 秒。这将确保您快速获得测试结果。 查看[此页面](../building-journeys/testing-the-journey.md)

## 持续时间等待{#duration}

选择下一个活动执行前等待的持续时间。

![](../assets/journey55.png)

## 自定义等待{#custom}

此选项允许您使用基于来自事件或数据源的字段的高级表达式来定义自定义日期，例如2020年7月12日下午5点。 它不允许您定义自定义持续时间，例如7天。 表达式编辑器中的表达式应提供dateTimeOnly格式。 查看[此页面](../expression/expressionadvanced.md)。 有关dateTimeOnly格式的详细信息，请参阅[此页面](../expression/data-types.md)。

>[!NOTE]
>
>您可以利用dateTimeOnly表达式或使用函数转换为dateTimeOnly。 例如： toDateTimeOnly(@{Event.offerOpened.activity.endTime})，事件中的字段格式为2016-08-12T09:46:06Z。
>
>历程的属性中应为&#x200B;**时区**。 因此，目前无法从界面直接指向完整的ISO-8601时间戳混合时间和时区偏移，例如2016-08-12T09:46:06.982-05。 请参阅[此页](../building-journeys/timezone-management.md)。

![](../assets/journey57.png)

<!--## Email send time optimization{#email_send_time_optimization}

>[!CAUTION]
>
>The email send time optimization capability is only available to customers who use the [Adobe Experience Platform Data Connector](https://docs.adobe.com/content/help/en/campaign-standard/using/developing/mapping-campaign-and-aep-data/aep-about-data-connector.html).

This type of wait uses a score calculated in the Adobe Experience Platform. The score calculates the propensity to click or open an email in the future based on past behavior. Note that the algorithm calculating the score needs a certain amount of data to work. As a result, when it does not have enough data, the default wait time will apply. At publication time, you'll be notified that the default time applies.

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
