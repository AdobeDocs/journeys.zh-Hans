---
product: adobe campaign
solution: Journey Orchestration
title: 发行说明
description: 了解发行说明
translation-type: tm+mt
source-git-commit: 010bccb16d2b6980ff758e3922d3bc315706f61b
workflow-type: tm+mt
source-wordcount: '2026'
ht-degree: 78%

---


# 发行说明 {#release-notes}

此页面列出了 Journey Orchestration 的所有新功能和改进。
您还可以查阅最新的[文档更新](../release-notes/documentation-updates.md)。

## 2020年11月版本{#november-release}

<table>
<thead>
<tr>
<th><strong>从一个旅程跳到另一个旅程</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>新的操作活动允许您将个人从一个旅程推向另一个旅程。 <strong>跳转</strong>活动允许您：
</p>
<ul>
<li>将复杂旅程分成若干个，简化复杂旅程的设计 </li>
<li>基于通用、可重用的旅程模式构建旅程</li>
</ul>
<p>有关详细信息，请参阅<a href="../building-journeys/jump.md">详细文档</a>。</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>在表达式编辑器中使用旅程属性</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>在高级表达式编辑器中，我们在字段和函数的列表中新增了一个类别。 这是系统从实时旅程中检索到的信息，如旅程ID或遇到的特定错误。 这将为您在构建旅程时提供更多可能性。 例如，在条件或操作中遇到错误时，您将能够提醒第三方系统。
</p>
<p>有关详细信息，请参阅<a href="../expression/journey-properties.md">详细文档</a>。</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>基于规则的事件 （测试版）</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>现在有一种新方法可以更轻松地设置事件，而无需使用eventID:基于规则的事件会根据条件来评估是否应触发事件。 您仍可以使用现有方法，现在称为“系统生成”。 该功能已通过Alpha项目在有限的客户群中进行了测试，现在所有客户都可以使用Beta版。
</p>
<p>有关详细信息，请参阅<a href="../event/about-events.md">详细文档</a>。</p>
</td>
</tr>
</tbody>
</table>

### 其他改进{#october-november}

在创建旅程的新版本时增加了限制。 这些限制可避免在流程中做出过于剧烈的更改，以保持版本之间的一致性。 [阅读更多](../about/limitations.md#journey-versions-limitations)

**区段资格**&#x200B;活动不再能用于包含Campaign Standard消息活动的旅程。 此限制保护Adobe Campaign Standard实例的完整性。 事实上，细分资格的使用可能导致每日消息发送高峰，这会使Campaign Standard事务消息过载。 [阅读更多](../about/limitations.md#segment-qualification)

## 2020年10月版{#october-release}

<table>
<thead>
<tr>
<th><strong>事件超时</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>您现在可以为事件配置超时，以便仅在特定时间内让旅程侦听事件。 您不再需要添加与活动路径平行的等待事件来实现此目的。
</p>
<p>有关详细信息，请参阅<a href="../building-journeys/event-activities.md#listening-to-events-during-a-specific-time">详细文档</a>。</p>
</td>
</tr>
</tbody>
</table>

### 其他改进{#october-other}

* 当您发布旅程的新版本时，先前版本会自动结束并切换到“已关闭”状态。 [阅读更多](../building-journeys/journey-versions.md)

## 2020年9月版本{#september-release}

### GA 更新{#september-ga-update}

<table>
<thead>
<tr>
<th><strong>条件活动改进</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>在将条件添加到旅程时，您现在可以定义标签。 如果您在旅程中使用多个条件，这可以更轻松地识别它们。
</p>
<p>有关详细信息，请参阅<a href="../building-journeys/condition-activity.md#about_condition">详细文档</a>。</p>
</td>
</tr>
</tbody>
</table>

### Alpha 更新{#september-alpha-update}

要发现 Alpha 的范围，请参阅此[部分](../alpha/alpha-overview.md)。

<table>
<thead>
<tr>
<th><strong>阅读细分活动改进</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p><strong>读取段</strong>活动已进行以下改进：
</p>
<ul>
<li><p>基于区段的旅程现在在画布上方显示，提醒您旅程的计划类型。 您可以单击此提醒以访问计划配置菜单。</p>
</li>
<li><p>测试模式日志的粒度已得到改进，可显示段导出进度状态。</p>
</li>
</ul>
<p>有关<strong>读取段</strong>活动的详细信息，请参阅<a href="../alpha/alpha-segment-trigger.md">详细文档</a>。</p>
</td>
</tr>
</tbody>
</table>

## 2020 年 8 月版 {#august-release}

### GA 更新{#august-ga-update}

区段鉴别事件的有效负荷现在包含可以在条件和操作中使用的以下上下文信息：行为（进入、退出）、鉴别时间戳和区段 ID。[阅读更多](../building-journeys/segment-qualification-events.md)

### Alpha 更新{#august-alpha-update}

要发现 Alpha 的范围，请参阅此[部分](../alpha/alpha-overview.md)。

<table>
<thead>
<tr>
<th><strong>区段触发活动</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>已对“区段触发”活动进行以下改进：
</p>
<ul>
<li><p>活动的名称已更改为“读取区段”。 </p>
</li>
<li><p>已从活动的属性中删除旅程调度程序的配置。现在可直接从旅程的属性访问该活动，该活动位于在“读取区段”活动放入画布后将显示的专用部分中。 </p>
</li>
<li><p>您现在可以在单一用户档案上测试旅程，并使用视觉流跟踪其在旅程中的进度。</p>
</li>
</ul>
<p>有关详细信息，请参阅<a href="../alpha/alpha-segment-trigger.md">详细文档</a>。</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>基于规则的事件</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>已对基于规则的事件进行以下改进：
</p>
<ul>
<li><p>您现在可以利用已在捕获并流入到 Platform 中的所有 Adobe Analytics 行为事件数据，从而触发旅程并将客户的体验自动化。<a href="../event/about-analytics.md">阅读更多</a></p>
</li>
<li><p>在测试模式下触发基于规则的事件时，现在可以直接查看事件 ID 条件。此外，在规则评估中涉及的每个字段旁边都添加了工具提示。<a href="../building-journeys/testing-the-journey.md#test-rule-based">阅读更多</a></p>
</li>
<li><p>基于规则的事件定义屏幕已重新组织，以改善体验。<a href="../event/about-creating.md">阅读更多</a></p>
</li>
</ul>
</td>
</tr>
</tbody>
</table>

## Alpha 版本 - 2020 年 7 月 {#alpha-release---july-2020}

Alpha 程序提供目前在有限的一组客户中经过测试的功能。这样，我们就可以根据收到的反馈来改进产品。这些功能并非对于所有 Journey Orchestration 客户都可用。

在专用[部分](../alpha/alpha-overview.md)中对这些功能进行了描述。

<table>
<thead>
<tr>
<th><strong>增强的用户界面</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Journey Orchestration 菜单内的导航已得到增强，以便提供与 Adobe Experience Platform 一致的界面：
</p>
<ul>
<li><p>菜单从界面的顶部移动到左侧。 </p>
</li>
<li><p>将管理功能分组到单个仪表板中。</p>
</li>
</ul>
<p>有关详细信息，请参阅<a href="../alpha/alpha-interface.md">详细文档</a>。</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>区段触发活动</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>“区段触发”活动允许属于 Adobe Experience Platform 区段的所有个人进入旅程。进入旅程的操作可以执行一次，也可以定期执行。<a href="../alpha/alpha-segment-trigger.md">阅读更多</a>
</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>基于规则的事件</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>我们简化了您设置体验事件的方式。我们正在引入一种无需使用 eventID 的新方法。在 Journey Orchestration 中设置事件时，现在可以定义基于规则的事件。<a href="../event/about-events.md">阅读更多</a>
</p>
</td>
</tr>
</tbody>
</table>


## 第 2 季度发行 - 2020 年 6 月 {#q2-release---june-2020}

<table>
<thead>
<tr>
<th><strong>Adobe Experience Platform 集成增强</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>已进行以下 Adobe Experience Platform 集成增强：</p>
<ul>
<li><p>新活动允许侦听 Adobe Experience Platform 区段入口/出口，以使人员进入旅程或在旅程中前进。<a href="../building-journeys/segment-qualification-events.md">阅读更多</a></p>
<img src="../assets/rn-segment7.png"/>
</li>
<li><p>由于新增了<strong>区段</strong>选项卡，现在无需离开 Journey Orchestration 界面即可创建和编辑 Adobe Experience Platform 区段。<a href="../segment/about-segments.md">阅读更多</a></p>
<img src="../assets/rn-segment1.png"/>
</li>
<li><p>在简单表达式编辑器中，Adobe Experience Platform 区段现在直接列出在导航树中，以便轻松设置条件，例如“此人是否属于区段 A？”。<a href="../segment/using-a-segment.md">阅读更多</a></p>
<img src="../assets/rn-segment4.png"/>
</li>
<li><p>Journey Orchestration 现在会自动将旅程中执行的步骤传递到 Adobe Experience Platform。这包括遇到的潜在错误。此信息可用于通过对特定旅程或所有旅程的旅程步骤事件执行查询，从而实现报告和故障排除。<a href="../building-journeys/sharing-overview.md">阅读更多</a></p>
<img src="../assets/rn-journeystepevent.png"/>
</li>
<li><p>Journey Orchestration 现在可以连接到生产和非生产 Adobe Experience Platform 沙箱。请注意，沙箱是测试版功能。<a href="../about/access-management.md#sandboxes">阅读更多</a></p>
</li>
</ul>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>旅程设计人员和测试模式增强功能</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>对旅程设计人员和测试模式进行了以下增强：</p>
<ul>
<li><p>您现在可以选中 1 个或 N 个旅程活动，将活动从一个旅程复制粘贴到另一个旅程。<a href="../building-journeys/using-the-journey-designer.md#copy-paste">阅读更多</a></p>
<img src="../assets/rn-copy-paste1.png"/>
</li>
<li><p>在启动一个事件以使测试用户档案进入旅程后，您现在可以看到其在旅程中的进度，这用彩色的视觉流显示。如果旅程中出错，系统还会显示错误的详细信息。<a href="../building-journeys/testing-the-journey.md#firing_events">阅读更多</a></p>
<img src="../assets/rn-journeytest6.png"/>
</li>
<li><strong>已完成</strong>的旅程状态已更名为<strong>已关闭（禁止进入）</strong>，以更好地反映此状态的含义。</li>
</ul>
</td>
</tr>
</tbody>
</table>

**其他改进**

为避免向第三方系统发送过多 API 调用，我们引入了新的公共 API 来设置“上限”规则。上限规则允许定义每毫秒对 API 端点的最大调用数。[阅读更多](../api/capping.md)

访问控制现在允许在用户访问管理中实现更大粒度。可用起始日期：2020 年 6 月 30 日。[阅读更多](../about/access-management.md#create-product-profile)

Journey Orchestration 现已在 APAC（澳大利亚数据中心）提供。可用起始日期：2020 年 6 月 30 日

Journey Orchestration 界面提供日语版。

## 第 1 季度发行 - 2020 年 3 月{#q1-release---march-2020}

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
<li>通过<strong>用户档案时区</strong>复选框，您可以使用进入旅程的人员的 Adobe Experience Platform 用户档案时区（如果可用）。如果不可用，则使用下拉列表中定义的时区。此功能与使用没有命名空间的事件的旅程不兼容。</li>
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

* 除美国以外，现在&#x200B;**欧洲、中东和非洲地区**&#x200B;也提供 Journey Orchestration。应用程序和文档提供法语和德语两个版本。

* Experience League 现已集成到产品中。这简化了对相关内容的访问，并有助于您充分利用 Experience Cloud。直接访问“帮助”选项卡底部的 Journey Orchestration 文档。此外，单击“帮助”>“反馈”以报告问题或与 Adobe 分享您的想法。

* 现在，所有列表屏幕中都提供 **C** 键盘快捷键，它允许您创建新项目：旅程、数据源、操作和事件。[阅读更多](../about/user-interface.md#section_ksq_zr1_ffb)

* 您现在可以&#x200B;**删除**&#x200B;已停止的旅程。与这些已删除的旅程关联的报告将不可用。

* 浏览 **Adobe Experience Platform 字段**（XDM 格式）时，除了字段名称外，您现在还会看到显示名称。此信息可从体验数据模型中的架构定义中检索。当可用时，将显示替代显示名称。此用户友好型描述（在 eVar 字段中尤为有用）使您能够更轻松地识别字段。[阅读更多](../about/user-interface.md#friendly-names-display)

## 正式全面发行 - 2019 年 12 月 {#ga-release---december-2019}

Journey Orchestration 现已正式全面发行。

利用存储在事件或数据源中的情境数据构建实时编排用例。

Journey Orchestration 允许由事件的情境数据、Adobe Experience Platform 信息或第三方 API 服务数据提供支持的实时编排。应用程序根据消费者的资料和行为确定在称为旅程的多步流中特定于消费者的下一个最佳操作。这包括最佳时间和操作类型，如通过 Adobe Campaign Standard 事务性消息传送功能（需要 Adobe Campaign Standard）向消费者发送推送通知或第三方系统通知。这些决策是根据规则和 Sensei 得分做出的。

[](../action/working-with-adobe-campaign.md)
详细了解 Journey Orchestration。

其他资源：

* [教程](https://docs.adobe.com/content/help/zh-Hans/journey-orchestration-learn/tutorials/understanding-journey-orchestration.html)
* [社区](https://www.adobe.com/go/journeyorchestrationcommunity)
