---
product: adobe campaign
title: 历程 API 入门
description: 了解有关历程 API 的更多信息
products: journeys
feature: Journeys
role: User
level: Intermediate
exl-id: a5dd3d23-c820-4ab7-bc6c-b1dcfe15022c
source-git-commit: 87d5cf223d9adec27eabcb55f2e09aa6d40b23a6
workflow-type: tm+mt
source-wordcount: '791'
ht-degree: 87%

---

# 历程 API 入门

## 关于 API 上限和 API 限制

在配置数据源或操作时，您需要建立与系统的连接，以检索要在历程中使用的其他信息，或者发送消息或 API 调用。

历程 API 支持每秒最多 5000 个事件，但某些外部系统或 API 的吞吐量可能不同。为防止这些系统过载，您可以使用&#x200B;**API 上限**&#x200B;和&#x200B;**API 限制**&#x200B;来限制每秒发送的事件数量。

每次按历程执行 API 调用时，它都会通过 API 引擎。在达到 API 中设置的限制时，如果您使用的是“API 上限”，则会拒绝调用；或者，如果您使用的是“API 限制”，则会按收到的顺序将调用排入等待队列并尽快处理，可能需要 6 小时。

例如，假设您为外部系统定义了每秒100次调用的上限或限制规则。 在 10 个不同历程中，系统由自定义操作调用。如果一个历程每秒收到 200 个调用，则将使用 100 个可用的位置，并丢弃剩余的 100 个调用或将它们排入队列。由于超出了最大使用率，因此其他 9 个历程将没有任何位置。此粒度有助于避免使外部系统出现过载和崩溃。

>[!IMPORTANT]
>
>**上限规则**&#x200B;在沙盒级别针对特定端点（调用的 URL）配置，但在全局范围内应用于该沙盒的所有历程。
>
>**限制规则**&#x200B;仅在生产沙盒上针对特定端点配置，但在全局范围内应用于所有沙盒中的所有历程。只能为每个组织使用一个限制配置。

有关如何使用这些 API 的更多信息，请参阅以下部分：

* [API 上限](capping.md)
* [API 限制](throttling.md)

Swagger 文件中也对这两个 API 进行了说明，请点击[此处](https://adobedocs.github.io/JourneyAPI/docs/)了解详情。

## 数据源和自定义操作容量 {#capacity}

对于&#x200B;**外部数据源**，每秒的最大调用数限制为 15。如果超出此限制，则会根据所使用的 API，丢弃或排入任何其他调用。联系 Adobe 以将端点包含在允许列表中，这样可以增加专用外部数据源的此限制，但对于公共外部数据源不可以这样操作。* [了解如何配置数据源](../datasource/about-data-sources.md)。

>[!NOTE]
>
>如果数据源使用的自定义身份验证的端点与数据源使用的端点不同，您需要联系 Adobe 以将该端点也包含在允许列表中。

对于&#x200B;**自定义操作**，您需要评估外部 API 的容量。例如，如果 Journey Optimizer 每秒发送 1000 个调用，而您的系统每秒只能支持 100 个调用，则需要定义上限或限制配置，以便系统不会饱和。[了解如何配置操作](../action/action.md)

## 设置 API 访问 {#api}

要在 [!DNL Journey Orchestration] 实例中使用这些 API，您需要使用 AdobeI/O 控制台。[!DNL Journey Orchestration] API 访问可通过以下步骤设置。有关每个步骤的详细信息，请参阅 [Adobe I/O 文档](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)。

>[!CAUTION]
>
>要在 Adobe I/O 中管理证书，请确保您具有组织<b>系统管理员</b>权限或拥有 Admin Console [开发人员帐户](https://helpx.adobe.com/cn/enterprise/using/manage-developers.html)。

1. **检查您是否拥有数字证书**，或在必要时创建一个。在以下步骤中需要随证书一起提供的公钥和私钥。
1. **在 Adobe I/O 中创建与 [!DNL Journey Orchestration] 服务**&#x200B;的新集成并对其进行配置。[!DNL Journey Orchestration] 和 Adobe Experience Platform 需要产品配置文件访问权限。随后将生成您的证书（API 密钥、客户端密钥等）。

>[!CAUTION]
>
>已弃用用于生成访问令牌的JWT方法。 所有新的集成都必须使用 [OAuth服务器到服务器身份验证方法](https://experienceleague.adobe.com/docs/experience-platform/landing/platform-apis/api-authentication.html#select-oauth-server-to-server). Adobe还建议您将现有集成迁移到OAuth方法。
>
>请阅读以下重要文档：
>[应用程序从JWT到OAuth的迁移指南](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)，
>[使用OAuth的新旧应用程序的实施指南](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)，
>[使用OAuth服务器到服务器凭据方法的优势](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/#why-oauth-server-to-server-credentials)

要建立安全的服务到服务 Adobe I/O API 会话，对 Adobe 服务提出的每个请求都必须在“Authorization”标头中包含以下信息。

```
curl -X GET https://journey.adobe.io/authoring/XXX \
 -H 'Authorization: Bearer <ACCESS_TOKEN>' \
 -H 'x-api-key: <API_KEY>' \
 -H 'x-gw-ims-org-id: <ORGANIZATION>'
```

* **&lt;ORGANIZATION>**：这是您的个人组织 ID，Adobe 会为每个实例提供一个组织 ID。要获取“ORGANIZATION ID”值，请咨询管理员或 Adobe 技术联系人。您还可以在创建新集成时，在许可证列表中将其检索到 Adobe I/O 中（请参阅 [Adobe I/O 文档](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)）。

* **&lt;access_token>**：您的个人访问令牌

* **&lt;API_KEY>**：您的个人 API 密钥。在将创建与 [!DNL Journey Orchestration] 服务的新集成后，可在 Adobe I/O 中找到。
