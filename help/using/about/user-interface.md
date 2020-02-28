---
title: 用户界面
description: 了解有关用户界面的更多信息
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: 891216a489b79fe4b168ecdb6120f5d9f3e107d0

---


# 用户界面{#concept_rcq_lqt_52b}


>[!CONTEXTUALHELP]
>id=&quot;jo_home&quot;
>title=&quot;关于旅程列表&quot;
>abstract=&quot;旅程列表允许您同时查看所有旅程，查看其状态并执行基本操作。 您可以复制、停止或删除您的旅程。 根据旅程，某些操作可能不可用。 例如，您无法停止或删除已完成的旅程。 您还可以使用搜索栏搜索旅程。”
>additional-url=&quot;https://images-tv.adobe.com/mpcv3/38af62cb-9390-4bc0-a576-d336849adb97_1574809570.1920x1080at3000_h264.mp4&quot; text=&quot;观看演示视频&quot;

>[!NOTE]
>
>为了充分利用旅程编排，我们建议将Chrome用作您的Internet浏览器。
>
>此文档经常更新以反映产品中最近的更改。 但是，某些屏幕截图可能与产品的界面略有不同。

## 了解界面{#section_jsq_zr1_ffb}

要访问Journey Orcheration的界面，请单击右 **[!UICONTROL App Selector]** 上角的图标。 然后， **[!UICONTROL Journey Orchestration]**&#x200B;单击右侧“Experience Platform”下方的。

![](../assets/journey1.png)

您还可以从Experience cloud主页中的部分访问旅程安排 **[!UICONTROL Quick access]** 。

![](../assets/journey1bis.png)

顶级菜单允许您浏览旅程编排的不同功能： **[!UICONTROL Home]**（旅程）**[!UICONTROL Data Sources]**, **[!UICONTROL Events]**, **[!UICONTROL Actions]**.

![](../assets/journey2.png)

单击 ![](../assets/icon-context.png) 屏幕右上角的图标以显示上下文帮助。 它可跨不同的旅程安排列表屏幕（旅程、事件、操作和数据源）使用。 这允许您查看当前功能的快速说明并访问相关文章和视频。

![](../assets/journey2bis.png)

## 搜索和筛选{#section_lgm_hpz_pgb}

在、 **[!UICONTROL Home]****[!UICONTROL Data Sources]****[!UICONTROL Events]** 和列表 **[!UICONTROL Actions]** 中，搜索栏允许您搜索项目。

单 **[!UICONTROL Filters]** 击列表左上角的过滤器图标可访问。 过滤器菜单允许您根据不同的条件过滤显示的元素。 您可以选择仅显示特定类型或状态的元素、您创建的元素或最近30天内修改的元素。

在和列 **[!UICONTROL Data Sources]**&#x200B;表中， **[!UICONTROL Events]** 使用“创 **[!UICONTROL Actions]** 建”过滤器 **** ，按创建日期和用户进行过滤。 例如，您可以选择仅显示您在过去30天中创建的事件。

在旅程列表(下 **[!UICONTROL Home]**)中，除了“旅程” **[!UICONTROL Creation filters]**&#x200B;之外，您还可以根据所显示的旅程的状态和版本(**[!UICONTROL Status and version filters]**)筛选这些旅程。 您还可以选择仅显示使用特定事件、字段组或操作(和&#x200B;**[!UICONTROL Activity filters]** )的旅程。您可 **[!UICONTROL Data filters]****[!UICONTROL Publication filters]** 以选择发布日期或用户。 例如，您可以选择仅显示昨天发布的最新版本实时旅程。 请参见 [](../building-journeys/using-the-journey-designer.md)。

>[!NOTE]
>
>请注意，使用列表右上角的配置按钮可以个性化显示的列。 为每个用户保存个性化。

通过 **[!UICONTROL Last update]** 和 **[!UICONTROL Last update by]** 列，可显示您的旅程的上次更新时间以及操作该旅程的用户。

![](../assets/journey74.png)

在事件、数据源和操作配置窗格中，字 **[!UICONTROL Used in]** 段显示使用该特定事件、字段组或操作的旅程数。 您可以单击该 **[!UICONTROL View journeys]** 按钮以显示相应旅程列表。

![](../assets/journey3bis.png)

在不同的列表中，您可以对每个元素执行基本操作。 例如，您可以复制或删除项目。

![](../assets/journey4.png)

## 浏览数据平台字段 {#friendly-names-display}

定义事 [件有效负荷](../event/defining-the-payload-fields.md)、字段 [组有效负荷和在表达式编辑器中选择字段时](../datasource/field-groups.md)[](../expression/expressionadvanced.md)，除字段名称外，还显示显示名称。 此信息是从体验数据模型中的架构定义中检索的。

如果在设置架构时提供了诸如“xdm:alternateDisplayInfo”的描述符，则用户友好名称将替换显示名称。 在使用“eVar”和通用字段时，此功能尤其有用。您可以通过API调用配置易记名称描述符。 有关详细信息，请参阅“架构注 [册”开发人员指南](https://www.adobe.io/apis/experienceplatform/home/xdm/xdmservices.html#!api-specification/markdown/narrative/technical_overview/schema_registry/schema_registry_developer_guide.md)。

![](../assets/xdm-from-descriptors.png)

如果有友好名称可用，则字段将显示为 `<friendly-name>(<name>)`。 例如，如果没有可用的友好名称，将显示显示名称 `<display-name>(<name>)`。 如果未定义这些字段，则只显示字段的技术名称 `<name>`。

>[!NOTE]
>
>当您从架构的联合中选择字段时，不检索友好名称。

## 使用不同的快捷键{#section_ksq_zr1_ffb}

以下是Journey Orcheration界面中提供的不同快捷键。

_在旅程、操作、数据源或事件列表中：_

* 按 **c** ，创建新的旅程、操作、数据源或事件。

_在旅程中配置活动时：_

画布会自动保存。 您可以在画布的左上角看到保存状态。

* 按 **Esc** 可关闭配置窗格并放弃所做的更改。 这相当于按 **[!UICONTROL Cancel]** 钮。
* 按 **[!UICONTROL Enter]** 或单击窗格外部以关闭配置窗格。 更改已保存。 这相当于按 **[!UICONTROL Ok]** 钮。
* 如果按或 **[!UICONTROL Delete]** Backspace **键**，则可以按以 **[!UICONTROL Enter]** 确认删除。

_弹出窗口中：_

* 按 **Escape** ，关闭它(相当于“ **Cancel** ”按钮)。
* 按 **[!UICONTROL Enter]** 以保存或确认(相当于 **[!UICONTROL Ok]** 或 **[!UICONTROL Save]** 按钮)。

_在事件、数据源或操作配置窗格中：_

* 按 **Esc** ，关闭配置窗格而不保存。
* 按 **[!UICONTROL Enter]** 以保存修改并关闭配置窗格。
* 按 **Tab** ，在不同字段之间跳转以进行配置。

_在简单的表达式编辑器中_

* 双击左侧的字段以添加查询（等效于拖放）。

_浏览XDM字段时：_

* 选中“节点”将选择该节点的所有字段。

_在所有文本区域中：_

* 使用 **Ctrl/Command + a组合键** ，选择文本。 在有效负荷预览中，它选择有效负荷。

_在具有搜索栏的屏幕中：_

* 使用 **Ctrl/Command + f组合键** ，选择搜索栏。

_在旅程的画布中：_

* 使用 **Ctrl/Command + a组合键** ，选择所有活动。
* 选择一个或多个活动后，按 **[!UICONTROL Delete]** 或 **空格** ，删除它们。 然后，您可以 **[!UICONTROL Enter]** 在确认弹出窗口中按确认。
* 从左侧调色板中双击某个活动，将其添加到第一个可用位置（从上到下）。
