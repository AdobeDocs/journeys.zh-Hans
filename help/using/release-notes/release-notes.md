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
translation-type: tm+mt
source-git-commit: 66e4acb339e9190cf2877c0ab1824ca5f41c8a6d

---


# 发行说明 {#release-notes}

本页列表了旅程编排的所有新增功能和改进。
您还可以查阅文档 [更新](../release-notes/documentation-updates.md)。

## 第一季度发布- 2020年3月 {#q1-release---march-2020}

**新增内容?**

<table>
<thead>
<tr>
<th><strong>测试模式增强</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>测试模式已进行了以下增强：</p>
<ul>
<li>当旅程使用多个事件时，您现在可以在测试模式的列表配置屏幕中，从下拉事件单独触发每个 <strong></strong> 。 <a href="../building-journeys/testing-the-journey.md#firing_events">阅读更多</a></p></li>
<li><p>当在旅程中使 <strong>用一个或多个等待活动</strong> ，您现在可以定义每个活动在测试模式下的持续时间。 默认时间为10秒。 可以使用左下角 <strong>的“Wait time in test</strong> （在测试中等待时间）”参数更改此设置。 <a href="../building-journeys/testing-the-journey.md">阅读更多</a></p><img src="../assets/rn-test.png"/>
</li>
<li>在测 <strong>试日志中</strong>，如果调用第三方系统（数据源或操作）时出错，现在将显示错误代码和错误响应。 <a href="../building-journeys/testing-the-journey.md#viewing_logs">阅读更多</a>
</li>
</ul>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>集中时区管理</strong><br/></th>
</tr>
</thead>
<tbody>
<tr> 
<td>
<p>时区管理现在集中在旅程属性面板中。 在旅程属性中添加了两个参数：</p>
<img src="../assets/rn-timezone.png"/>
<ul>
<li>时 <strong>区列表</strong> ，允许您选择特定时区。 默认情况下，使用浏览器的时区。 </li>
<li>通 <strong>过用户档案时区</strong> ，您可以使用进入旅程的人员的Experience Platform用户档案时区（如果有）。 否则，将使用下拉列表中定义的时区。 此功能与使用没有命名空间的事件的旅程不兼容。</li>
</ul>
<p>有关详细信息，请参阅更改 <a href="../building-journeys/changing-properties.md#timezone">属性</a> 和时 <a href="../building-journeys/timezone-management.md">区管理部分</a> 。</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>旅程设计人员增强功能</strong><br/></th>
</tr>
</thead>
<tbody>
<tr> 
<td>
<p>旅程 <strong>设计人员左侧的旅程调色板</strong>，已得到增强：</p>
<ul>
<li>“搜索”栏旁的新图标允许您隐藏或显示调色板中不可用的元素，例如，使用与旅程中使用的事件不同的命名空间的。 <strong></strong> 默认情况下，不可用的项目是隐藏的。</li>
<li>使用“搜 <strong>索</strong> ”字段时，现在会显示每个画布活动类别的结果数。</li>
<li>改进了不同活动类别之间的导航。</li>
</ul>
<p>在旅程设计器中，您现在可以检查您是否正在访问旅程的最新版本。 此信息显示在版本号旁边。</p>
<p>在旅程画 <strong>布中</strong>，当两个活动断开连接时，现在会显示一条警告消息。</p>
<img src="../assets/rn-canvas.png"/>
<p>有关详细信息，请参阅详 <a href="../building-journeys/using-the-journey-designer.md">细文档</a>。</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>上下文帮助</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>现在，跨不同的旅程编排列表屏幕(旅程、事件、操作和数据源)提供上下文帮助。 这允许您视图当前功能的快速说明并访问相关文章和视频。</p>
<p>要显示上下文帮助，请 <img src="../assets/icon-context.png"/> 单击屏幕右上角的图标。 </p>
<img src="../assets/rn-context.png"/>
</td>
</tr>
</tbody>
</table>

**其他改进**

* 除了美国以外，Journeys Orchestration现在在 **EMEA提供**。 应用程序和文档提供法语和德语版。

* Experience League现已集成到产品中。 这简化了对相关内容的访问，并有助于您充分利用Experience Cloud。 直接访问“帮助”选项卡底部的“旅程安排”文档。 此外，单击“帮助”>“反馈”以报告问题或与Adobe共享您的想法。

* 现 **在所有列表屏幕中都提供C** 键盘快捷键，它允许您创建新项目：旅程、数据源、操作和事件。 [阅读更多](../about/user-interface.md#section_ksq_zr1_ffb)

* 您现在可以删 **除已停** 止的旅程。 与这些已删除的旅程关联的报告将不可用。

* 浏览“数 **据平台”字段** （XDM格式）时，除字段名称外，您现在还会看到显示名称。 此信息是从体验数据模型中的模式定义中检索的。 当可用时，将显示替代显示名称。 此用户友好型描述（在eVar字段的情况下尤其有用）允许您更轻松地识别字段。 [阅读更多](../about/user-interface.md#friendly-names-display)

## GA版本- 2019年12月 {#ga-release---december-2019}

旅程编排现已正式推出。

利用存储在事件或数据源中的情境数据构建实时编排使用案例。

旅程安排允许实时安排，由事件的情境数据、Adobe Experience Platform的信息或第三方API服务的数据提供支持。 应用程序根据消费者的用户档案和行为确定在称为旅程的多步骤流中特定于消费者的下一最佳操作。 这包括最佳时间和操作类型，例如通过Adobe Campaign标准事务消息传递功能(需要Adobe Campaign标准)向消费者发送推送通知或第三方系统的通知。 这些决定基于规则和Sensei得分。

[](../action/working-with-adobe-campaign.md)
详细了解 Journey Orchestration。

其他资源：

* [教程](https://docs.adobe.com/content/help/en/platform-learn/tutorials/journey-orchestration/introduction.html)
* [社区](https://www.adobe.com/go/journeyorchestrationcommunity)
