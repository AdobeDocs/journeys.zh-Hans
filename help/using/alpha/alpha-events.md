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
source-git-commit: f146a22cec5ffbbc61b51f8fc3c875078b2ee6bf
workflow-type: tm+mt
source-wordcount: '380'
ht-degree: 4%

---


# 基于规则的事件{#simplified-events}

我们简化了您设置体验事件的方式。 我们引入了一种无需使用eventID的新方法。 在Journey Orchestration中设置事件时，您现在可以定义基于规则的事件。

此新类型的事件不生成eventID。 使用简单的表达式编辑器，您现在只需定义一个规则，系统将使用该规则来识别将触发您旅程的相关事件。 此规则可以基于事件有效负荷中可用的任何字段，例如用户档案的位置或添加到用户档案购物车的项目数。

这种新方法对用户来说大多是透明的。 唯一的更改是事件定义屏幕中的新字段。

1. 在左侧菜单中，单击“管 **理员** ”图标，然后单 **击事件**。 将显示事件列表。

   ![](../assets/alpha-event1.png)

1. Click **Add** to create a new event. 事件配置窗格将在屏幕右侧打开。

   ![](../assets/alpha-event2.png)

1. 输入事件的名称。 您还可以添加描述。

   ![](../assets/alpha-event3.png)

1. 在新的 **事件ID类型** 字段中，选 **择规则**。

   ![](../assets/alpha-event4.png)

   >[!NOTE]
   >
   >“ **系统生成** ”类型是需要eventID的现有方法。 请参 [阅此部分](../event/about-events.md)。

1. 定义 **模式** 和有效 **负荷字段**。 请参 [阅此部分](../event/defining-the-payload-fields.md)。

   ![](../assets/alpha-event5.png)

   >[!NOTE]
   >
   >当您选择“系 **统生成”类型**&#x200B;时，只有具有eventID类型混音的模式可用。 当您选择基于 **规则的类** 型时，所有体验事件模式均可用。

1. 在事件ID条 **件字段内单击** 。 使用简单的表达式编辑器，定义系统将使用的条件，以识别将触发您旅程的事件。

   ![](../assets/alpha-event6.png)

   在我们的例子中，我们根据用户档案的城市写了一个条件。 这意味着，每当系统收到与此条件(City **字段** 和Paris值 **)匹配** 的事件时，它都会将其传递给Journey Orchestration。

1. 定义 **命名空间** 和 **密钥**。 请参 [阅选择命名空间](../event/selecting-the-namespace.md)[和定义事件键](../event/defining-the-event-key.md)。

   ![](../assets/alpha-event7.png)

事件配置和旅程创建的其他步骤保持不变。

该事件现已配置好，可以像任何其他事件一样被丢弃到旅程中。 每次将与规则匹配的事件发送到系统时，都会将其传递给Journey Orchestration以触发您的旅程。

