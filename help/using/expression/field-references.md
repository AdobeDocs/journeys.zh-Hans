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
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 8be9cd1803ab2f7093934424c36fcd7407a4a20a

---



# 字段引用 {#concept_fkj_ll5_dgb}

字段引用可附加到事件或字段组。 唯一有意义的信息是字段的名称及其路径。

如果在字段中使用特殊字符，则需要使用双引号或简单引号。 以下是需要引号的情况：

* 字段以数字字符开头
* 字段以“-”字符开头
* 该字段包含除以下内容之外的任何内容： _a_-_z_, _A_-_z,_ A- _Z,A-Z,A-Z,_ A-Z,A-Z,A ___-Z-,A-Z,A-Z,A-Z-A-B,A-Z-A-Z,M-B-B-A-B-B-B-B-B-B-B-B-B-B-B-B-B-B-B-B-B-B-B-B-B-B-B-B-B-B-B-B-B-B-B-B-B-B-B-B-B-B-B-B-B-B-B-B-B-B-B-B-_

例如，如果字段为 _3h_:# _{OpenWeather.weatherData.rain.&#39;3h&#39;} > 0_

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

默认值可以与字段名称相关联。 语法如下：


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
>字段的类型和默认值必须相同。 例如，@{LobbyBeacon.endUserID。_experience.emailid.id, defaultValue :2}将无效，因为默认值是整数，而预期值应为字符串。

**集合中字段的引用**

集合中定义的元素使用特定函数全部、第一个和最后一个引用。 For more information, see [](../expression/collection-management-functions.md).

例如：

```
@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all()
```

**引用地图中定义的字段**&#x200B;为了检索地图中的元素，我们使用带有给定键的条目函数。 例如，根据所选的命名空间定义事件的键时使用它。 请参阅选择命名空间。 For more information, see [](../event/selecting-the-namespace.md).

```
@{MyEvent.identityMap.entry('Email').first().id}
```

在此表达式中，我们将获取活动“IdentityMap”字段的“Email”键条目。 “电子邮件”条目是一个集合，我们使用“first()”从中获取第一个元素中的“id”。 For more information, see [](../expression/collection-management-functions.md).

**数据源的参数值（数据源动态值）**

如果从外部数据源中选择一个需要调用参数的字段，则右侧会显示一个新选项卡，允许您指定此参数。 请参见 [](../expression/expressionadvanced.md)。

对于更复杂的用例，如果要将数据源的参数包含在主表达式中，则可以使用关键字参数定义其 _值_。 参数可以是任何有效的表达式，即使来自另一个也包含另一个参数的数据源也是如此。

>[!NOTE]
>
>在表达式中定义参数值时，右侧的选项卡会消失。

请使用以下语法：

```
#{<datasource>.<field group>.fieldName, params: {<params-1-name>: <params-1-value>, <params-2-name>: <params-2-value>}}
```

* **`<params-1-name>`**:数据源中第一个参数的精确名称。
* **`<params-1-value>`**:第一个参数的值。 它可以是任何有效的表达式。

例如：

```
#{Weather.main.temperature, params: {localisation: @{Profile.address.localisation}}}
#{Weather.main.temperature, params: {localisation: #{GPSLocalisation.main.coordinates, params: {city: @{Profile.address.city}}}}}
```
