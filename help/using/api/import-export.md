---
product: adobe campaign
title: 导入导出API说明
description: 了解有关导入导出API的更多信息。
products: journeys
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '1131'
ht-degree: 2%

---


# 使用导出 — 导入API

通过单个API调用导出历程版本及其所有相关对象（历程、事件、数据源、字段组、自定义操作）。 导出生成的有效负载可用于轻松将历程导入其他环境（实例或沙盒）。
此功能允许您跨多个实例或针对多个测试环境工作流管理您的历程。


## 资源

在[此处](https://adobedocs.github.io/JourneyAPI/docs/)提供的Swagger文件中介绍了Journey Orchestration导出 — 导入API。

要将此API与您的Journey Orchestration实例一起使用，您需要使用AdobeI/O控制台。 您可以按照以下步骤开始操作：[Adobe开发人员控制台快速入门](https://www.adobe.io/apis/experienceplatform/console/docs.html#!AdobeDocs/adobeio-console/master/getting-started.md) ，然后使用本页中的部分。

要测试和准备集成，[此处](https://raw.githubusercontent.com/AdobeDocs/JourneyAPI/master/postman-collections/Journey-Orchestration_Export-import-API_postman-collection.json)提供了Postman集合。


## 导出 — 导入流程

我们建议按照以下步骤来跨环境导出和导入您的历程：

1. 在开始环境中创建并参数化历程。 [此处提供更多信息](https://docs.adobe.com/content/help/zh-Hans/journeys/using/building-journeys/about-journey-building/journey.html)
1. 检查历程版本是否没有错误。 [此处提供更多信息](https://docs.adobe.com/content/help/en/journeys/using/building-journeys/testing-the-journey.html)
1. 调用&#x200B;**/list/journeys** API以检索最新历程版本的UID历程和UID。 如果需要，您可以调用&#x200B;**/journeys/`{uid}`/latest**&#x200B;以查找最新历程版本的UID。
1. 使用启动环境参数（orgID和sandboxName）调用&#x200B;**export** API。
1. 打开返回有效负载，然后检查以下项目：
   * 如果导出的历程包含&#x200B;**特定凭据**，则需要将这些凭据替换为与新环境对应的凭据。
   * 如果导出的历程包含指向&#x200B;**XDM架构**&#x200B;的&#x200B;**事件**，则如果ID值不同，则需要使用xdmEntity节点中新环境的架构ID手动更新架构ID引用。 需要为每个事件完成此更新。 [此处提供更多信息](https://docs.adobe.com/content/help/en/journeys/using/events-journeys/experience-event-schema.html)
   * 如果您的历程包含电子邮件、短信或推送操作，那么如果目标环境中的名称与开始环境中的名称不同，则您可能需要更新模板名称或mobileApp名称。
1. 使用您的目标环境参数（orgID和sandboxName）调用&#x200B;**Import** API。 请注意，您可以根据需要多次调用导入API。 每次调用导入API时，都会生成历程中包含的每个对象的UUID和名称。
1. 导入历程后，即可在Journey Orchestration应用程序中发布该数据。 更多信息[此处](https://docs.adobe.com/content/help/en/journeys/using/building-journeys/publishing-the-journey.html)


## 身份验证

### 设置 API 访问

Journey OrchestrationAPI访问权限通过以下步骤进行设置。 [Adobe I/O文档](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)中详细描述了每个步骤。

>[!CAUTION]
>
>要在Adobe I/O中管理证书，请确保您拥有组织的<b>系统管理员</b>权限，或在Admin Console中拥有[开发人员帐户](https://helpx.adobe.com/enterprise/using/manage-developers.html)权限。

1. **检查您是否拥有数字证书**，或根据需要创建一个证书。在以下步骤中需要随证书一起提供的公钥和私钥。
1. **在Adobe I/O中创建与服务 [!DNL Journey Orchestration]** 的新集成并对其进行配置。Journey Orchestration和Adobe Experience Platform需要产品配置文件访问权限。 随后将生成您的凭据（API密钥、客户端密钥……）。
1. **从之前生成的凭据创建JSON Web令牌(JWT)** ，然后使用您的私钥对其进行签名。JWT会对Adobe验证您的身份并授予您访问API的权限所需的所有身份和安全信息进行编码。 此[部分](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md)中详细介绍了此步骤
1. **通过POST请求或** 通过开发人员控制台界面交换JWT以进行访问令牌。此访问令牌必须用在API请求的每个标头中。

要建立安全的服务到服务Adobe I/OAPI会话，对Adobe服务的每个请求都必须在授权标头中包含以下信息。

```
curl -X GET https://journey.adobe.io/authoring/XXX \
 -H 'Authorization: Bearer <ACCESS_TOKEN>' \
 -H 'x-api-key: <API_KEY>' \
 -H 'x-gw-ims-org-id: <ORGANIZATION>'
```

* **&lt;organization>**:这是您的个人组织ID，Adobe会为您的每个实例提供一个组织ID:

   * &lt;organization> :您的生产实例
   要获取您的组织ID值，请咨询您的管理员或Adobe技术联系人。 创建新集成时，您还可以在许可证列表中将其检索到Adobe I/O中(请参阅[Adobe I/O文档](https://www.adobe.io/authentication.html))。

* **&lt;access_token>**:您的个人访问令牌，在通过POST请求交换JWT时检索。

* **&lt;api_key>**:您的个人API密钥。在创建[!DNL Journey Orchestration]服务的新集成后，该集成在Adobe I/O中提供。



## 导出 — 导入API说明

此API允许您导出通过其UID标识的历程版本，以及通过其UID导出所有相关对象（历程、事件、数据源、字段组、自定义操作）。
生成的有效负载可用于在其他环境（沙盒或实例）中导入历程版本。

| 方法 | 路径 | 说明 |
|---|---|---|
| `[POST]` | /journeyVersions/import | 导入由历程版本导出生成的历程版本内容 |
| `[GET]` | /journeyVersions/`{uid}`/export | 导出历程版本 |
| `[GET]` | /journeys/`{uid}`/latest | 获取历程的最新历程版本 |
| `[POST]` | /list/journeys | 列出历程的元数据及其历程版本 |


### 导出特性和护栏

* 导出之前，历程必须有效。

* 不会导出凭据，并在响应有效负载中插入占位符（即INSERT_SECRET_HERE）。
导出调用后，您必须先手动插入新凭据（对应于目标环境），然后才能在目标环境中导入有效负载。

* 以下对象将导出，但永远不会在目标环境中导入。 这些是由Journey Orchestration自动管理的系统资源。 您无需替换“INSERT_SECRET_HERE”。
   * **数据提供程序**:“Adobe Campaign Standard Data Provider”(acsDataProvider)和“Experience Platform”(acpsDataProvider)
   * **字段组** (dataEntities):&quot;ProfileFieldGroup&quot;(acpsDataPack)



### 导入特性

* 在导入过程中，使用新UID和新名称创建历程对象，以确保目标环境（实例或沙盒）中的唯一性。

* 如果导入有效负载包含密钥占位符，则会引发错误。 您必须在POST调用之前替换凭据信息才能导入历程。

## 警告和错误

潜在错误包括：

* 在&#x200B;**导出时间**，如果历程版本无效：错误500

* 在&#x200B;**导入时间**&#x200B;时，如果有效载荷在修改后无效，或者有效载荷中未正确定义凭据：错误400

* 在导入步骤之后，如果事件的XDM架构ID在目标环境中无效，则Journey Orchestration应用程序中会显示错误。 在这种情况下，将无法发布历程。