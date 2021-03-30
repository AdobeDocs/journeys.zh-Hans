---
product: adobe campaign
solution: Journey Orchestration
title: 更改属性
description: 了解如何更改属性
feature: 历程
role: 商业从业者
level: 中间
translation-type: tm+mt
source-git-commit: a8bfd4fd829ff8fadc68de87dc0b9de085a962e3
workflow-type: tm+mt
source-wordcount: '495'
ht-degree: 1%

---



# 更改属性 {#concept_prq_wqt_52b}

单击右上角的铅笔图标以访问旅程的属性。

您可以更改旅程名称、添加描述、允许重新进入、选择开始和结束日期，并定义&#x200B;**[!UICONTROL Timeout and error]**&#x200B;持续时间（如果您是管理员）。

![](../assets/journey32.png)

## 入口{#entrance}

默认情况下，新旅程允许重新进入。 您可以取消选中“一次性”旅程选项，例如，当某人进入商店时，您要优惠一次性馈赠。 在这种情况下，您不希望客户能够重新进入旅程并再次接收优惠。

当旅程“结束”时，其状态为&#x200B;**[!UICONTROL Closed (no entrance)]**。 这一旅程将不再让新人进入旅程。 已经在旅程中的人将正常完成旅程。

在默认全局超时30天后，旅程将切换到&#x200B;**已完成**&#x200B;状态。 请参阅此[部分](#global_timeout)。

## 旅程活动{#timeout_and_error}中的超时和错误

在编辑操作或条件活动时，您可以在出现错误或超时时定义替代路径。 如果询问第三方系统的活动的处理超过了在旅程的属性（**[!UICONTROL Timeout and  error]**&#x200B;字段）中定义的超时持续时间，则将选择第二路径以执行潜在的回退操作。

授权值介于1到30秒之间。

如果您的旅程是时间敏感型的(例如：对人的实时位置做出响应)，因为您不能将您的动作延迟超过几秒钟。 **[!UICONTROL Timeout and error]**&#x200B;如果您的旅程对时间不太敏感，则可以使用一个较长的值为调用的系统提供更多时间以发送有效响应。

[!DNL Journey Orchestration] 还使用全局超时。请参见[下一节](#global_timeout)。

## 全局旅程超时{#global_timeout}

除了在旅程活动中使用的[timeout](#timeout_and_error)之外，还存在全局旅程超时，该超时不会显示在接口中，并且无法更改。 此超时将在个人进入后30天内停止其在旅程中的进度。 这意味着个人的旅程不能持续超过30天。 在30天超时期后，将删除个人的数据。 在超时期结束时仍在旅程中流动的个人将被停止，并将其作为报告中的错误予以考虑。

>[!NOTE]
>
>[!DNL Journey Orchestration] 不会直接对隐私选择退出、访问或删除请求做出响应。但是，全局超时可确保个人在任何旅程中停留30天以上。

由于30天的旅程超时，当不允许重新进入旅程时，我们无法确保重新进入的阻塞超过30天。 事实上，由于我们删除了有关在进入旅程30天后进入旅程的人员的所有信息，因此我们无法知道之前输入的人员，超过30天前。

## 时区和用户档案时区{#timezone}

时区在旅程级别定义。

您可以输入固定时区或使用Adobe Experience Platform用户档案定义旅程时区。

有关时区管理的详细信息，请参阅[此页](../building-journeys/timezone-management.md)。
