---
product: adobe campaign
title: 字段引用
description: 瞭解進階運算式中的欄位參考
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 2f317306-9afd-4e9a-88b8-fc66102e1046
source-git-commit: bb07c0edaae469962ee3bf678664b4a0a83572fe
workflow-type: tm+mt
source-wordcount: '557'
ht-degree: 3%

---

# 字段引用 {#concept_fkj_ll5_dgb}

欄位參考可附加至事件或欄位群組。 唯一有意義的資訊是欄位名稱及其路徑。

如果您在欄位中使用特殊字元，則需要使用雙引號或簡單引號。 以下是需要報價的情況：

* 欄位以數字字元開頭
* 欄位以「 — 」字元開頭
* 欄位包含下列專案以外的任何專案： _a_-_z_， _A_-_Z_， _0_-_9_， _ ， _-_

例如，如果您的欄位為 _3h_： _#{OpenWeather.weatherData.rain.&#39;3h&#39;} > 0_

```json
// event field
@{<event name>.<XDM path to the field>}
@{LobbyBeacon.endUserIDs._experience.emailid.id}

// field group
#{<data source name>.<field group name>.<path to the field>}
#{ExperiencePlatform.ProfileFieldGroup.profile.personalEmail.address}
```

在運算式中，事件欄位以「@」參照，資料來源欄位以「#」參照。

語法顏色是用來在視覺上區分事件欄位（綠色）和欄位群組（藍色）。

## 欄位參考的預設值 {#default-value}

預設值可與欄位名稱相關聯。 語法如下：

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
>欄位型別和預設值必須相同。 例如，@{LobbyBeacon.endUserIDs。_experience.emailid.id， defaultValue ： 2}將無效，因為預設值是整數，而預期值應為字串。

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

您可以新增任何型別的運算式作為預設值。 唯一的限制是運算式必須傳回預期的資料型別。 使用函式時，需要使用()封裝函式。

```
#{ExperiencePlatform.Subscriptions.profile.consents.marketing.any.time, defaultValue : (now())} 
== date("2022-02-10T00:00:00Z")
```

## 集合內欄位的參考

集合中定義的元素會使用特定函式來參照 `all`， `first` 和 `last`. 有关详细信息，请参见[此页面](../expression/collection-management-functions.md)。

示例：

```json
@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all()
```

## 參照地圖中定義的欄位

### `entry` 函数

為了擷取對應中的元素，我們使用具有給定索引鍵的專案函式。 例如，根據選取的名稱空間，在定義事件的索引鍵時會使用它。 請參閱選取名稱空間。 如需詳細資訊，請參閱 [此頁面](../event/selecting-the-namespace.md).

```json
@{MyEvent.identityMap.entry('Email').first().id}
```

在此運算式中，我們取得事件之「IdentityMap」欄位的「Email」索引鍵。 &#39;Email&#39;專案是集合，我們使用&#39;first()&#39;從其中取得第一個元素中的&#39;id&#39;。 如需詳細資訊，請參閱 [此頁面](../expression/collection-management-functions.md).

### `firstEntryKey` 函数

若要擷取對映的第一個專案鍵，請使用 `firstEntryKey` 函式。

此範例顯示如何擷取特定清單中訂閱者的第一個電子郵件地址：

```json
#{ExperiencePlatform.Subscriptions.profile.consents.marketing.email.subscriptions.entry('daily-email').subscribers.firstEntryKey()}
```

在此範例中，訂閱清單名為 `daily-email`. 電子郵件地址在中定義為金鑰 `subscribers` 對應，此對應會連結至訂閱清單對應。

### `keys` 函数

若要擷取到地圖的所有索引鍵，請使用 `keys` 函式。

此範例說明如何針對特定設定檔擷取與特定清單訂閱者相關聯的所有電子郵件地址：

```json
#{ExperiencePlatform.Subscriptions.profile.consents.marketing.email.subscriptions.entry('daily-mail').subscribers.keys()
```

## 資料來源的引數值（資料來源動態值）

如果您從外部資料來源選取欄位，需要呼叫引數，右側會出現一個新索引標籤，可讓您指定此引數。 请参阅[此页](../expression/expressionadvanced.md)。

對於更複雜的使用案例，如果您想將資料來源的引數納入主要運算式中，則可使用關鍵字定義其值 _引數_. 引數可以是任何有效的運算式，即使來自包含其他引數的另一個資料來源亦然。

>[!NOTE]
>
>當您在運算式中定義引數值時，右側的標籤會消失。

使用下列語法：

```json
#{<datasource>.<field group>.fieldName, params: {<params-1-name>: <params-1-value>, <params-2-name>: <params-2-value>}}
```

* **`<params-1-name>`**：資料來源中第一個引數的確切名稱。
* **`<params-1-value>`**：第一個引數的值。 它可以是任何有效的運算式。

示例：

```json
#{Weather.main.temperature, params: {localisation: @{Profile.address.localisation}}}
#{Weather.main.temperature, params: {localisation: #{GPSLocalisation.main.coordinates, params: {city: @{Profile.address.city}}}}}
```
