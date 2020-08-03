---
title: 访问管理
description: 了解有关访问管理的更多信息
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: 5a480ba736b642485f2078a6e6c40c28a11f38a3
workflow-type: tm+mt
source-wordcount: '845'
ht-degree: 5%

---


# 访问管理{#concept_rfj_wpt_52b}

## 关于访问管理 {#about-access-management}

[!DNL Journey Orchestration] 允许您为用户分配一组权限，以定义他们可以访问的界面部分。

可由有权访问管理控制台的管理员管理。 有关管理控制台的更多信息，请参阅此[文档](https://helpx.adobe.com/cn/enterprise/managing/user-guide.html)。

要能够访问， [!DNL Journey Orchestration]用户必须：

* 与权限关 [!DNL Journey Orchestration] 联 **[!UICONTROL product profile]** 的一 [!DNL Journey Orchestration] 部分。
* 属于某个 [!DNL Adobe Experience Platform]**[!UICONTROL product profile]**。 没有强制许可。 用户应具有 **[!UICONTROL profile management]** 从界面创建和编辑平台段的权 [!DNL Journey Orchestration] 限。 有关更多信息，请参见此[页面](https://docs.adobe.com/content/help/en/experience-platform/access-control/home.html#adobe-admin-console)。

在管理控制台中，您可以向用户分配以下现成的产品用户档案之一：

* **[!UICONTROL Limited Access User]**: 具有对旅程和报告的只读访问权限的用户。 此产品用户档案包括以下权限：
   * 阅读旅程
   * 阅读报告

* **[!UICONTROL Administrators]**: 用户可访问管理菜单，并可以管理旅程、事件和报告。 此产品用户档案包括以下权限：
   * 管理旅程
   * 发布旅程
   * 管理事件、数据源和操作
   * 管理报告

   >[!NOTE]
   >
   >**[!UICONTROL Administrators]** 是唯一允许在Adobe Campaign Standard中创建、编辑和发布交易消息（或消息模板）的产品用户档案。 如果您使用用户档案在旅程中发送消息，则需要此产品Adobe Campaign Standard。

* **[!UICONTROL Standard User]**: 具有基本访问权限的用户，如旅程管理。 此产品用户档案包括以下权限：
   * 管理旅程
   * 发布旅程
   * 管理报告

如果现成的用户档案不足以管理用户，您还可以创建自己的产品用户档案。
用户必须始终链接到产品用户档案，以便您为他们分配特定的内置权限，例如：

* **[!UICONTROL Read journeys]**
* **[!UICONTROL Read reports]**
* **[!UICONTROL Manage events, data sources and actions]**
* **[!UICONTROL Read events, data sources and actions]**
* **[!UICONTROL Manage journeys]**
* **[!UICONTROL Publish journeys]**
* **[!UICONTROL Manage reports]**

您可以在下面找到权限与不同功 [!DNL Journey Orchestration]能之间的兼容性。

![](../assets/do-not-localize/journey_permission.png)

## 创建产品用户档案 {#create-product-profile}

[!DNL Journey Orchestration] 允许您创建自己的产品用户档案，并为用户分配一组权限和沙箱。 通过产品用户档案，您可以授权或拒绝对界面中特定功能或对象的访问。

有关如何创建和管理沙箱的更多信息，请参阅 [Adobe Experience Platform文档](https://docs.adobe.com/content/help/en/experience-platform/sandbox/ui/user-guide.html)。

要创建产品用户档案并分配一组权限和沙箱，请执行以下操作：

1. 在Admin Console中，选择 **[!UICONTROL Journey Orchestration]**。 From the **[!UICONTROL Product profile]** tab, click **[!UICONTROL New Profile]**.

   ![](../assets/do-not-localize/user_management_5.png)

1. 为新 **[!UICONTROL Profile Name]** 产品 **[!UICONTROL Description]** 用户档案添加和。 如果希望用户档案不 **[!UICONTROL Display name]** 同，请取消选 **[!UICONTROL Same as Profile Name]** 中并键入 **[!UICONTROL Display name]**。

1. 在类别 **[!UICONTROL User Notifications]** 中，选择在添加用户或从此产品用户档案中删除用户时，是否会通过电子邮件通知用户。

1. 完成后，单击 **[!UICONTROL Done]**。 您的新产品用户档案现已创建。

   ![](../assets/do-not-localize/user_management_1.png)

1. 选择您的新产品用户档案以开始管理权限。 在选项卡 **[!UICONTROL Users]** 中，将用户添加到您的产品用户档案。 有关更多信息，请参见此[页面](../about/access-management.md#assigning-product-profile)。

1. 执行与上述步骤相同的步骤，以添 **[!UICONTROL Admin]** 加到您的产品用户档案。

1. 从选 **[!UICONTROL Permissions]** 项卡中，选择两个类别之一 **[!UICONTROL Sandbox]** ，或 **[!UICONTROL Authoring]** 者打开页面并添 **[!UICONTROL Edit Permissions]** 加或删除您的产品用户档案的权限。

   ![](../assets/do-not-localize/user_management_7.png)

1. 在权 **[!UICONTROL Sandboxes]** 限类别中，选择要分配给产品用户档案的沙箱。 在 **[!UICONTROL Available Permissions Items]**&#x200B;下，单击加号(+)图标，将沙箱分配给用户档案。 For more information on sandboxes, refer to this [section](../about/access-management.md#sandboxes).

   ![](../assets/do-not-localize/user_management_8.png)

1. 如果需要，请在 **[!UICONTROL Included Permission Items]**&#x200B;下面单击删除您的产品用户档案权限旁边的X图标。

   ![](../assets/do-not-localize/user_management_9.png)

1. 在权 **[!UICONTROL Authoring]** 限类别中，执行与上述步骤相同的步骤，向产品用户档案添加权限。
   <br>有关权限与权限之间的兼容性以及 [!DNL Journey Orchestration]不同功能的更多信息，请参 [阅本节](../about/access-management.md#about-access-management)。

   ![](../assets/do-not-localize/user_management_10.png)

1. 完成后，单击 **[!UICONTROL Save]**。

您的产品用户档案现已创建并配置。 链接到此用户档案的用户现在可以连接到 [!DNL Journey Orchestration]。

## 分配产品用户档案 {#assigning-product-profile}

产品用户档案会分配给您组织内共享相同权限的一组用户。
本部分提供每个现成产品用户档案的列表，这些已分配权限。

要为用户分配产品用户档案以进行访问，请执行以下操 [!DNL Journey Orchestration]作：

1. 在Admin Console中，选择 **[!UICONTROL Journey Orchestration]**。

   ![](../assets/do-not-localize/user_management.png)

1. 选择新用户将链接到的产品用户档案。

   ![](../assets/do-not-localize/user_management_2.png)

1. 单击 **[!UICONTROL Add user]**。

   您还可以将新用户添加到用户组以微调共享的权限集。 有关更多信息，请参见此[页面](https://helpx.adobe.com/enterprise/using/user-groups.html)。

   ![](../assets/do-not-localize/user_management_3.png)

1. 键入新用户的电子邮件地址，然后单击 **[!UICONTROL Save]**。

   ![](../assets/do-not-localize/user_management_4.png)

随后，您的用户将收到一封重定向到您的实例的 [!DNL Journey Orchestration] 电子邮件。

## 使用沙箱 {#sandboxes}

[!DNL Journey Orchestration] 允许您将实例分区为称为沙箱的分隔虚拟环境。
沙箱通过管理控制台中的产品用户档案进行分配。 For more information on how to assign sandboxes, refer to this [section](../about/access-management.md#create-product-profile).

[!DNL Journey Orchestration] 反映为给定组织创建的Adobe Experience Platform沙箱。
Adobe Experience Platform沙箱可以从Adobe Experience Platform实例创建或重置。 有关详细步 [骤，请参阅](https://docs.adobe.com/content/help/en/experience-platform/sandbox/ui/user-guide.html) “沙箱用户指南”。

您可以在屏幕左上角找到沙箱切换器控件。 要从一个沙箱切换到另一个沙箱，请单击切换器中当前活动的沙箱，然后从下拉列表中选择另一个沙箱。
