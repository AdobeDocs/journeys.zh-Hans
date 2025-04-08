---
product: adobe campaign
title: 更改属性
description: 了解如何更改属性
feature: Journeys
role: User
level: Intermediate
exl-id: 06d26078-b9b8-4dc4-918d-0f2426d00f54
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '598'
ht-degree: 2%

---

# 更改属性 {#concept_prq_wqt_52b}



>[!CAUTION]
>
>**正在查找Adobe Journey Optimizer**？ 单击[此处](https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer/using/ajo-home){target="_blank"}获取Journey Optimizer文档。
>
>
>_本文档参考已被Journey Optimizer替换的旧版Journey Orchestration资料。 如果您对访问Journey Orchestration或Journey Optimizer有任何疑问，请联系您的帐户团队。_


单击右上角的铅笔图标可访问历程的属性。

如果您是管理员，则可以更改历程的名称、添加描述、允许重新进入、选择开始和结束日期并定义&#x200B;**[!UICONTROL Timeout and error]**&#x200B;持续时间。

对于实时历程，此屏幕显示发布日期和发布历程的用户名称。

**复制技术详细信息**&#x200B;允许您复制有关历程的技术信息，供支持团队用于进行故障排除。 复制了以下信息：JourneyVersion UID、OrgID、orgName、sandboxName、lastDeployedBy、lastDeployedAt。

![](../assets/journey32.png)

## 入口{#entrance}

默认情况下，允许重入新的历程。您可以取消选中“一次性”旅程选项，例如，如果您想要在人员进入商店时提供一次性礼品。 在这种情况下，您不希望客户能够重新进入历程并再次收到选件。

历程“结束”时，其状态为&#x200B;**[!UICONTROL Closed (no entrance)]**。 历程将停止让新个人进入历程。 已在历程中的人员将正常完成历程。

在默认全局超时30天后，历程将切换到&#x200B;**已完成**&#x200B;状态。 请参阅此[部分](#global_timeout)。

## 历程活动中的超时和错误 {#timeout_and_error}

编辑操作或条件活动时，您可以定义替代路径以防出现错误或超时。 如果对第三方系统询问的活动处理超过了历程属性（**[!UICONTROL Timeout and  error]**&#x200B;字段）中定义的超时持续时间，将选择第二条路径来执行潜在的回退操作。

授权值介于1和30秒之间。

如果历程对时间敏感（例如：对人员的实时位置做出反应），我们建议您定义一个非常短的&#x200B;**[!UICONTROL Timeout and error]**&#x200B;值，因为您的操作延迟时间不能超过几秒。 如果您的旅程不太时效性，则可以使用较长的值，为调用的系统留出更多时间来发送有效响应。

[!DNL Journey Orchestration]还使用全局超时。 请参阅[下一节](#global_timeout)。

## 全局历程超时 {#global_timeout}

除了历程活动中使用的[timeout](#timeout_and_error)之外，还有全局历程超时，该超时未显示在界面中且无法更改。 此超时将在个人进入历程30天后停止个人进度。 这意味着个人的历程不能超过30天。 在30天超时之后，将删除个人的数据。 超时期间结束时仍在历程中流动的个人将被停止，并且他们将被视为报告中的错误。

>[!NOTE]
>
>[!DNL Journey Orchestration]不会直接对隐私选择退出、访问或删除请求做出反应。 但是，全局超时可确保个人在任何历程中的停留时间不超过30天。

由于30天历程超时，当历程不允许重新进入时，我们无法确保重新进入阻止将工作超过30天。 事实上，当我们删除有关进入旅程30天后进入旅程的人员的所有信息时，我们无法知道该人员是超过30天前进入的。

## 时区和配置文件时区 {#timezone}

时区在历程级别定义。

您可以输入固定时区，或使用Adobe Experience Platform配置文件定义历程时区。

有关时区管理的详细信息，请参阅[此页面](../building-journeys/timezone-management.md)。
