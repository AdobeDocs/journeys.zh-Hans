---
product: adobe campaign
title: 更改属性
description: 了解如何更改属性
feature: Journeys
role: User
level: Intermediate
exl-id: 06d26078-b9b8-4dc4-918d-0f2426d00f54
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '543'
ht-degree: 0%

---

# 更改属性 {#concept_prq_wqt_52b}

单击右上方的铅笔图标以访问历程的属性。

您可以更改历程名称、添加描述、允许重新进入、选择开始和结束日期并定义 **[!UICONTROL Timeout and error]** 持续时间（如果您是管理员）。

对于实时历程，此屏幕显示发布日期和发布历程的用户名称。

的 **复制技术详细信息** 允许您复制有关历程的技术信息，供支持团队用于进行故障排除。 将复制以下信息：JourneyVersion UID、OrgID、orgName、sandboxName、lastDeployedBy、lastDeployedAt。

![](../assets/journey32.png)

## 入口{#entrance}

默认情况下，新历程允许重新进入。 您可以取消选中“一次性”历程的选项，例如，如果您希望在某人进入商店时提供一次性礼品。 在这种情况下，您不希望客户能够重新进入历程并再次接收选件。

当历程“结束”时，将具有状态 **[!UICONTROL Closed (no entrance)]**. 历程将不再让新人进入历程。 已在历程中的人员将正常完成历程。

在默认的全局超时为30天后，历程将切换到 **已完成** 状态。 请参阅 [部分](#global_timeout).

## 历程活动中的超时和错误 {#timeout_and_error}

在编辑操作或条件活动时，您可以定义出现错误或超时的替代路径。 如果查询第三方系统的活动的处理超过了历程属性中定义的超时持续时间(**[!UICONTROL Timeout and  error]** 字段)，则将选择第二个路径来执行潜在的回退操作。

授权值介于1到30秒之间。

我们建议您定义一个非常短的 **[!UICONTROL Timeout and error]** 值(例如：响应人员的实时位置)，因为您不能将操作延迟超过几秒钟。 如果您的历程不太时间敏感，您可以使用较长的值为调用的系统提供更多时间以发送有效响应。

[!DNL Journey Orchestration] 也使用全局超时。 请参阅 [下一部分](#global_timeout).

## 全局历程超时 {#global_timeout}

除 [超时](#timeout_and_error) 在历程活动中，还存在全局历程超时，该超时未显示在界面中，且无法更改。 此超时将在个人进入后30天停止历程中的进度。 这意味着个人的历程不能持续超过30天。 在30天超时期后，将删除个人数据。 在超时时段结束时仍在历程中流动的个人将被停止，并将其作为报表中的错误考虑在内。

>[!NOTE]
>
>[!DNL Journey Orchestration] 不会直接对隐私选择退出、访问或删除请求做出反应。 但是，全局超时可确保个人在任何历程中停留的时间不得超过30天。

由于历程超时30天，因此当不允许历程重新进入时，我们无法确保重新进入阻止的工作时间超过30天。 事实上，由于我们删除了有关在进入历程30天后进入历程的人员的所有信息，因此我们无法知道之前进入的人员，即30天前。

## 时区和配置文件时区 {#timezone}

在历程级别定义时区。

您可以输入固定时区或使用Adobe Experience Platform配置文件定义历程时区。

有关时区管理的更多信息，请参阅 [本页](../building-journeys/timezone-management.md).
