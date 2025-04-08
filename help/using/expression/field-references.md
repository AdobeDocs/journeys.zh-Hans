---
product: adobe campaign
title: 字段引用
description: 了解高级表达式中的字段引用
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 2f317306-9afd-4e9a-88b8-fc66102e1046
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '607'
ht-degree: 2%

---

# 字段引用 {#concept_fkj_ll5_dgb}


>[!CAUTION]
>
>**正在查找Adobe Journey Optimizer**？ 单击[此处](https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer/using/ajo-home){target="_blank"}获取Journey Optimizer文档。
>
>
>_本文档参考已被Journey Optimizer替换的旧版Journey Orchestration资料。 如果您对访问Journey Orchestration或Journey Optimizer有任何疑问，请联系您的帐户团队。_


字段引用可以附加到事件或字段组。 唯一有意义的信息是字段的名称及其路径。

如果您在字段中使用特殊字符，则需要使用双引号或简单引号。 以下是需要引用时的情况：

* 该字段以数字字符开头
* 字段以“ — ”字符开头
* 该字段包含&#x200B;_a_-_z_、_A_-_Z_、_0_-_9_、_、_-_&#x200B;以外的任何内容

例如，如果您的字段是&#x200B;_3h_： _#{OpenWeather.weatherData.rain.&#39;3h&#39;} > 0_

```json
// event field
@{<event name>.<XDM path to the field>}
@{LobbyBeacon.endUserIDs._experience.emailid.id}

// field group
#{<data source name>.<field group name>.<path to the field>}
#{ExperiencePlatform.ProfileFieldGroup.profile.personalEmail.address}
```

在表达式中，事件字段通过“@”引用，数据源字段通过“#”引用。

语法颜色用于直观地区分事件字段（绿色）和字段组（蓝色）。

## 字段引用的默认值 {#default-value}

默认值可以与字段名称关联。 语法如下：

```json
// event field
@{<event name>.<XDM path to the field>, defaultValue: <default value expression>}
@{LobbyBeacon.endUserIDs._experience.emailid.id, defaultValue: "example@adobe.com"}
// field group
#{<data source name>.<field group name>.<path to the field>, defaultValue: <default value expression>}
#{ExperiencePlatform.ProfileFieldGroup.profile.personalEmail.address, defaultValue: "example@adobe.com"}
```

>[!NOTE]
>
>字段的类型和默认值必须相同。 例如，@{LobbyBeacon.endUserIDs._experience.emailid.id， defaultValue ： 2}将无效，因为默认值为整数，而预期值应为字符串。

示例：

```json
// for an event 'OrderEvent' having the following payload:
{
    "orderId": "12345"
}
 
expression example:
- @{OrderEvent.orderId}                                    -> "12345"
- @{OrderEvent.producdId, defaultValue : "not specified" } -> "not specified" // default value, productId is not a field present in the payload
- @{OrderEvent.productId}                                  -> null
 
 
// for an entity 'Profile' on datasource 'ACP' having fields person/lastName, with fetched data such as:
{
    "person": {
        "lastName":"Snow"
    },
    "emails": [
        { "email":"john.snow@winterfell.westeros" },
        { "email":"snow@thewall.westeros" }
    ]
}
 
expression examples:
- #{ACP.Profile.person.lastName}                 -> "Snow"
- #{ACP.Profile.emails.at(1).email}              -> "snow@thewall.westeros"
- #{ACP.Profile.person.age, defaultValue : -1}   -> -1 // default value, age is not a field present in the payload
- #{ACP.Profile.person.age}                      -> null
```

您可以添加任何类型的表达式作为默认值。 唯一的限制是表达式必须返回预期的数据类型。 使用函数时，需要使用()封装函数。

```
#{ExperiencePlatform.Subscriptions.profile.consents.marketing.any.time, defaultValue : (now())} 
== date("2022-02-10T00:00:00Z")
```

## 对收藏集中字段的引用

集合中定义的元素使用特定函数`all`、`first`和`last`引用。 有关详细信息，请参见[此页面](../expression/collection-management-functions.md)。

示例：

```json
@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all()
```

## 对映射中定义的字段的引用

### `entry`函数

为了检索映射中的元素，我们使用带有给定键的入口函数。 例如，在根据选定的命名空间定义事件的键时使用该变量。 请参阅选择命名空间。 有关详细信息，请参阅[此页面](../event/selecting-the-namespace.md)。

```json
@{MyEvent.identityMap.entry('Email').first().id}
```

在此表达式中，我们将获得事件的“IdentityMap”字段的“Email”键的条目。 “Email”条目是一个集合，我们从其中使用“first()”获取第一个元素中的“id”。 有关详细信息，请参阅[此页面](../expression/collection-management-functions.md)。

### `firstEntryKey`函数

要检索映射的第一个条目键，请使用`firstEntryKey`函数。

此示例说明如何检索特定列表订阅者的第一个电子邮件地址：

```json
#{ExperiencePlatform.Subscriptions.profile.consents.marketing.email.subscriptions.entry('daily-email').subscribers.firstEntryKey()}
```

在此示例中，订阅列表名为`daily-email`。 电子邮件地址在`subscribers`映射中定义为键，该映射链接到订阅列表映射。

### `keys`函数

要检索到映射的所有键，请使用`keys`函数。

此示例说明如何为特定用户档案检索与特定列表订阅者关联的所有电子邮件地址：

```json
#{ExperiencePlatform.Subscriptions.profile.consents.marketing.email.subscriptions.entry('daily-mail').subscribers.keys()
```

## 数据源的参数值（数据源动态值）

如果您从外部数据源中选择字段，则需要调用一个参数，则右侧会显示一个新选项卡，允许您指定此参数。 请参阅[此页](../expression/expressionadvanced.md)。

对于更复杂的用例，如果要在主表达式中包含数据源的参数，可以使用关键字&#x200B;_params_&#x200B;定义其值。 参数可以是任何有效的表达式，即使来自还包含另一个参数的另一个数据源也是如此。

>[!NOTE]
>
>在表达式中定义参数值时，右侧的选项卡消失。

使用以下语法：

```json
#{<datasource>.<field group>.fieldName, params: {<params-1-name>: <params-1-value>, <params-2-name>: <params-2-value>}}
```

* **`<params-1-name>`**：数据源中第一个参数的确切名称。
* **`<params-1-value>`**：第一个参数的值。 它可以是任何有效的表达式。

示例：

```json
#{Weather.main.temperature, params: {localisation: @{Profile.address.localisation}}}
#{Weather.main.temperature, params: {localisation: #{GPSLocalisation.main.coordinates, params: {city: @{Profile.address.city}}}}}
```
