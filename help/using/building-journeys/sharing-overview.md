---
product: adobe campaign
solution: Journey Orchestration
title: 旅程步骤共享概述
description: 旅程步骤共享概述
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '420'
ht-degree: 7%

---


# 旅程步骤共享概述{#sharing-overview}

[!DNL Journey Orchestration] 自动将旅程性能数据发送到Adobe Experience Platform，以便与其他数据结合，以便分析。

>[!NOTE]
>
>默认情况下，该功能不会在所有新部署的实例上激活。 激活应要求。

例如，您已设置发送多个电子邮件的旅程。 此功能允许您将数据与 [!DNL Journey Orchestration] 下游事件数据相结合，如发生了多少转换、网站上发生了多少参与，或在商店中发生了多少交易。 旅程信息可以与Adobe Experience Platform的数据相结合，无论是从其他数字资产还是离线资产，都可以提供更全面的性能视图。

[!DNL Journey Orchestration] 自动为个人在旅程中执行的每个步骤创建必要的模式和流到Adobe Experience Platform的数据集中。 步骤事件对应于旅程中从一个节点移动到另一个节点的个人。 例如，在具有事件、条件和操作的旅程中，将向Adobe Experience Platform发送三步事件。

传递的XDM字段的列表是全面的。 有些代码包含系统生成的代码，而另一些代码则具有易读的易用名称。 示例包括旅程活动的标签或步骤状态：操作超时或以错误结束的次数。

>[!CAUTION]
>
>无法为实时用户档案服务打开数据集。 请确保关闭 **[!UICONTROL Profile]** 了切换。

旅程以流方式在数据发生时发送数据。 您可以使用查询服务查询此数据。 您可以连接到Customer Journey Analytics或其他BI工具，以视图与这些步骤相关的数据。

将创建以下模式:

* 旅程步骤用户档案事件 [!DNL Journey Orchestration] 模式-体验旅程中所采取步骤的事件以及用于映射到单个旅程参与者的身份映射。
* 旅程步骤事件 [!DNL Journey Orchestration] 模式-绑定到旅程元数据的旅程步骤事件。
* 旅程模式，包含旅程字段- [!DNL Journey Orchestration] 用于描述旅程的旅程元数据。

![](../assets/sharing1.png)

![](../assets/sharing2.png)

传递以下数据集：

* 旅程步骤用户档案事件模式 [!DNL Journey Orchestration]
* 旅程步骤事件
* 旅程

![](../assets/sharing3.png)

传递到Adobe Experience Platform的XDM字段的列表详情如下：

* [journeySteps 事件常用字段](../building-journeys/sharing-common-fields.md)
* [journeyStep 事件操作执行字段](../building-journeys/sharing-execution-fields.md)
* [journeyStep 事件数据提取字段](../building-journeys/sharing-fetch-fields.md)
* [journeyStep 事件身份字段](../building-journeys/sharing-identity-fields.md)
* [旅程场](../building-journeys/sharing-journey-fields.md)

有关将步骤事件报告到Adobe Experience Platform的更多信息，请观看此 [教程视频](https://docs.adobe.com/content/help/en/journey-orchestration-learn/tutorials/reporting-step-events-to-adobe-experience-platform.html)。
