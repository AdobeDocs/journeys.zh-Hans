---
product: adobe campaign
solution: Journey Orchestration
title: 关于高级表达式编辑器
description: 了解如何构建高级表达式
translation-type: tm+mt
source-git-commit: c41b49e2208727f5e3a562b838c4b052c70e8412
workflow-type: tm+mt
source-wordcount: '541'
ht-degree: 94%

---


# 关于高级表达式编辑器 {#concept_uyj_trt_52b}

高级表达式编辑器允许您在界面的各种屏幕中构建高级表达式，例如，在定义数据源条件时。
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

## 了解界面{#section_otq_tnj_cjb}

此屏幕允许您手动编写表达式。

![](../assets/journey70.png)

屏幕左侧显示了可用字段和函数：

* **[!UICONTROL Events]**：选择从入站事件接收的字段之一。显示的事件字段列表是符合上下文的，并根据历程中添加的事件而有所不同。[阅读更多](../event/about-events.md)
* **[!UICONTROL Segments]**:如果您已经删除 **[!UICONTROL Segment qualification]** 了事件，请选择要在表达式中使用的区段。[阅读更多](../segment/using-a-segment.md)
* **[!UICONTROL Data Sources]**：从数据源的字段组提供的字段列表中进行选择。[阅读更多](../datasource/about-data-sources.md)
* **[!UICONTROL Journey properties]**:此部分重新分组与给定用户档案的旅程相关的技术字段。[阅读更多](../expression/journey-properties.md)
* **[!UICONTROL Functions]**：从允许执行复杂筛选的内置函数列表中进行选择。函数按类别组织。[阅读更多](../expression/functions.md)

![](../assets/journey65.png)

自动完成机制会显示上下文建议。

![](../assets/journey68.png)

语法验证机制检查代码的完整性。错误显示在编辑器顶部。

![](../assets/journey69.png)

**使用高级表达式编辑器构建条件时需要参数**

如果您从外部数据源选择字段，则需要调用参数（请参阅[此页面](../datasource/external-data-sources.md)）。例如，在与天气相关的数据源中，常用的参数将为“city”。因此，必须选择要获取此城市参数的位置。还可以将函数应用于参数以执行格式更改或连接。

![](../assets/journeyuc2_19.png)

对于更复杂的用例，如果要在主表达式中包含数据源的参数，可以使用“params”关键字定义其值。请参阅[此页](../expression/field-references.md)。
