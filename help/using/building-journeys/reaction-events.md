---
product: adobe campaign
title: 反应事件
description: 了解反应事件
feature: Journeys
role: User
level: Intermediate
exl-id: 2f2a2905-1521-48d9-b593-9b31238282a5
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '451'
ht-degree: 2%

---

# 反应事件 {#section_dhx_gss_dgb}


>[!CAUTION]
>
>**正在查找Adobe Journey Optimizer**？ 单击[此处](https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer/using/ajo-home){target="_blank"}获取Journey Optimizer文档。
>
>
>_本文档参考已被Journey Optimizer替换的旧版Journey Orchestration资料。 如果您对访问Journey Orchestration或Journey Optimizer有任何疑问，请联系您的帐户团队。_



在面板中可用的不同事件活动中，您会找到内置的&#x200B;**[!UICONTROL Reactions]**&#x200B;事件。 利用此活动，可响应与同一历程中通过电子邮件、短信或推送活动发送的消息相关的跟踪数据。 此信息来自Adobe Campaign Standard中的事务性消息传递。 我们会在与Adobe Experience Platform共享该信息的那一刻实时捕获该信息。 对于推送通知，您可以对点击、发送或失败的消息做出反应。 对于短信消息，您可以对已发送或失败的消息做出反应。 对于电子邮件，您可以对点击、发送、打开或失败的消息做出反应。

也可以使用此机制在消息没有反应时执行操作。 为此，请创建与反应活动平行的第二个路径，并添加等待活动。 如果在等待活动中定义的时段内没有反应，则将选择第二条路径。 例如，您可以选择发送跟进消息。

请注意，仅当以前存在电子邮件、推送或短信活动时，才能在画布中使用反应活动。

请参阅[关于操作活动](../building-journeys/about-action-activities.md)。

![](../assets/journey45.png)

以下是配置反应事件的不同步骤：

1. 将&#x200B;**[!UICONTROL Label]**&#x200B;添加到反应。 此步骤是可选的。
1. 从下拉列表中，选择要做出反应的操作活动。 您可以选择位于路径前面步骤中的任何操作活动。
1. 根据您选择的操作（电子邮件、短信或推送通知），选择要回应的内容。
1. 您可以定义事件超时（40秒到30天之间）和超时路径。 这将为未在定义的持续时间内做出反应的个人创建第二个路径。 测试使用反应事件的历程时，测试模式&#x200B;**[!UICONTROL Wait time]**&#x200B;的默认值和最小值为40秒。 请参阅[此小节](../building-journeys/testing-the-journey.md)。

>[!NOTE]
>
>无论反应事件部署在Adobe Campaign Standard上还是AWS服务器上，均可与它配合使用。
>
>反应事件无法跟踪在其他历程中发生的电子邮件、短信或推送操作。
>
>反应事件跟踪“已跟踪”类型链接的点击次数（请参阅此[页面](https://experienceleague.adobe.com/docs/campaign-standard/using/designing-content/links.html?lang=zh-Hans#about-tracked-urls)）。 未考虑退订和镜像页面链接。

>[!IMPORTANT]
>
>Gmail等电子邮件客户端允许阻止图像。 使用电子邮件中包含的0像素图像跟踪电子邮件打开次数。 如果图像被阻止，则不会考虑电子邮件打开次数。
