---
title: 关于操作
description: 了解如何配置操作
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
source-git-commit: 87910a9f3dbf2c34776a8d2ab1f00426e8b0704c

---


# 关于操作 {#about_actions}

>[!CONTEXTUALHELP]
>id=&quot;jo_actions&quot;
>title=&quot;About actions&quot;
>abstract=&quot;这是您定义与将发送消息的系统的连接的位置。 此处定义的操作随后将显示在旅程左侧的“操作”类别中。 &quot;

行动是一种连接方式，通过它可向客户提供个性化的实时体验，如推送通知、电子邮件、短信或您在业务中使用的任何其他数字参与方式。

自定义操作允许您将第三方系统的连接配置为发送消息或API调用。 可以使用任何提供商提供的任何服务配置操作，这些服务可以通过REST API调用，并且JSON格式的有效负荷。

这些操作位于旅程左侧的类别中(请参 **[!UICONTROL Action]** 阅 [](../building-journeys/about-action-activities.md) )。

>[!NOTE]
>
>自定义操作的配置始终由技术用户 **执行**。

在“操作 **”列表中**，您可以按c创建新旅程、操作、数据源或事件。 有关旅程编排中的快捷键的更多信息，请参阅 [](../about/user-interface.md#section_ksq_zr1_ffb)。

要查看操作列表或配置新操作，请单击顶 **[!UICONTROL Actions]** 部菜单中的。 此时将显示操作列表。 有关 [](../about/user-interface.md) 该界面的详细信息，请参阅。

![](../assets/custom1.png)

如果您有Adobe Campaign Standard，则需要配置开箱即用的操作，以使用Adobe Campaign Standard的“交易消息传递”功能发送电子邮件、推送通知和SMS。 请参阅[](../action/working-with-adobe-campaign.md)。

如果您使用第三方系统发送消息，如Epsilon、Facebook、Adobe.io、Firebase等，则需要添加和配置自定义操作。 请参阅[](../action/about-custom-action-configuration.md)。

有关如何为旅程安排配置动作以及如何在旅程中使用动作的更多信息，请观看此视 [频教程](https://docs.adobe.com/content/help/en/platform-learn/tutorials/journey-orchestration/configure-actions.html)。
