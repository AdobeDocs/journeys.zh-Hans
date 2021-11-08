---
product: adobe campaign
title: 字段引用
description: 了解高级表达式中的字段引用
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 2f317306-9afd-4e9a-88b8-fc66102e1046
source-git-commit: e4a003656058ac7ae6706e22fd5162c9e875629a
workflow-type: tm+mt
source-wordcount: '524'
ht-degree: 3%

---

# 字段引用 {#concept_fkj_ll5_dgb}

字段引用可以附加到事件或字段组。 唯一有意义的信息是字段的名称及其路径。

如果您在字段中使用特殊字符，则需要使用双引号或简单引号。 以下是需要引号的情况：

* 字段以数字字符开头
* 字段以“ — ”字符开头
* 字段包含除以下内容之外的任何内容： _a_-_z_, _A_-_Z_, _0_-_9_, _ , _-_

例如，如果您的字段为 _3小时_: _#{OpenWeather.weatherData.rain.&#39;3h&#39;} > 0_

```json
// event field
@{<event name>.<XDM path to the field>}
@{LobbyBeacon.endUserIDs._experience.emailid.id}

// field group
#{<data source name>.<field group name>.<path to the field>}
#{ExperiencePlatform.ProfileFieldGroup.profile.personalEmail.address}
```

在表达式中，事件字段被引用“@”，数据源字段被引用“#”。

语法颜色用于直观地区分事件字段（绿色）和字段组（蓝色）。

## 字段引用的默认值

默认值可与字段名称关联。 语法如下所示：

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
>字段类型和默认值必须相同。 例如，@{LobbyBeacon.endUserIDs。_experience.emailid.id， defaultValue :2}将无效，因为默认值是整数，而预期值应为字符串。

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

## 对集合中字段的引用

使用特定函数引用集合中定义的元素 `all`, `first` 和 `last`. 有关详细信息，请参见[此页面](../expression/collection-management-functions.md)。

示例 :

```json
@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all()
```

## 对映射中定义的字段的引用

### `entry` 函数

为了检索映射中的元素，我们使用包含给定键的条目函数。 例如，在根据所选命名空间定义事件的键时，会使用该键。 请参阅选择命名空间。 有关更多信息，请参阅 [本页](../event/selecting-the-namespace.md).

```json
@{MyEvent.identityMap.entry('Email').first().id}
```

在此表达式中，我们将获取事件“IdentityMap”字段的“Email”键的条目。 “Email”条目是一个集合，我们从中使用“first()”获取第一个元素中的“id”。 有关更多信息，请参阅 [本页](../expression/collection-management-functions.md).

### `firstEntryKey` 函数

要检索映射的第一个条目键，请使用 `firstEntryKey` 函数。

此示例显示如何检索特定列表订阅者的第一个电子邮件地址：

```json
#{ExperiencePlatform.Subscriptions.profile.consents.marketing.email.subscriptions.entry('daily-email').subscribers.firstEntryKey()}
```

在本例中，订阅列表名为 `daily-email`. 电子邮件地址在 `subscribers` 映射，链接到订阅列表映射。

### `keys` 函数

要检索到映射的所有键，请使用 `keys` 函数。

此示例显示如何为特定用户档案检索与特定列表订阅者关联的所有电子邮件地址：

```json
#{ExperiencePlatform.Subscriptions.profile.consents.marketing.email.subscriptions.entry('daily-mail').subscribers.keys()
```

## 数据源的参数值（数据源动态值）

如果从外部数据源中选择字段需要调用参数，则右侧会显示一个新选项卡，用于指定此参数。 请参阅[此页](../expression/expressionadvanced.md)。

对于更复杂的用例，如果要在主表达式中包含数据源的参数，可以使用关键字定义其值 _params_. 参数可以是任何有效表达式，即使来自其他数据源（也包含其他参数）的参数也是如此。

>[!NOTE]
>
>在表达式中定义参数值时，右侧的选项卡会消失。

使用以下语法：

```json
#{<datasource>.<field group>.fieldName, params: {<params-1-name>: <params-1-value>, <params-2-name>: <params-2-value>}}
```

* **`<params-1-name>`**:数据源中第一个参数的确切名称。
* **`<params-1-value>`**:第一个参数的值。 它可以是任何有效的表达式。

示例：

```json
#{Weather.main.temperature, params: {localisation: @{Profile.address.localisation}}}
#{Weather.main.temperature, params: {localisation: #{GPSLocalisation.main.coordinates, params: {city: @{Profile.address.city}}}}}
```
