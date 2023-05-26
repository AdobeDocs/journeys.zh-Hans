---
product: adobe campaign
title: 关于操作活动
description: 了解操作活动
feature: Journeys
role: User
level: Intermediate
exl-id: 5436602f-af7a-41db-8b10-d3d28a6d0cd0
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 28%

---

# 关于操作活动 {#concept_hbj_hrt_52b}

从屏幕左侧的面板，如下所示 **[!UICONTROL Events]** 和 **[!UICONTROL Orchestration]**，您将找到 **[!UICONTROL Actions]** 类别。

![](../assets/journey58.png)

这些活动代表各种的可用通信渠道。您可以将它们组合在一起，创建跨渠道方案。

如果您有Adobe Campaign Standard，则可以使用以下现成的操作活动： **[!UICONTROL Email]**， **[!UICONTROL Push]** 和 **[!UICONTROL SMS]**. 请参见[此页面](../building-journeys/using-adobe-campaign-actions.md)。

如果您已配置自定义操作，则它们也会显示在此处(请参阅 [此页面](../building-journeys/using-custom-actions.md))。

将操作活动拖放到画布中时，您可以定义 **[!UICONTROL Label]**. 这允许您向操作名称添加后缀，该后缀将显示在画布中的活动下方。 如果您在历程中多次使用相同的操作，并且希望更轻松地识别它们，则此功能非常有用。 报告也将更易于阅读。 您还可以添加可选 **[!UICONTROL Description]**.

![](../assets/journey59bis.png)

当操作或条件中发生错误时，个人历程将停止。使其继续的唯一方法是选中 **[!UICONTROL Add an alternative path in case of a timeout or an error]** 框。请参阅[此章节](../building-journeys/using-the-journey-designer.md#paths)。
