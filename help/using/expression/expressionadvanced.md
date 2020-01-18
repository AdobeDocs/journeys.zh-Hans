---
title: 关于高级表达式编辑器
description: 了解如何构建高级表达式
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
source-git-commit: 017d502e21605b3e0b8c61e5fea0b4f6a65d4470

---


# 关于高级表达式编辑器 {#concept_uyj_trt_52b}

高级表达式编辑器允许您在界面的各种屏幕中构建高级表达式，例如，在定义数据源条件时。
每次您需要定义需要特定数据操作的操作参数时，也可以使用它。 您可以利用来自事件的数据或从数据源检索的其他信息。 在旅程中，显示的事件字段列表是上下文的，并会因在旅程中添加的事件而异。

高级表达式编辑器提供了一组内置函数和运算符，使您能够处理值并定义一个专门满足您需求的表达式。 高级表达式编辑器还允许您定义外部数据源参数的值、处理映射字段和集合，如体验事件。

![](../assets/journey65.png)

_高级表达式编辑器界面_

高级表达式编辑器可用于：

* 为数据源 [和活动信息创建](../building-journeys/condition-activity.md#about_condition) 高级条件
* 在日期条 [件中定义自定义时区](../building-journeys/timezone-management.md) ，固定日期等待活动，自定义等待活动
* 定义自定 [义等待活动](../building-journeys/wait-activity.md#custom)
* 定义操作参数映射

如果可能，您可以使用／按钮在两种模 **[!UICONTROL Advanced mode]**式之间**[!UICONTROL Simple mode]** 切换。 此处介绍了简单 [模式](../building-journeys/condition-activity.md#about_condition)。

>[!NOTE]
>
>条件可以在简单或高级表达式编辑器中定义。 它们始终返回布尔类型。
>
>操作参数可以通过选择字段或通过高级表达式编辑器来定义。 他们会根据自己的表达式返回特定的数据类型。

## 访问高级表达式编辑器 {#section_fdz_4nj_cjb}

您可以通过以下不同方式访问高级表达式编辑器：

* 在创建数据源条件时，可以通过单击访问高级编辑器 **[!UICONTROL Advanced mode]**。

   ![](../assets/journeyuc2_33.png)

* 创建自定义时区或自定义计时器时，将直接显示高级编辑器。
* 映射操作参数时，单击 **[!UICONTROL Advanced mode]**。

## 了解界面{#section_otq_tnj_cjb}

此屏幕允许您手动编写表达式。

![](../assets/journey70.png)

屏幕的左侧显示了可用字段和函数：

* **[!UICONTROL Events]**:选择从入站事件接收的字段之一。 显示的事件字段列表是上下文的，并根据旅程中添加的事件而有所不同。
* **[!UICONTROL Data Sources]**:从数据源的字段组中可用的字段列表中选择。
* **[!UICONTROL Functions]**:从允许执行复杂过滤的内置函数列表中选择。 功能按类别进行组织。

![](../assets/journey65.png)

自动完成机制显示上下文建议。

![](../assets/journey68.png)

语法验证机制检查代码的完整性。 错误显示在编辑器的顶部。

![](../assets/journey69.png)

**使用高级表达式编辑器构建条件时需要参数**

如果您从外部数据源中选择了需要调用参数的字段(请参阅 [](../datasource/external-data-sources.md))。 例如，在与天气相关的数据源中，常用参数将为“city”。 因此，您必须选择要获取此city参数的位置。 还可以将函数应用于参数以执行格式更改或连接。

![](../assets/journeyuc2_19.png)

对于更复杂的用例，如果要在主表达式中包含数据源的参数，可以使用“params”关键字定义其值。 请参 [阅此页](../expression/field-references.md)。
