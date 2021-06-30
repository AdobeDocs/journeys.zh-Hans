---
product: adobe campaign
title: 反应事件
description: 了解反应事件
feature: 历程
role: Business Practitioner
level: Intermediate
exl-id: 2f2a2905-1521-48d9-b593-9b31238282a5
source-git-commit: fb6bdb60ac70a94a62956a306bedee9cb607e2a2
workflow-type: tm+mt
source-wordcount: '411'
ht-degree: 2%

---

# 反应事件 {#section_dhx_gss_dgb}

在面板中可用的不同事件活动中，您会找到内置的&#x200B;**[!UICONTROL Reactions]**&#x200B;事件。 此活动允许您对与通过电子邮件、短信或同一历程中的推送活动发送的消息相关的跟踪数据做出反应。 此信息来自Adobe Campaign Standard中的事务型消息传递。 我们会在与Adobe Experience Platform共享这些信息时实时捕获这些信息。 对于推送通知，您可以对点击、发送或失败的消息做出反应。 对于短信消息，您可以对已发送或失败的消息做出响应。 对于电子邮件，您可以对点击、发送、打开或失败的消息做出响应。

您还可以使用此机制在消息未受到任何反应时执行操作。 为此，请创建与反应活动平行的第二个路径，并添加等待活动。 如果在等待活动中定义的时间段内没有反应，则将选择第二个路径。 例如，您可以选择发送跟进消息。

请注意，只有在之前有电子邮件、推送或短信活动时，您才能在画布中使用反应活动。

请参阅[关于操作活动](../building-journeys/about-action-activities.md)。

![](../assets/journey45.png)

以下是配置反应事件的不同步骤：

1. 向反应中添加&#x200B;**[!UICONTROL Label]**。 此步骤是可选的。
1. 从下拉列表中，选择要对其做出响应的操作活动。 您可以选择位于路径前面步骤中的任何操作活动。
1. 根据您选择的操作（电子邮件、短信或推送通知），选择您要对什么做出反应。
1. 您可以定义事件超时（在40秒到30天之间）和超时路径。 这将为未在定义的持续时间内做出反应的个人创建第二个路径。 测试使用反应事件的历程时，测试模式&#x200B;**[!UICONTROL Wait time]**&#x200B;默认值和最小值为40秒。 请参阅[此小节](../building-journeys/testing-the-journey.md)。

>[!NOTE]
>
>反应事件与Adobe Campaign Standard配合使用，无论是部署在AWS还是Azure服务器上。
>
>反应事件无法跟踪在其他历程中发生的电子邮件、短信或推送操作。
>
>反应事件跟踪“tracked”类型链接的点击量（请参阅此[page](https://experienceleague.adobe.com/docs/campaign-standard/using/designing-content/links.html#about-tracked-urls)）。 未考虑退订和镜像页面链接。

>[!IMPORTANT]
>
>电子邮件客户端（如Gmail）允许图像阻止。 使用电子邮件中包含的0像素图像跟踪打开的电子邮件。 如果图像被阻止，则不会考虑打开的电子邮件。
