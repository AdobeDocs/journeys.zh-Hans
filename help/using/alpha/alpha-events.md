---
title: 基于规则的事件
description: 进一步了解基于规则的事件。
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
source-git-commit: 9cdaa673dbe9247aa1e9c9aef58cfa003d014786
workflow-type: tm+mt
source-wordcount: '656'
ht-degree: 11%

---


# 基于规则的事件{#simplified-events}

我们简化了您设置体验事件的方式。我们正在引入一种无需使用 eventID 的新方法。在 Journey Orchestration 中设置事件时，现在可以定义基于规则的事件。

此新类型的事件不生成eventID。 使用简单的表达式编辑器，您现在只需定义一个规则，系统将使用该规则来识别将触发您旅程的相关事件。 此规则可以基于事件有效负荷中可用的任何字段，例如用户档案的位置或添加到用户档案购物车的项目数。

这种新方法对用户来说大多是透明的。 唯一的更改是事件定义屏幕中的新字段。

>[!CAUTION]
>
>为基于规则的事件定义限制规则。 它将旅程可处理的合格事件数限制为每分钟40万。 请联系您的Alpha项目联系人以了解更多信息。

## 利用Adobe Analytics数据{#analytics-data}

>[!NOTE]
>
>本条仅适用于需要使用Adobe Analytics数据的客户。

您可以利用您已捕获的所有Adobe Analytics行为事件数据并将其流化到平台中，以触发旅程并为客户自动化体验。

为了使此功能正常工作，您需要在Adobe Experience Platform激活要利用的报表包：

1. 在Adobe Experience Platform，选 **[!UICONTROL Sources]** 择“ **[!UICONTROL Add data]** Adobe Analytics”部分。 将显示可用Adobe Analytics报表包的列表。

1. 选择要启用的报表包，单击并 **[!UICONTROL Next]** 单击 **[!UICONTROL Finish]**。

1. 与Alpha项目联系人共享源数据ID。

这将启用该报表包的Analytics源连接器。 每当数据传入时，它都会转换为体验事件并发送到Adobe Experience Platform。

![](../assets/alpha-event9.png)

有关Adobe Analytics源连接器的详细信息，请参阅文 [档](https://docs.adobe.com/help/en/experience-platform/sources/connectors/adobe-applications/analytics.html) 和 [教程](https://docs.adobe.com/content/help/en/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html)。

## 配置基于规则的事件{#configuring-rule-based}

1. 从左侧菜单，单击图 **[!UICONTROL Admin]** 标，然后单击 **[!UICONTROL Events]**。 将显示事件列表。

   ![](../assets/alpha-event1.png)

1. 单击&#x200B;**[!UICONTROL Add]**&#x200B;以创建新事件。事件配置窗格将在屏幕右侧打开。

   ![](../assets/alpha-event2.png)

1. 输入事件的名称。 您还可以添加描述。

   ![](../assets/alpha-event3.png)

1. In the new **[!UICONTROL Event ID type]** field, select **[!UICONTROL Rule Based]**.

   ![](../assets/alpha-event4.png)

   >[!NOTE]
   >
   >类 **[!UICONTROL System Generated]** 型是需要eventID的现有方法。 请参阅[此章节](../event/about-events.md)。

1. 定义有 **[!UICONTROL Schema]** 效负荷 **[!UICONTROL Fields]**。 请参阅[此章节](../event/defining-the-payload-fields.md)。

   ![](../assets/alpha-event5.png)

   >[!NOTE]
   >
   >当您选择时， **[!UICONTROL System Generated type]**&#x200B;只有具有eventID类型mixin的模式才可用。 选择类型时， **[!UICONTROL Rule Based]** 所有体验事件模式均可用。

1. 在字段内 **[!UICONTROL Event ID condition]** 单击。 使用简单的表达式编辑器，定义系统将使用的条件，以识别将触发您旅程的事件。

   ![](../assets/alpha-event6.png)

   在我们的例子中，我们根据用户档案的城市写了一个条件。 这意味着，只要系统收到与此条件（字段和值）匹&#x200B;**[!UICONTROL City]** 配的事件 **[!UICONTROL Paris]** ，它就会将其传递给Journey Orchestration。

1. 定义 **[!UICONTROL Namespace]** 和 **[!UICONTROL Key]**。 请参 [阅选择命名空间](../event/selecting-the-namespace.md)[和定义事件键](../event/defining-the-event-key.md)。

   ![](../assets/alpha-event7.png)

事件配置和旅程创建的其他步骤保持不变。

该事件现已配置好，可以像任何其他事件一样被丢弃到旅程中。 每次将与规则匹配的事件发送到系统时，都会将其传递给Journey Orchestration以触发您的旅程。

## 基于规则的事件的测试模式{#test-rule-based}

测试模式也适用于使用基于规则的事件的旅程。

触发事件时， **事件配置** 屏幕允许您定义要通过测试的事件参数。 您可以单击右上角的工具提示图标来视图事件ID条件。 作为规则评估的一部分的每个字段旁边也会显示工具提示。

![](../assets/alpha-event8.png)

For more information on how to use the test mode, refer to [](../building-journeys/testing-the-journey.md).

