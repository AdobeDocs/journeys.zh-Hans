---
product: adobe campaign
title: 关于高级表达式编辑器
description: 了解如何构建高级表达式
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: f6f0004d-8a33-4671-9c16-e56edfe2a45e
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '595'
ht-degree: 77%

---

# 关于高级表达式编辑器 {#concept_uyj_trt_52b}


>[!CAUTION]
>
>**正在查找Adobe Journey Optimizer**？ 单击[此处](https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer/using/ajo-home){target="_blank"}获取Journey Optimizer文档。
>
>
>_本文档参考已被Journey Optimizer替换的旧版Journey Orchestration资料。 如果您对访问Journey Orchestration或Journey Optimizer有任何疑问，请联系您的帐户团队。_


使用高级表达式编辑器可以在界面的各个屏幕中生成高级表达式。例如，您可以在配置和使用历程以及定义数据源条件时构建表达式。
它还可在您每次需要定义需要特定数据操作的操作参数时使用。您可以利用来自事件的数据或从数据源检索的其他信息。在历程中，显示的事件字段列表是符合上下文的，并根据历程中添加的事件而有所不同。

高级表达式编辑器提供一组内置函数和运算符，让您处理值并定义一个专门满足您需求的表达式。高级表达式编辑器还允许您定义外部数据源参数的值、处理映射字段和集合，如体验事件。

![](../assets/journey65.png)

_高级表达式编辑器界面_

高级表达式编辑器可用于：

* 为数据源和事件信息创建[高级条件](../building-journeys/condition-activity.md#about_condition)
* 定义自定义[等待活动](../building-journeys/wait-activity.md#custom)
* 定义操作参数映射

如果可能，您可以使用&#x200B;**[!UICONTROL Advanced mode]**/**[!UICONTROL Simple mode]**&#x200B;按钮在两种模式之间切换。[此处](../building-journeys/condition-activity.md#about_condition)介绍了简单模式。

>[!NOTE]
>
>条件可以在简单或高级表达式编辑器中定义。它们始终返回布尔类型。
>
>操作参数可以通过选择字段或通过高级表达式编辑器来定义。他们根据表达式返回特定数据类型。

## 访问高级表达式编辑器 {#section_fdz_4nj_cjb}

您可以通过不同方式访问高级表达式编辑器：

* 在创建数据源条件时，可以通过单击 **[!UICONTROL Advanced mode]** 访问高级编辑器 。

  ![](../assets/journeyuc2_33.png)

* 创建自定义计时器时，系统将直接显示高级编辑器。
* 映射操作参数时，单击 **[!UICONTROL Advanced mode]**。

## 探索界面{#section_otq_tnj_cjb}

此屏幕允许您手动编写表达式。

![](../assets/journey70.png)

屏幕左侧显示了可用字段和函数：

* **[!UICONTROL Events]**：选择从入站事件接收的字段之一。显示的事件字段列表是符合上下文的，并根据历程中添加的事件而有所不同。 [了解详情](../event/about-events.md)
* **[!UICONTROL Segments]**：如果您已删除&#x200B;**[!UICONTROL Segment qualification]**&#x200B;事件，请选择要在表达式中使用的区段。 [了解详情](../segment/using-a-segment.md)
* **[!UICONTROL Data Sources]**：从数据源的字段组提供的字段列表中进行选择。 [了解详情](../datasource/about-data-sources.md)
* **[!UICONTROL Journey properties]**：此部分重组与给定用户档案的历程相关的技术字段。 [了解详情](../expression/journey-properties.md)
* **[!UICONTROL Functions]**：从允许执行复杂筛选的内置函数列表中进行选择。函数按类别组织。 [了解详情](../expression/functions.md)

![](../assets/journey65.png)

自动完成机制会显示上下文建议。

![](../assets/journey68.png)

语法验证机制检查代码的完整性。错误显示在编辑器顶部。

![](../assets/journey69.png)

**使用高级表达式编辑器构建条件时需要参数**

如果您从外部数据源选择字段，则需要调用参数（请参阅[此页面](../datasource/external-data-sources.md)）。例如，在与天气相关的数据源中，常用的参数将为“city”。因此，必须选择要获取此城市参数的位置。还可以将函数应用于参数以执行格式更改或连接。

![](../assets/journeyuc2_19.png)

对于更复杂的用例，如果要在主表达式中包含数据源的参数，可以使用“params”关键字定义其值。请参阅[此页](../expression/field-references.md)。
