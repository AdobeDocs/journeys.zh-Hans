---
title: 导入导出API说明
description: 进一步了解导入导出API。
contentOwner: sauviat
products: journeys
audience: audiences
content-type: reference
topic-tags: journeys
translation-type: tm+mt
source-git-commit: b852c08a488a1bec02b8b31a1fccf1a8773b99af
workflow-type: tm+mt
source-wordcount: '1103'
ht-degree: 2%

---


# 使用导出导入API

通过单个API调用导出旅程版本及其所有相关对象(旅程、事件、数据源、字段组、自定义操作)。 导出生成的有效负荷可用于轻松将旅程导入另一个环境（实例或沙箱）。
此功能允许您跨多个实例或针对多个测试环境工作流管理您的旅程。


## 资源

Journey Orchestration导入导出API在此处提供的Swagger文件中有 [说明](https://adobedocs.github.io/JourneyAPI/docs/)。

要将此API与您的Journey Orchestration实例一起使用，您需要使用AdobeI/O控制台。 您可以通过以下方式进行 [开始：开始使用Adobe开](https://www.adobe.io/apis/experienceplatform/console/docs.html#!AdobeDocs/adobeio-console/master/getting-started.md) 发人员控制台，然后使用本页中的各个部分。

要测试和准备集成，此处提供邮递员 [集合](https://raw.githubusercontent.com/AdobeDocs/JourneyAPI/master/postman-collections/Journey-Orchestration_Export-import-API_postman-collection.json)。


## 导出——导入流

我们建议按照以下步骤在环境中导出和导入您的旅程：

1. 在开始环境中创建旅程并为其添加参数。 [此处了解更多信息](https://docs.adobe.com/content/help/zh-Hans/journeys/using/building-journeys/about-journey-building/journey.html)
1. 检查旅程版本是否没有错误。 [此处了解更多信息](https://docs.adobe.com/content/help/en/journeys/using/building-journeys/testing-the-journey.html)
1. 调 **用/列表** /journeys API以检索最新旅程版本的UID旅程和UID。 如果需要，您可 **以调用/`{uid}`journeys/** /latest，以查找最新旅程版本的UID。
1. 使用您的 **开始** 环境参数（orgID和sandboxName）调用导出API。
1. 打开返回有效负荷，然后检查以下项目：
   * 如果导出的旅程包 **含特定凭据**，则需要将这些凭据替换为与新环境对应的凭据。
   * 如果导出的旅程 **包含指** 向XDM模式的 **事件**，则需要手动更新模式ID引用，如果ID值不同，则需要使用xdmEntity节点中新环境的模式ID来更新ID引用。 此更新需要针对每个事件完成。 [此处了解更多信息](https://docs.adobe.com/content/help/en/journeys/using/events-journeys/experience-event-schema.html)
   * 如果您的旅程包含电子邮件、短信或推送操作，则如果目标环境中的名称与开始环境中的名称不同，则可能必须更新模板名称或mobileApp名称。
1. 使用您的 **目标** 环境调用导入API。 请注意，您可以根据需要多次调用导入API。 每次调用导入API时，都会生成旅程中包含的UUID和每个节点的名称。
1. 导入“旅程”后，您可以在新的沙箱或环境中发布它。


## 身份验证

### 设置 API 访问

Journey OrchestrationAPI访问权限通过以下步骤设置。 这些步骤均详见 [AdobeI/O文档](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)。

>[!CAUTION]
>
>要在AdobeI/O中管理证书，请确保您对组织 <b>或Admin Console中的</b> System Administrator [权限](https://helpx.adobe.com/enterprise/using/manage-developers.html) ，或者拥有Developer帐户。

1. **检查您有数字证书**，或根据需要创建数字证书。 在以下步骤中需要随证书提供的公钥和私钥。
1. **在AdobeI/O中创[!DNL Journey Orchestration]建与** Service的新集成并进行配置。 Journey Orchestration和Adobe Experience Platform需要产品用户档案访问。 随后将生成您的凭据（API密钥、客户端机密……）。
1. **从先前生成的凭据创建JSON Web** Token(JWT)，然后使用您的私钥对其进行签名。 JWT对Adobe验证您的身份并授予您对API的访问权限时所需的所有身份和安全信息进行编码。 此步骤详见本 [节](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md)
1. **通过访问令牌请求或通过** “开发人员控制台界面”将JWT交换为POST。 此访问令牌必须用于API请求的每个头中。

要建立安全的服务到服务AdobeI/O API会话，对Adobe服务的每个请求都必须在授权标头中包含以下信息。

```
curl -X GET https://journey.adobe.io/authoring/XXX \
 -H 'Authorization: Bearer <ACCESS_TOKEN>' \
 -H 'x-api-key: <API_KEY>' \
 -H 'x-gw-ims-org-id: <ORGANIZATION>'
```

* **&lt;组织>**:这是您的个人组织ID,Adobe为每个实例提供一个组织ID:

   * &lt;组织>:您的生产实例
   要获取您的组织ID值，请咨询您的管理员或Adobe技术联系人。 创建新集成时，您还可以在许可证列表中将其检索到AdobeI/O中(请参阅 [AdobeI/O文档](https://www.adobe.io/authentication.html))。

* **&lt;ACCESS_TOKEN>**:您的个人访问令牌，通过POST请求交换JWT时检索到。

* **&lt;API_KEY>**:您的个人API密钥。 它在创建与服务的新集成后在AdobeI/O中提 [!DNL Journey Orchestration] 供。



## 导出导入API说明

此API允许您按其uid导出旅程版本和所有相关对象(旅程、事件、数据源、字段组、自定义操作)。
生成的有效负荷可用于在其他环境（沙箱或实例）中导入旅程版本。

| 方法 | 路径 | 说明 |
|---|---|---|
| `[POST]` | /journeyVersions/import | 导入旅程版本导出生成的旅程版本内容 |
| `[GET]` | /journeyVersions/`{uid}`/export | 导出旅程版本 |
| `[GET]` | /journeys/`{uid}`latest | 获取旅程的最新旅程版本 |
| `[POST]` | /列表/旅程 | 列表旅程的元数据及其旅程版本 |


### 出口特点与护栏

* 不导出凭据，并插入占位符（即INSERT_SECRET_HERE）。
在导出有效负荷后，您必须手动插入新凭据(与目标环境相对应)，然后才能将有效负荷导入目标环境。

* 当数据源包含 **参数builtIn:true**，您无需替换“INSERT_SECRET_HERE”。 这是由旅程环境自动管理的系统数据源。

* 以下对象将导出，但永远不会在目标环境中导入：
   * **数据提供者**: acsDataProvider和acppsDataProvider
   * **字段组**:acppsFieldGroup
   * **自定义操作**:acsAction

* 出口前，该旅程必须有效。

### 导入特性

* 在导入过程中，将使用新的UUID和新名称创建旅程对象，以确保目标环境（实例或沙箱）中的唯一性。

* 如果导入有效负荷包含机密占位符，则会引发错误。 您必须在POST调用前替换凭据信息才能导入旅程。

## 警告和错误

潜在错误有：

* 在 **导出时**，如果旅程版本无效：错误500

* 在导 **入时**，如果修改后有效负荷无效，或者有效负荷中未正确定义凭据：错误400

* 在导入步骤后，如果尝试在目标环境中发布旅程，而不更改事件的XDM模式ID，则会显示错误。

