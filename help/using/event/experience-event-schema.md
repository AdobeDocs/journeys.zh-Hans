---
product: adobe campaign
solution: Journey Orchestration
title: '关于针对Journey Orchestration模式的ExperienceEvent事件 '
description: '了解面向Journey Orchestration模式的ExperienceEvent事件 '
translation-type: tm+mt
source-git-commit: 81bb0b5da38217f9290214901c64e90d7ec2ba0e
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---



# 关于[!DNL Journey Orchestration]模式的ExperienceEvent事件

[!DNL Journey Orchestration] 事件是通过流摄取发送到Adobe Experience Platform的XDM体验事件。

因此，为[!DNL Journey Orchestration]设置事件的一个重要先决条件是您熟悉Adobe Experience Platform的体验数据模型（或XDM），以及如何构建XDM体验事件模式，以及如何将XDM格式化的数据流式传输到Adobe Experience Platform。

## [!DNL Journey Orchestration]模式的事件要求

为[!DNL Journey Orchestration]设置事件的第一步是确保您定义了一个XDM模式来表示事件，并创建了一个数据集来记录Adobe Experience Platform事件的实例。 为事件建立数据集并非绝对必要，但将事件发送到特定数据集将允许您保留用户的事件历史记录，以供将来参考和分析，因此这始终是个好主意。 如果您还没有适合您的模式的事件和数据集，可以在Adobe Experience PlatformWeb界面中执行这两个任务。

![](../assets/schema1.png)

将用于[!DNL Journey Orchestration]模式的任何XDM事件均应满足以下要求：

* 模式必须是XDM ExperienceEvent类。

   ![](../assets/schema2.png)

* 对于系统生成的事件,模式必须包括Orchestration eventID mixin。 [!DNL Journey Orchestration] 使用此字段识别旅程中使用的事件。

   ![](../assets/schema3.png)

* 声明标识字段以标识事件的主体。 如果未指定身份，则可以使用身份映射。 不建议这样做。

   ![](../assets/schema4.png)

* 如果您希望此数据稍后在旅程中可供查阅，请标记模式和数据集以进行用户档案。

   ![](../assets/schema5.png)

   ![](../assets/schema6.png)

* 您可以随意包含数据字段以捕获要包含在事件中的任何其他上下文数据，如有关用户、从中生成事件的设备、位置或与事件相关的任何其他有意义的情况。

   ![](../assets/schema7.png)

   ![](../assets/schema8.png)