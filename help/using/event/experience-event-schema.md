---
product: adobe campaign
solution: Journey Orchestration
title: '关于ExperienceEvent模式，用于Journey Orchestration事件 '
description: '了解ExperienceEvent模式用于Journey Orchestration事件 '
feature: 历程
role: 业务从业者
level: 中间
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '328'
ht-degree: 0%

---



# 关于[!DNL Journey Orchestration]事件的ExperienceEvent模式

[!DNL Journey Orchestration] 事件是通过流摄取发送到Adobe Experience Platform的XDM体验事件。

因此，为[!DNL Journey Orchestration]设置事件的一个重要先决条件是您熟悉Adobe Experience Platform的体验数据模型（或XDM）、如何构建XDM体验事件模式，以及如何将XDM格式化的数据流化到Adobe Experience Platform。

## [!DNL Journey Orchestration]模式要求

为[!DNL Journey Orchestration]设置事件的第一步是确保您定义了一个XDM模式来表示事件，并创建了一个数据集来记录Adobe Experience Platform上事件的实例。 拥有事件的事件集并非绝对必要，但将事件发送到特定数据集将允许您维护用户的历史记录以供将来参考和分析，因此始终是个不错的主意。 如果您还没有适合您的事件的模式和数据集，则可以在Adobe Experience Platform Web界面中执行这两个任务。

![](../assets/schema1.png)

将用于[!DNL Journey Orchestration]事件的任何XDM模式都应满足以下要求：

* 模式必须是XDM ExperienceEvent类。

   ![](../assets/schema2.png)

* 对于系统生成的事件,模式必须包含Orchestration eventID mixin。 [!DNL Journey Orchestration] 使用此字段来标识在旅程中使用的事件。

   ![](../assets/schema3.png)

* 声明标识字段以标识事件的主体。 如果未指定任何标识，则可以使用标识映射。 不建议这样做。

   ![](../assets/schema4.png)

* 如果您希望此数据稍后在历程中可供查找，请标记模式和数据集以进行用户档案。

   ![](../assets/schema5.png)

   ![](../assets/schema6.png)

* 您可以随意地包含数据字段，以捕获您希望随事件一起包含的任何其他上下文数据，例如有关用户、从中生成事件的设备的信息、位置，或与事件相关的任何其他有意义的环境。

   ![](../assets/schema7.png)

   ![](../assets/schema8.png)