---
title: 发行说明
description: 了解发行说明
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: ht
source-git-commit: 66e4acb339e9190cf2877c0ab1824ca5f41c8a6d
workflow-type: ht
source-wordcount: '758'
ht-degree: 100%

---


# 发行说明 {#release-notes}

此页面列出了 Journey Orchestration 的所有新功能和改进。
您还可以参阅[文档更新](../release-notes/documentation-updates.md)。

## 第 1 季度发行 - 2020 年 3 月{#q1-release---march-2020}

**新增内容?**

<table>
<thead>
<tr>
<th><strong>测试模式增强功能</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>测试模式已进行了以下增强功能：</p>
<ul>
<li>当旅程使用多个事件时，您现在可以从测试模式的<strong>事件配置</strong>屏幕中的下拉列表单独触发每个事件。<a href="../building-journeys/testing-the-journey.md#firing_events">阅读更多</a></p></li>
<li><p>当在旅程中使用一个或多个<strong>等待</strong>活动时，您现在可以定义每个活动在测试模式下的停留时间。默认时间为 10 秒。可以使用左下角的<strong>测试中的等待时间</strong>参数更改此设置。<a href="../building-journeys/testing-the-journey.md">阅读更多</a></p><img src="../assets/rn-test.png"/>
</li>
<li>在<strong>测试日志</strong>中，如果调用第三方系统（数据源或操作）时出错，则现在将显示错误代码和错误响应。<a href="../building-journeys/testing-the-journey.md#viewing_logs">阅读更多</a>
</li>
</ul>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>集中化时区管理</strong><br/></th>
</tr>
</thead>
<tbody>
<tr> 
<td>
<p>时区管理现在集中在旅程属性面板中。旅程属性中添加了两个参数：</p>
<img src="../assets/rn-timezone.png"/>
<ul>
<li><strong>时区</strong>下拉列表允许您选择特定时区。默认情况下，使用浏览器的时区。 </li>
<li>通过<strong>资料时区</strong>复选框，您可以使用进入旅程的人员的 Experience Platform 资料时区（如果可用）。如果不可用，则使用下拉列表中定义的时区。此功能与使用没有命名空间的事件的旅程不兼容。</li>
</ul>
<p>有关更多信息，请参阅<a href="../building-journeys/changing-properties.md#timezone">更改属性</a>和<a href="../building-journeys/timezone-management.md">时区管理</a>部分。</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>旅程设计器增强功能</strong><br/></th>
</tr>
</thead>
<tbody>
<tr> 
<td>
<p>旅程设计器左侧的旅程<strong>面板</strong>已得到增强：</p>
<ul>
<li>通过<strong>搜索</strong>栏旁的新图标，您可以隐藏或显示面板中不可用的元素，例如使用不同于您的旅程中使用的命名空间的事件。默认情况下，不可用项目处于隐藏状态。</li>
<li>使用<strong>搜索</strong>字段，会显示每个画布活动类别的结果数。</li>
<li>不同活动类别之间的导航已得到改进。</li>
</ul>
<p>在旅程设计器中，您可以检查您是否正在访问旅程的最新版本。此信息显示在版本号旁边。</p>
<p>在旅程<strong>画布</strong>中，当两个活动断开连接时，会显示一条警告消息。</p>
<img src="../assets/rn-canvas.png"/>
<p>有关详细信息，请参阅<a href="../building-journeys/using-the-journey-designer.md">详细文档</a>。</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>情景帮助</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>现在，可以跨不同的 Journey Orchestration 列表屏幕（旅程、事件、操作和数据源）提供情景帮助。通过此情景帮助，您可以查看当前功能的快速说明，并访问相关文章和视频。</p>
<p>要显示情景帮助，请单击屏幕右上角的 <img src="../assets/icon-context.png"/>图标。 </p>
<img src="../assets/rn-context.png"/>
</td>
</tr>
</tbody>
</table>

**其他改进**

* 除美国以外，Journeys Orchestration 也在&#x200B;**欧洲、中东和非洲地区**&#x200B;提供。应用程序和文档提供法语和德语两个版本。

* Experience League 现已集成到产品中。这简化了对相关内容的访问，并有助于您充分利用 Experience Cloud。直接访问“帮助”选项卡底部的 Journey Orchestration 文档。此外，单击“帮助”>“反馈”以报告问题或与 Adobe 分享您的想法。

* 现在，所有列表屏幕中都提供 **C** 键盘快捷键，它允许您创建新项目：旅程、数据源、操作和事件。[阅读更多](../about/user-interface.md#section_ksq_zr1_ffb)

* 您现在可以&#x200B;**删除**&#x200B;已停止的旅程。与这些已删除的旅程关联的报告将不可用。

* 浏览 **Data Platform 字段**（XDM 格式）时，除了字段名称外，您现在还会看到显示名称。此信息可从体验数据模型中的架构定义中检索。当可用时，将显示替代显示名称。此用户友好型描述（在 eVar 字段中尤为有用）使您能够更轻松地识别字段。[阅读更多](../about/user-interface.md#friendly-names-display)

## 正式全面发行 - 2019 年 12 月 {#ga-release---december-2019}

Journey Orchestration 现已正式全面发行。

利用存储在事件或数据源中的情境数据构建实时编排用例。

Journey Orchestration 允许由事件的情境数据、Adobe Experience Platform 信息或第三方 API 服务数据提供支持的实时编排。应用程序根据消费者的资料和行为确定在称为旅程的多步流中特定于消费者的下一个最佳操作。这包括最佳时间和操作类型，如通过 Adobe Campaign Standard 事务性消息传送功能（需要 Adobe Campaign Standard）向消费者发送推送通知或第三方系统通知。这些决策是根据规则和 Sensei 得分做出的。

[](../action/working-with-adobe-campaign.md)
详细了解 Journey Orchestration。

其他资源：

* [教程](https://docs.adobe.com/content/help/en/platform-learn/tutorials/journey-orchestration/introduction.html)
* [社区](https://www.adobe.com/go/journeyorchestrationcommunity)
