---
title: 更改属性
description: 了解如何更改属性
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
source-wordcount: '471'
ht-degree: 0%

---



# 更改属性 {#concept_prq_wqt_52b}

单击右上角的铅笔图标以访问旅程的属性。

您可以更改旅程名称、添加描述、允许重新进入、选择开始和结束日期，以及定义持 **[!UICONTROL Timeout and error]** 续时间（如果您是管理员）。

![](../assets/journey32.png)

## 入口{#entrance}

默认情况下，新旅程允许重新进入。 您可以取消选中“一次性拍摄”旅程选项，例如，当某人进入商店时，您要优惠一次性馈赠。 在这种情况下，您不希望客户能够重新进入旅程并再次收到优惠。

当旅程“结束”时，它将具有状态 **[!UICONTROL Closed (no entrance)]**。 旅程将停止让新人进入旅程。 旅程中已有的人将正常完成旅程。

## 旅程活动超时和错误 {#timeout_and_error}

在编辑操作或条件活动时，您可以在出错或超时的情况下定义替代路径。 如果询问第三方系统的活动的处理超过在旅程的属性（字段）中定义的超时持续时间&#x200B;**[!UICONTROL Timeout and  error]** ，则将选择第二路径以执行潜在的回退操作。

授权值介于1到30秒之间。

如果您的旅程对时间很敏感， **[!UICONTROL Timeout and error]** 我们建议您定义一个非常短的值(例如： 对人的实时位置做出响应)，因为您不能将操作延迟超过几秒钟。 如果您的旅程对时间不太敏感，您可以使用较长的值为调用的系统提供更多时间，以发送有效的响应。

[!DNL Journey Orchestration] 还使用全局超时。 请参阅下 [一节](#global_timeout)。

## 全局旅程超时 {#global_timeout}

除了在旅程 [活动中使](#timeout_and_error) 用的超时外，还存在全局旅程超时，该超时不会显示在界面中，并且无法更改。 此超时将在个人进入后30天停止旅程中的进度。 这意味着个人旅程不能超过30天。 在30天超时期后，将删除个人的数据。 在超时期结束时仍在旅程中流动的个人将被停止，并将其作为报告中的错误予以考虑。

>[!NOTE]
>
>[!DNL Journey Orchestration] 不会直接对隐私选择退出、访问或删除请求做出响应。 但是，全局超时可确保个人在任何旅程中停留不超过30天。

由于30天的旅程超时，当旅程重新进入不被允许时，我们无法确保重新进入的阻塞将工作超过30天。 事实上，当我们删除所有关于在他们进入旅程30天后进入旅程的人员的信息时，我们无法知道之前输入的人员，超过30天前。

## 时区和用户档案时区 {#timezone}

时区在旅程级别定义。

您可以输入固定时区或使用Adobe Experience Platform用户档案定义旅程时区。

有关时区管理的详细信息，请参阅 [](../building-journeys/timezone-management.md)。
