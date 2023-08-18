---
title: 升级到Adobe Journey Optimizer
description: 了解如何升级到Adobe Journey Optimizer
hide: true
hidefromtoc: true
exl-id: 887fd3bb-bcd3-4a6d-9817-43049c51ecba
source-git-commit: 3e9ff02cecfe85ea38cce4b0d241156f6209202f
workflow-type: tm+mt
source-wordcount: '753'
ht-degree: 2%

---

# 将Journey Orchestration环境升级到Adobe Journey Optimizer{#ugrade-ajo}

## 什么是Adobe Journey Optimizer？

Adobe Journey Optimizer是一款灵活的、可扩展的应用程序，它原生构建于Adobe Experience Platform上，可在任何应用程序、设备、屏幕或渠道中编排和提供个性化、连接且及时的客户历程&#x200B;。

## Journey Orchestration 是什么？

Journey Orchestration是一项基于Adobe Experience Platform构建的服务，允许您根据每位客户先前的行为和偏好为其定制各个历程。 Journey Orchestration是Journey Optimizer的前沿应用。

## 为何要迁移到Adobe Journey Optimizer？

**访问简化的界面** 通过Experience Platform功能，可快速访问历程、数据集、用户档案、警报等。 无需在Adobe Experience Platform和Journey Orchestration之间来回切换即可访问架构或数据集，所有内容均可直接从Adobe Journey Optimizer获得。 有关更多信息，请参阅此 [页面](https://experienceleague.adobe.com/docs/journey-optimizer/using/get-started/user-interface.html).

<table>
<tr>
<th>之前</th>
<th>之后</th>
</tr>
<tr>
<td><img src="../assets/migration-ajo-1.png"><p>访问Journey Orchestration中的历程、区段和管理员部分（数据源、事件和操作）。 可在Adobe Experience Platform中访问区段和数据集。 </p></td>
<td><img src="../assets/migration-ajo-2.png"><p>对历程、区段、管理员、区段和数据集的访问权限， <strong>Adobe Journey Optimizer中的所有组件</strong>. <strong>其他Adobe Experience Platform功能</strong> 也可在此处访问。</p></td>
</tr>
</table>

**新的报表界面** 以及访问新的报表功能：

<table>
<tr>
<th>之前</th>
<th>之后</th>
</tr>
<tr>
<td><img src="../assets/migration-ajo-5.png"></td>
<td><img src="../assets/migration-ajo-6.png"><p><strong>全局视图</strong> 用于衡量所选时段内历程和投放的影响。 要获得更多实时指标，您可以访问 <strong>实时视图</strong>. 对于您的历程中使用的每个投放渠道（电子邮件、短信、推送），应 <strong>专用部分</strong> 可用于查看指标。 仅当您使用现成可用时，才适用 <strong>Adobe Journey Optimizer消息传送功能</strong>. 请联系您的帐户团队以了解更多信息。</p></td>
</tr>
</table>

改进报告体验或在发布新功能后丰富报告体验的任何演变，都只能在新的报告界面上使用。 开始使用它以获取更全面的Adobe Journey Optimizer体验。

获取其他当前活动的收益 **Adobe Journey Optimizer功能** 以及即将推出的新功能，如字段级访问控制和对象级访问控制。 请联系您的帐户团队以获取更多信息。

## 如何升级Journey Orchestration环境？

1. 请联系您的客户团队以更新您与Adobe的协议。

1. 等待我们的工程团队完成更改。

1. 使用Journey Optimizer的产品配置文件更新您的权限。 请参阅此 [页面](https://experienceleague.adobe.com/docs/journey-optimizer/using/administration/ootb-product-profiles.html?lang=zh-Hans).

1. 您现在可以访问Adobe Journey Optimizer了！

## 常见问题

### 是否需要规划从Journey Orchestration迁移到Adobe Journey Optimizer的任何内容？

不需要，无需迁移，无需您进行任何工作，无需停机，无需额外投资。 您只需更新与Adobe的协议，其余工作由我们来完成。 请联系您的客户代表，以获取有关如何启动此流程的说明。

### 更改后我会丢失一些内容吗？

不需要，您将保留所有现有Journey Orchestration和Adobe Experience Platform对象：架构、数据集、旅程、事件、数据源、操作。 任何内容都不会丢失，所有实时历程将继续正常运行，不会中断。

<table>
<tr>
<th>之前</th>
<th>之后</th>
</tr>
<tr>
<td><img src="../assets/migration-ajo-7.png"></td>
<td><img src="../assets/migration-ajo-8.png"></td>
</tr>
</table>

### 我仍会在应用程序切换器中看到Journey Orchestration，它是否正常？

![](../assets/migration-ajo-9.png)

是的，这是正常的。 升级后的几天内，您仍可能会看到Journey Orchestration项目。 请使用Journey Optimizer的。

### 如果我现在将Journey Orchestration与Adobe Campaign Standard结合使用，会发生什么？

迁移到Adobe Journey Optimizer后，您仍然能够使用历程与Adobe Campaign Standard之间的集成，方法是在Adobe Journey Optimizer中设计客户历程并让Adobe Campaign Standard发送投放。

但是，由于Adobe Journey Optimizer报表栈栈的工作方式，报表不会将历程数据和Campaign Standard数据结合使用。 历程信息可在Adobe Journey Optimizer报表中获取，投放信息可在Adobe Campaign Standard中获取。 可以进行Experience Platform配置以将Adobe Campaign Standard数据恢复到Adobe Experience Platform中，使其可供Customer Journey Analytics([了解详情](https://business.adobe.com/products/experience-platform/customer-journey-analytics.html))或其他第三方报表工具，例如Tableau或PowerBI。

Adobe Journey Optimizer报表在使用Adobe Journey Optimizer的现成消息传送功能时操作最佳(可在专门的Adobe Journey Optimizer产品中获取)。 有关如何在历程画布中创作消息的更多信息，请参阅此 [页面](https://experienceleague.adobe.com/docs/journey-optimizer/using/messages/messages-in-journeys.html).

请联系您的帐户团队以了解更多信息。
