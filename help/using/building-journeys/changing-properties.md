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
source-git-commit: 76369cd714c513e0038278ad058bf1ba43fcd240

---



# 更改属性 {#concept_prq_wqt_52b}

单击右上方的铅笔图标以访问旅程的属性。

如果您是管理员，则可以更改旅程名称、添加描述、允许重新进入、选择开始日期和结束日期并定 **[!UICONTROL Timeout and error]** 义持续时间。

![](../assets/journey32.png)

## 入口{#entrance}

默认情况下，新旅程允许重新进入。 您可以取消选中“一拍”旅程选项，例如，当某人进入商店时，您要提供一次性礼品。 在这种情况下，您不希望客户能够重新进入旅程并再次收到优惠。

当旅程“结束”时，它将具有状态 **[!UICONTROL Finished]**。 旅程将不再让新人进入旅程。 已经在旅途中的人将正常地完成旅程。

## 旅程活动中的超时和错误 {#timeout_and_error}

在编辑操作或条件活动时，您可以在出现错误或超时的情况下定义替代路径。 如果询问第三方系统的活动的处理超过在旅程的属性（字段）中定义的超时持续时间，则选择第二路径以执行潜在的回退操作。**[!UICONTROL Timeout and  error]**

授权值介于1到30秒之间。

如果您的旅程是时间敏感的， **[!UICONTROL Timeout and error]** 我们建议您定义一个非常短的值(例如：对人物的实时位置做出响应)，因为您不能将您的动作延迟超过几秒钟。 如果您的旅程对时间不太敏感，则可以使用较长的值为调用的系统提供更多时间以发送有效的响应。

旅程安排还使用全局超时。 请参阅下 [一节](#global_timeout)。

## 全局旅程超时 {#global_timeout}

除了在旅程 [活动中使用的超时](#timeout_and_error) ，还存在一个全局旅程超时，该超时不会显示在界面中，并且无法更改。 此超时将在进入后30天内停止个人在旅程中的进度。 这意味着个人的旅程不能超过30天。 在30天超时期后，将删除个人的数据。 在超时期间结束时仍在旅程中流动的个人将被停止，并将其作为报告错误予以考虑。

>[!NOTE]
>
>旅程安排不会直接对隐私选择退出、访问或删除请求做出反应。 但是，全局超时可确保个人在任何旅程中停留不超过30天。

由于30天的行程超时，当行程重新进入不允许时，无法确保重新进入的阻塞超过30天。 事实上，由于我们删除了有关在他们进入旅程30天后进入旅程的人员的所有信息，因此我们无法了解之前在30天前进入的人员。

## 时区和配置文件时区 {#timezone}

时区在旅程级别定义。

您可以输入固定时区或使用Experience Platform配置文件定义旅程时区。

有关时区管理的详细信息，请参阅 [](../building-journeys/timezone-management.md)。
