---
title: 字段引用
description: 了解高级表达式中的字段引用
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: b852c08a488a1bec02b8b31a1fccf1a8773b99af
workflow-type: tm+mt
source-wordcount: '424'
ht-degree: 1%

---



# 字段引用 {#concept_fkj_ll5_dgb}

字段引用可附加到事件或字段组。 唯一有意义的信息是字段的名称及其路径。

如果在字段中使用特殊字符，则需要使用多次引号或简单引号。 以下是需要引号的情况：

* 具有数字特征的场开始
* 带有“-”字符的字段开始
* 该字段包含除以下内容之外的任何内容： _a_-z _、_ A _-_ Z、_0_- _,____, 9,_

例如，如果字段为 _3h_: _#{OpenWeather.weatherData.rain。&#39;3h&#39;} > 0_

```
// event field
@{<event name>.<XDM path to the field>}
@{LobbyBeacon.endUserIDs._experience.emailid.id}

// field group
#{<data source name>.<field group name>.<path to the field>}
#{ExperiencePlatform.ProfileFieldGroup.profile.personalEmail.address}
```

在表达式中，事件字段被引用为“@”，数据源字段被引用为“#”。

语法颜色用于以可视方式区分事件字段（绿色）和字段组（蓝色）。

**字段引用的默认值**

默认值可以与字段名称关联。 语法如下：

```
// event field
@{<event name>.<XDM path to the field>, defaultValue: <default value expression>}
@{LobbyBeacon.endUserIDs._experience.emailid.id, defaultValue: "example@adobe.com"}
// field group
#{<data source name>.<field group name>.<path to the field>, defaultValue: <default value expression>}
#{ExperiencePlatform.ProfileFieldGroup.profile.personalEmail.address, defaultValue: "example@adobe.com"}
```

>[!NOTE]
>
>字段的类型和默认值必须相同。 例如，@{LobbyBeacon.endUserIDs。_experience.emailid.id, defaultValue :2}将无效，因为默认值是整数，而预期值应为字符串。

**集合中字段的引用**

集合中定义的元素使用特定函数all、first和last进行引用。 For more information, see [](../expression/collection-management-functions.md).

示例 :

```
@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all()
```

**在映射中定义的字段的引用**

为了在地图中检索元素，我们使用带给定键的输入函数。 例如，根据所选事件定义命名空间的键时，会使用它。 请参阅选择命名空间。 For more information, see [](../event/selecting-the-namespace.md).

```
@{MyEvent.identityMap.entry('Email').first().id}
```

在此表达式中，我们将获得事件“IdentityMap”字段的“Email”键。 “Email”条目是一个集合，我们从中使用“first()”获取第一个元素中的“id”。 For more information, see [](../expression/collection-management-functions.md).

**数据源的参数值（数据源动态值）**

如果从外部数据源中选择一个需要调用参数的字段，则右侧会显示一个新选项卡，用于指定此参数。 请参见 [](../expression/expressionadvanced.md)。

For more complex use cases, if you want to include the parameters of the data source in the main expression, you can define their values using the keyword _params_. 参数可以是任何有效表达式，即使来自另一个数据源也可以是另一个参数。

>[!NOTE]
>
>在表达式中定义参数值时，右侧的选项卡消失。

使用以下语法：

```
#{<datasource>.<field group>.fieldName, params: {<params-1-name>: <params-1-value>, <params-2-name>: <params-2-value>}}
```

* **`<params-1-name>`**:数据源中第一个参数的确切名称。
* **`<params-1-value>`**:第一个参数的值。 它可以是任何有效的表达式。

示例:

```
#{Weather.main.temperature, params: {localisation: @{Profile.address.localisation}}}
#{Weather.main.temperature, params: {localisation: #{GPSLocalisation.main.coordinates, params: {city: @{Profile.address.city}}}}}
```
