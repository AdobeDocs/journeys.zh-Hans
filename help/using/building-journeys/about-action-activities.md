---
title: 关于操作活动
description: 了解行动活动
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
source-git-commit: a65a5db5b35291cbc2635f9ae67fd8c8c5284575
workflow-type: tm+mt
source-wordcount: '166'
ht-degree: 4%

---


# 关于操作活动 {#concept_hbj_hrt_52b}

从调色板中，在屏幕的左侧，在下 **[!UICONTROL Events]** 面 **[!UICONTROL Orchestration]**&#x200B;和下面找到 **[!UICONTROL Actions]** 类别。

![](../assets/journey58.png)

这些活动代表不同的可用通信渠道。 您可以将它们组合在一起，以创建跨渠道场景。

如果您有Adobe Campaign Standard，可以使用以下现成操作活动: **[!UICONTROL Email]**, **[!UICONTROL Push]** 和 **[!UICONTROL SMS]**。 请参见 [](../building-journeys/using-adobe-campaign-actions.md)。

如果已配置自定义操作，则它们也将显示在此处(请参 [](../building-journeys/using-custom-actions.md)阅)。

在画布中放置操作活动时，可以定义操作 **[!UICONTROL Label]**。 这允许您向将在画布中的活动下显示的操作名称添加后缀。 如果您在旅程中多次使用同一操作，并希望更轻松地识别它们，则此功能非常有用。 报告也更易于阅读。 您还可以添加可选项 **[!UICONTROL Description]**。

![](../assets/journey59bis.png)

当操作或条件中发生错误时，单个旅程将停止。 使其继续的唯一方法是选中该框 **[!UICONTROL Add an alternative path in case of a timeout or an error]**。 请参见 [](../building-journeys/using-the-journey-designer.md#paths)。
