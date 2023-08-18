---
product: adobe campaign
title: 导入导出API描述
description: 了解有关导入导出API的更多信息。
products: journeys
source-git-commit: fb6bdb60ac70a94a62956a306bedee9cb607e2a2
workflow-type: tm+mt
source-wordcount: '1123'
ht-degree: 27%

---


# 使用Export-Import API

通过单个API调用导出历程版本及其所有相关对象（历程、事件、数据源、字段组、自定义操作）。 导出结果有效负载可用于轻松将历程导入其他环境（实例或沙盒）。
此功能允许您跨多个实例或针对多个测试环境工作流管理历程。


## 资源

在可用的Swagger文件中介绍了Journey OrchestrationExport-Import API [此处](https://adobedocs.github.io/JourneyAPI/docs/).

要在您的Journey Orchestration实例中使用此API，您需要使用AdobeI/O控制台。 您可以按照以下步骤开始操作 [Adobe Developer控制台快速入门](https://www.adobe.io/apis/experienceplatform/console/docs.html#!AdobeDocs/adobeio-console/master/getting-started.md) 然后使用此页中的部分。

要测试和准备集成，可使用Postman收藏集 [此处](https://raw.githubusercontent.com/AdobeDocs/JourneyAPI/master/postman-collections/Journey-Orchestration_Export-import-API_postman-collection.json).


## Export-Import流

我们建议按照以下步骤跨环境导出和导入您的历程：

1. 在启动环境中创建旅程并为其参数。 [此处提供更多信息](https://experienceleague.adobe.com/docs/journeys/using/building-journeys/about-journey-building/journey.html)
1. 检查历程版本是否没有错误。 [此处提供更多信息](https://experienceleague.adobe.com/docs/journeys/using/building-journeys/testing-the-journey.html)
1. 调用 **/list/journey** 用于检索UID历程和最新历程版本的UID的API。 如有需要，您可以致电 **/journeys/`{uid}`/latest** 以查找最新历程版本的UID。
1. 调用 **导出** 包含启动环境参数（orgID和sandboxName）的API。
1. 打开返回有效负载，然后选中以下项：
   * 如果导出的历程包含 **特定凭据**，您需要将这些凭据替换为与新环境对应的凭据。
   * 如果导出的历程包含 **事件** 指向 **XDM架构**，如果ID值不同，您需要在xdmEntity节点中手动使用新环境的架构ID更新架构ID引用。 需要对每个事件进行此更新。 [此处提供更多信息](https://experienceleague.adobe.com/docs/journeys/using/events-journeys/experience-event-schema.html)
   * 如果您的历程包含电子邮件、短信或推送操作，并且目标环境中的名称与启动环境中的名称不同，则您可能需要更新模板名称或mobileApp名称。
1. 调用 **导入** 包含目标环境参数（orgID和sandboxName）的API。 请注意，您可以根据需要多次调用导入API。 每次调用导入API时，都会生成历程中包含的每个对象的UUID和名称。
1. 导入历程后，您可以在Journey Orchestration应用程序中发布该变量。 更多信息 [此处](https://experienceleague.adobe.com/docs/journeys/using/building-journeys/publishing-the-journey.html)


## 身份验证

### 设置 API 访问

通过以下步骤设置Journey OrchestrationAPI访问。 有关每个步骤的详细信息，请参阅 [Adobe I/O 文档](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)。

>[!CAUTION]
>
>要在 Adobe I/O 中管理证书，请确保您具有组织<b>系统管理员</b>权限或拥有 Admin Console [开发人员帐户](https://helpx.adobe.com/cn/enterprise/using/manage-developers.html)。

1. **检查您是否拥有数字证书**，或在必要时创建一个。在以下步骤中需要随证书一起提供的公钥和私钥。
1. **在 Adobe I/O 中创建与 [!DNL Journey Orchestration] 服务**&#x200B;的新集成并对其进行配置。Journey Orchestration和Adobe Experience Platform需要产品配置文件访问权限。 随后将生成您的证书（API 密钥、客户端密钥等）。
1. 使用您的私钥在之前生成的证书中&#x200B;**创建 JSON Web 令牌 (JWT)** 并对其进行签名。对于 Adobe 验证身份并授予 API 访问权限所需的所有身份和安全信息，JWT 会进行编码。要详细了解此步骤，请参阅此[部分](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md)
1. 通过 POST 请求或 Developer Console 界面&#x200B;**将 JWT 换为访问令牌**。在 API 请求的每个标头中必须使用此访问令牌。

要建立安全的服务到服务 Adobe I/O API 会话，对 Adobe 服务提出的每个请求都必须在“Authorization”标头中包含以下信息。

```
curl -X GET https://journey.adobe.io/authoring/XXX \
 -H 'Authorization: Bearer <ACCESS_TOKEN>' \
 -H 'x-api-key: <API_KEY>' \
 -H 'x-gw-ims-org-id: <ORGANIZATION>'
```

* **&lt;organization>**：这是您的个人组织ID，Adobe会为您每个实例提供一个组织ID：

   * &lt;organization> ：您的生产实例

  要获取“ORGANIZATION ID”值，请咨询管理员或 Adobe 技术联系人。您还可以在创建新集成时，在许可证列表中将其检索到 Adobe I/O 中（请参阅 [Adobe I/O 文档](https://www.adobe.io/authentication.html)）。

* **&lt;ACCESS_TOKEN>**：您的个人访问令牌，通过 POST 请求交换 JWT 时可以找到。

* **&lt;API_KEY>**：您的个人 API 密钥。在将创建与 [!DNL Journey Orchestration] 服务的新集成后，可在 Adobe I/O 中找到。



## Export-Import API描述

通过此API，可导出由其UID标识的历程版本以及所有相关对象（历程、事件、数据源、字段组、自定义操作）。
生成的有效负载可用于导入其他环境（沙盒或实例）中的历程版本。

| 方法 | 路径 | 描述 |
|---|---|---|
| `[POST]` | /journeyVersions/import | 导入由历程版本导出生成的历程版本内容 |
| `[GET]` | /journeyVersions/`{uid}`/export | 导出历程版本 |
| `[GET]` | /journeys/`{uid}`/latest | 获取历程的最新历程版本 |
| `[POST]` | /list/journey | 列出历程的元数据及其历程版本 |


### 导出特征和护栏

* 导出前历程必须有效。

* 不会导出凭据，并且响应有效负载中会插入占位符（即INSERT_SECRET_HERE）。
在导出调用后，必须先手动插入新凭据（对应于目标环境），然后才能在目标环境中导入有效负载。

* 将导出以下对象，但绝不会在目标环境中导入它们。 这些是由Journey Orchestration自动管理的系统资源。 您无需替换“INSERT_SECRET_HERE”。
   * **DataProviders**：“Adobe Campaign Standard数据提供程序”(acsDataProvider)和“Experience Platform”(acppsDataProvider)
   * **字段组** (dataEntities)：“ProfileFieldGroup”(acppsDataPack)



### 导入特征

* 在导入期间，将使用新UID和新名称创建历程对象，以确保在目标环境（实例或沙盒）中的唯一性。

* 如果导入有效负载包含密钥占位符，则会引发错误。 您必须在POST调用导入旅程之前替换凭据信息。

## 警告和错误

潜在的错误包括：

* 在 **导出时间**，如果历程版本无效：错误500

* 在 **导入时间**，如果有效负载在修改后无效，或者如果在有效负载中未正确定义凭据：错误400

* 在导入步骤之后，如果事件的XDM架构ID在Journey Orchestration环境中无效，则目标应用程序中会显示错误。 在这种情况下，将无法发布历程。