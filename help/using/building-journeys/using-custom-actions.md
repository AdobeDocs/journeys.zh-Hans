---
product: adobe campaign
solution: Journey Orchestration
title: 使用自定义操作
description: 了解操作活动
feature: 历程
role: 业务从业者
level: 中间
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '131'
ht-degree: 4%

---


# 使用自定义操作 {#section_f2c_hbg_nhb}

如果您使用自定义操作，您将在只读模式下看到在操作配置屏幕中定义的&#x200B;**[!UICONTROL URL Configuration]**&#x200B;和&#x200B;**[!UICONTROL Authentication]**&#x200B;参数（请参阅[此页](../action/about-custom-action-configuration.md)）。

>[!NOTE]
>
>无法在自定义操作参数中传递集合。 如果自定义操作需要集合，则它将不起作用。 另请注意，这些参数具有预期的格式(示例：字符串、小数等)。 必须注意遵守这些预期格式。

在&#x200B;**[!UICONTROL Action parameters]**&#x200B;部分，您将看到定义为&#x200B;_&quot;Variable&quot;_&#x200B;的消息参数。 对于这些参数，您可以定义获取此信息的位置(例如：事件、数据源)、手动传递值或使用高级表达式编辑器处理高级用例。 高级用例可以是数据操作和其他函数使用。 请参阅[此页](../expression/expressionadvanced.md)
