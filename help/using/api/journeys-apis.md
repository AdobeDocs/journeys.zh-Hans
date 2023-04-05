---
product: adobe campaign
title: 历程API入门
description: 了解有关历程API的更多信息
products: journeys
feature: Journeys
role: User
level: Intermediate
source-git-commit: fa493cf1e856378e4d79a6932c30cebf5e11e028
workflow-type: tm+mt
source-wordcount: '832'
ht-degree: 2%

---

# 历程API入门

## 关于上限和限制API

在配置数据源或操作时，您需要建立与系统的连接，以检索要在历程中使用的其他信息，或者发送消息或API调用。

历程API支持每秒最多5000个事件，但某些外部系统或API的吞吐量可能不相等。 为防止这些系统过载，您可以使用 **上限** 和 **限制** 用于限制每秒发送的事件数的API。

每次按历程执行API调用时，它都会通过API引擎。 如果达到API中设置的限制，则如果您使用上限API，则调用将被拒绝；或者，如果您使用限制API，则调用会按收到的顺序尽快排队6小时进行处理。

例如，假设您为外部系统定义了每秒100次调用的上限或限制规则。 在10个不同历程中，系统由自定义操作调用。 如果一个历程每秒收到200个调用，则它将使用100个可用插槽，并丢弃或排入剩余100个插槽的队列。 由于超出了最大速率，因此其他9个历程将没有任何插槽。 此粒度有助于保护外部系统免遭过载和崩溃。

>[!IMPORTANT]
>
>**上限规则** 在沙盒级别为特定端点（称为的URL）配置，但全局应用于该沙盒的所有历程。
>
>**限制规则** 仅在生产沙箱上配置，用于特定端点，但全局用于所有沙箱中的所有历程。 每个组织只能有一个限制配置。

有关如何使用这些API的更多信息，请参阅以下章节：

* [API上限](capping.md)
* [限制API](throttling.md)

这两个API还在可用的Swagger文件中进行了描述 [此处](https://adobedocs.github.io/JourneyAPI/docs/).

## 数据源和自定义操作容量 {#capacity}

对于 **外部数据源**，则每秒的最大调用数限制为15。 如果超出此限制，则会根据所使用的API，丢弃或排入任何其他调用。 通过联系Adobe以在中包含端点，可以增加专用外部数据源的此限制，但允许列表对于公共外部数据源，此选项不可用。 * [了解如何配置数据源](../datasource/about-data-sources.md).

>[!NOTE]
>
>如果数据源使用的自定义身份验证的端点与数据源使用的端点不同，则您需要联系Adobe以将该端点也包含在允许列表中。

对于 **自定义操作**，您需要评估外部API的容量。 例如，如果Journey Optimizer每秒发送1000个调用，而您的系统每秒只能支持100个调用，则您需要定义上限或流量配置，以便系统不会饱和。 [了解如何配置操作](../action/action.md)

## 设置 API 访问 {#api}

要将这些API与 [!DNL Journey Orchestration] 实例中，您需要使用AdobeI/O控制台。 [!DNL Journey Orchestration] 通过以下步骤设置API访问。 有关每个步骤的详细信息，请参见 [Adobe I/O文档](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).

>[!CAUTION]
>
>要在Adobe I/O中管理证书，请确保 <b>系统管理员</b> 组织或 [开发人员帐户](https://helpx.adobe.com/enterprise/using/manage-developers.html) 中。

1. **检查您是否拥有数字证书**，或根据需要创建一个。 在以下步骤中需要随证书一起提供的公钥和私钥。
1. **创建新集成 [!DNL Journey Orchestration] 服务** Adobe I/O并对其进行配置。 需要产品配置文件访问权限 [!DNL Journey Orchestration] 和Adobe Experience Platform。 随后将生成您的凭据（API密钥、客户端密钥……）。
1. **创建JSON Web令牌(JWT)** 使用您的私钥对其进行签名。 JWT会对Adobe验证您的身份并授予您访问API的权限所需的所有身份和安全信息进行编码。 此中详细介绍了此步骤 [部分](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md)
1. **将JWT交换为访问令牌** 通过POST请求或通过开发人员控制台界面。 此访问令牌必须用在API请求的每个标头中。

要建立安全的服务到服务Adobe I/OAPI会话，对Adobe服务的每个请求都必须在授权标头中包含以下信息。

```
curl -X GET https://journey.adobe.io/authoring/XXX \
 -H 'Authorization: Bearer <ACCESS_TOKEN>' \
 -H 'x-api-key: <API_KEY>' \
 -H 'x-gw-ims-org-id: <ORGANIZATION>'
```

* **&lt;organization>**:这是您的个人组织ID，Adobe会为您的每个实例提供一个组织ID。 要获取您的组织ID值，请咨询您的管理员或Adobe技术联系人。 您还可以在创建新集成时，在许可证列表中将其检索到Adobe I/O中(请参阅 <a href="https://www.adobe.io/authentication.html">Adobe I/O文档</a>)。

* **&lt;access_token>**:您的个人访问令牌，在通过POST请求交换JWT时检索。

* **&lt;api_key>**:您的个人API密钥。 它在创建与的新集成后在Adobe I/O中提供 [!DNL Journey Orchestration] 服务。
