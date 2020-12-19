---
product: adobe campaign
solution: Journey Orchestration
title: 导入导出API说明
description: 进一步了解导入导出API。
products: journeys
translation-type: tm+mt
source-git-commit: 8da1d4a6c01279bf502c3ec39bdaba8fcc8e64f8
workflow-type: tm+mt
source-wordcount: '1131'
ht-degree: 2%

---


# 使用Export-Import API

通过单个API调用导出旅程版本及其所有相关对象(旅程、事件、数据源、字段组、自定义操作)。 导出生成的有效负荷可用于轻松将旅程导入另一个环境（实例或沙箱）。
此功能允许您跨多个实例或针对多个测试环境工作流管理您的旅程。


## 资源

在[此处](https://adobedocs.github.io/JourneyAPI/docs/)提供的Swagger文件中介绍Journey Orchestration导出——导入API。

要将此API与您的Journey Orchestration实例一起使用，您需要使用AdobeI/O控制台。 您可以按照此[Adobe开发者控制台快速入门](https://www.adobe.io/apis/experienceplatform/console/docs.html#!AdobeDocs/adobeio-console/master/getting-started.md)进行开始，然后使用本页中的各节。

要测试和准备集成，[此处](https://raw.githubusercontent.com/AdobeDocs/JourneyAPI/master/postman-collections/Journey-Orchestration_Export-import-API_postman-collection.json)提供Postman集合。


## 导出——导入流

我们建议按照以下步骤在环境中导出和导入您的旅程：

1. 在开始环境中创建旅程并为其添加参数。 [此处了解更多信息](https://docs.adobe.com/content/help/zh-Hans/journeys/using/building-journeys/about-journey-building/journey.html)
1. 检查旅程版本是否没有错误。 [此处了解更多信息](https://docs.adobe.com/content/help/en/journeys/using/building-journeys/testing-the-journey.html)
1. 调用&#x200B;**/列表/journeys** API以检索最新旅程版本的UID旅程和UID。 如果需要，可以调用&#x200B;**/journeys/`{uid}`/latest**&#x200B;来查找最新旅程版本的UID。
1. 使用您的开始环境参数（orgID和sandboxName）调用&#x200B;**export** API。
1. 打开返回有效负荷，然后检查以下项目：
   * 如果导出的旅程包含&#x200B;**特定凭据**，则需要将这些凭据替换为与新环境对应的凭据。
   * 如果导出的旅程包含指向&#x200B;**XDM事件**&#x200B;的&#x200B;**模式**，则需要手动更新模式ID引用，如果ID值不同，则使用xdmEntity节点中新环境的模式ID进行更新。 此更新需要针对每个事件完成。 [此处了解更多信息](https://docs.adobe.com/content/help/en/journeys/using/events-journeys/experience-event-schema.html)
   * 如果您的旅程包含电子邮件、短信或推送操作，则如果目标环境中的名称与开始环境中的名称不同，则可能必须更新模板名称或mobileApp名称。
1. 使用您的目标环境参数（orgID和sandboxName）调用&#x200B;**Import** API。 请注意，您可以根据需要多次调用导入API。 每次调用导入API时，都会生成旅程中包含的每个对象的UUID和名称。
1. 导入旅程后，您可以在Journey Orchestration应用程序中发布它。 更多信息[此处](https://docs.adobe.com/content/help/en/journeys/using/building-journeys/publishing-the-journey.html)


## 身份验证

### 设置 API 访问

Journey OrchestrationAPI访问权限通过以下步骤设置。 每个步骤详见[Adobe I/O文档](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)。

>[!CAUTION]
>
>要管理Adobe I/O的证书，请确保您对组织具有<b>系统管理员</b>权限，或在管理控制台中具有[开发人员帐户](https://helpx.adobe.com/enterprise/using/manage-developers.html)权限。

1. **检查您有数字证书**，或根据需要创建数字证书。在以下步骤中需要随证书提供的公钥和私钥。
1. **创建与Adobe I/O服务的 [!DNL Journey Orchestration]** 新集成并进行配置。Journey Orchestration和Adobe Experience Platform需要产品用户档案访问。 随后将生成您的凭据（API密钥、客户端机密……）。
1. **从先前生成的凭据创** 建JSON Web令牌(JWT)，并用私钥对其进行签名。JWT对Adobe验证您的身份并授予您对API的访问权限时所需的所有身份和安全信息进行编码。 此步骤详见此[部分](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md)
1. **通过POST请求或** 通过开发人员控制台界面将JWT交换为访问令牌。此访问令牌必须用于API请求的每个头中。

要建立安全的服务到服务Adobe I/OAPI会话，对Adobe服务的每个请求都必须在授权标头中包含以下信息。

```
curl -X GET https://journey.adobe.io/authoring/XXX \
 -H 'Authorization: Bearer <ACCESS_TOKEN>' \
 -H 'x-api-key: <API_KEY>' \
 -H 'x-gw-ims-org-id: <ORGANIZATION>'
```

* **&lt;organization>**:这是您的个人组织ID,Adobe为每个实例提供一个组织ID:

   * &lt;organization> :您的生产实例
   要获取您的组织ID值，请咨询您的管理员或Adobe技术联系人。 在许可证列表中创建新集成时，您还可以将其检索到Adobe I/O(请参阅[Adobe I/O文档](https://www.adobe.io/authentication.html))。

* **&lt;access_token>**:您的个人访问令牌，通过POST请求交换JWT时检索到。

* **&lt;api_key>**:您的个人API密钥。它在Adobe I/O创建到[!DNL Journey Orchestration]服务的新集成后提供。



## 导出——导入API说明

通过此API，可以导出由其UID标识的旅程版本，以及所有相关对象(旅程、事件、数据源、字段组、自定义操作)的uid。
生成的有效负荷可用于在其他环境（沙箱或实例）中导入旅程版本。

| 方法 | 路径 | 说明 |
|---|---|---|
| `[POST]` | /journeyVersions/import | 导入旅程版本导出生成的旅程版本内容 |
| `[GET]` | /journeyVersions/`{uid}`/export | 导出旅程版本 |
| `[GET]` | /journeys/`{uid}`/latest | 获取旅程的最新旅程版本 |
| `[POST]` | /列表/旅程 | 列表旅程的元数据及其旅程版本 |


### 出口特点与护栏

* 出口前，该旅程必须有效。

* 不导出凭据，并在响应有效负荷中插入占位符（即INSERT_SECRET_HERE）。
在导出调用后，您必须手动插入新凭据(与目标环境对应)，然后才能将有效负荷导入目标环境。

* 以下对象将导出，但永远不会在目标环境中导入。 这些是由Journey Orchestration自动管理的系统资源。 您无需替换“INSERT_SECRET_HERE”。
   * **数据提供者**:“Adobe Campaign Standard数据提供者”(acsDataProvider)和“Experience Platform”(acppsDataProvider)
   * **字段组** (dataEntities):“ProfileFieldGroup”(acpsDataPack)



### 导入特性

* 在导入过程中，将使用新的UID和新名称创建旅程对象，以确保目标环境（实例或沙箱）中的唯一性。

* 如果导入有效负荷包含机密占位符，则会引发错误。 您必须在POST调用前替换凭据信息才能导入旅程。

## 警告和错误

潜在错误有：

* 在&#x200B;**导出时间**，如果旅程版本无效：错误500

* 在&#x200B;**导入时间**，如果负载在修改后无效，或者凭据在负载中未正确定义：错误400

* 在导入步骤后，如果模式的XDM事件ID在目标环境中无效，则Journey Orchestration应用程序中会显示错误。 在这种情况下，无法发布旅程。