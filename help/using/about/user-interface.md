---
product: adobe campaign
title: 用户界面
description: 了解有关用户界面的更多信息
feature: Journeys
role: User
level: Intermediate
exl-id: 0d0e74c7-6cb0-4068-a69a-3c01f8b3552d
source-git-commit: a5ec1c4c5608113bb17dfbdea0587f6bb342099a
workflow-type: tm+mt
source-wordcount: '985'
ht-degree: 94%

---

# 用户界面{#concept_rcq_lqt_52b}

>[!NOTE]
>
>为了充分利用 [!DNL Journey Orchestration]，我们建议将 Chrome 用作您的 Internet 浏览器。接口以 IMS 中定义的语言显示。如果 IMS 语言不受 [!DNL Journey Orchestration] 支持，则界面将以英语显示。
>
>此文档会经常更新以反映产品中的最新更改。但是，某些屏幕截图可能与产品的界面略有不同。

## 访问 [!DNL Journey Orchestration]{#accessing_journey_orchestration}

要访问 [!DNL Journey Orchestration] 的界面，请单击右上角的 **[!UICONTROL App Selector]** 图标，然后单击 **[!UICONTROL Journey Orchestration]**。

![](../assets/journey1.png)

您还可以从 Experience Cloud 主页的 **[!UICONTROL Quick access]** 部分访问 [!DNL Journey Orchestration]。

![](../assets/journey1bis.png)

## 了解界面{#section_jsq_zr1_ffb}

>[!CONTEXTUALHELP]
>id="jo_home"
>title="关于历程列表"
>abstract="历程列表允许您同时查看所有历程、查看其状态并执行基本操作。"
>additional-url="https://images-tv.adobe.com/mpcv3/38af62cb-9390-4bc0-a576-d336849adb97_1574809570.1920x1080at3000_h264.mp4" text="观看演示视频"

通过顶部菜单，您可以浏览 [!DNL Journey Orchestration] 的不同功能：**[!UICONTROL Home]**（历程）、**[!UICONTROL Data Sources]**、**[!UICONTROL Events]**、**[!UICONTROL Actions]**。

![](../assets/journey2.png)

单击屏幕右上角的![](../assets/icon-context.png)图标以显示情景帮助。它可以在不同的 [!DNL Journey Orchestration] 列表屏幕（历程、事件、操作和数据源）中使用。通过此情景帮助，您可以查看当前功能的快速说明，并访问相关文章和视频。

![](../assets/journey2bis.png)

## 搜索和筛选{#section_lgm_hpz_pgb}

在 **[!UICONTROL Home]**、**[!UICONTROL Data Sources]**、**[!UICONTROL Events]** 和 **[!UICONTROL Actions]** 列表中，搜索栏允许您搜索项目。

单击列表左上角的过滤器图标即可访问 **[!UICONTROL Filters]**。通过过滤器菜单，您可以根据不同的条件筛选显示的元素。您可以选择仅显示特定类型或状态、您创建的元素或最近 30 天内修改的元素。

在 **[!UICONTROL Data Sources]**、**[!UICONTROL Events]** 和 **[!UICONTROL Actions]** 列表中，使用 **[!UICONTROL Creation filters]** 按创建日期和用户进行过滤。例如，您可以选择仅显示您在过去 30 天中创建的事件。

在历程列表中(在 **[!UICONTROL Home]**)，以及 **[!UICONTROL Creation filters]**，您还可以根据显示的历程的状态、类型和版本(**[!UICONTROL Status and version filters]**)。 类型可以是： **[!UICONTROL Unitary event]** 或 **[!UICONTROL Segment qualification]**. 您还可以选择仅显示使用特定事件、字段组或操作（**[!UICONTROL Activity filters]**&#x200B;和 **[!UICONTROL Data filters]**）的历程。通过&#x200B;**[!UICONTROL Publication filters]**，您可以选择发布日期或用户。例如，您可以选择仅显示昨天发布的最新版实时历程。请参阅[此页](../building-journeys/using-the-journey-designer.md)。

>[!NOTE]
>
>请注意，显示的列可以使用列表右上角的配置按钮进行个性化设置。为每个用户保存个性化设置。

通过 **[!UICONTROL Last update]**&#x200B;和 **[!UICONTROL Last update by]** 列，可显示您的历程的上次更新时间以及运行该更新的用户。

![](../assets/journey74.png)

在“事件”、“数据源”和“操作配置”窗格中，**[!UICONTROL Used in]**&#x200B;字段显示使用该特定事件、字段组或操作的历程数。您可以单击“**[!UICONTROL View journeys]**”按钮以显示相应历程的列表。

![](../assets/journey3bis.png)

在不同的列表中，您可以对每个元素执行基本操作。例如，您可以删除项目或制作项目副本。

![](../assets/journey4.png)

## 浏览 Adobe Experience Platform 字段 {#friendly-names-display}

在定义[事件有效负载](../event/defining-the-payload-fields.md)、[字段组有效负载](../datasource/field-groups.md)以及在[表达式编辑器](../expression/expressionadvanced.md)中选择字段时，除字段名称外，还会显示其显示名称。此信息可从体验数据模型中的架构定义中检索。

如果在设置架构时提供了诸如“xdm:alternateDisplayInfo”之类的描述符，则用户友好型名称将替换显示名称。在使用“eVars”和通用字段时尤为有用。您可以通过 API 调用配置友好名称描述符。有关详细信息，请参阅[架构注册开发人员指南](https://experienceleague.adobe.com/docs/experience-platform/xdm/api/getting-started.html?lang=zh-Hans)。

![](../assets/xdm-from-descriptors.png)

如果友好名称可用，则字段将显示为`<friendly-name>(<name>)`。如果没有可用的友好名称，将显示其显示名称，如`<display-name>(<name>)`。如果这两种名称均未定义，则仅显示字段的技术名称 `<name>`。

>[!NOTE]
>
>从架构组合中选择字段时，不会检索友好名称。

## 辅助功能{#accessibility}

Adobe Journey Optimizer中的辅助功能由Adobe Experience Platform提供：

* 键盘辅助功能
* 颜色对比度
* 验证必填字段

在 Adobe Experience Platform 文档中[了解详情](https://experienceleague.adobe.com/docs/experience-platform/accessibility/features.html?lang=zh-Hans){target="_blank"}。

您可以在Adobe Journey Optimizer中使用这些常用键盘快捷键：

| 操作 | 快捷键 |
| --- | --- |
| 在用户界面元素、部分和菜单组之间移动 | Tab |
| 在用户界面元素、部分和菜单组之间向后移动 | Shift + Tab |
| 在部分内移动，将焦点设置到单个元素 | 箭头 |
| 选择或清除焦点元素 | 回车键或空格键 |
| 取消选择、折叠面板或关闭对话框 | Esc |

在 Adobe Experience Platform 文档中[了解详情](https://experienceleague.adobe.com/docs/experience-platform/accessibility/custom.html?lang=zh-Hans){target="_blank"}。

您可以在 Journey Optimizer 的特定部分中使用这些快捷键：

<table>
  <thead>
    <tr>
      <th>界面元素</th>
      <th>操作</th>
      <th>快捷键</th>
    </tr>
  </thead>
  <tr>
    <td>历程、操作、数据源或事件列表</td>
    <td>创建历程、操作、数据源或事件</td>
    <td>C</td>
  </tr>
  <tr>
    <td rowspan="3">历程画布处于草稿状态</td>
    <td>从左侧面板的第一个可用位置从上到下添加活动</td>
    <td>双击活动</td>
  </tr>
  <tr>
    <td>选择所有活动</td>
    <td>Ctrl + A (Windows)<br/>Command + A (Mac)</td>
  </tr>
  <tr>
    <td>删除选定的活动</td>
    <td>Delete 键或退格键，然后按回车键以确认删除</td>
  </tr>
  <tr>
  <td rowspan="3">

以下元素的配置窗格：

<ul>
  <li>历程中的活动</li>
  <li>事件</li>
  <li>数据源</li>
  <li>操作</li>
</ul>

</td>
    <td>移到要配置的下一个字段</td>
    <td>Tab</td>
  </tr>
  <tr>
    <td>保存更改并关闭配置窗格</td>
    <td>回车键</td>
  </tr>
  <tr>
    <td>放弃更改并关闭配置窗格</td>
    <td>Esc</td>
  </tr>
  <tr>
    <td rowspan="4">测试模式下的历程</td>
    <td>启用或禁用测试模式</td>
    <td>T</td>
  </tr>
  <tr>
    <td>在基于事件的历程中触发事件</td>
    <td>E</td>
  </tr>
  <tr>
    <td>

在基于区段的历程中触发事件，其中 **[!UICONTROL Single profile at a time]** 选项处于打开状态

</td>
    <td>P</td>
  </tr>
  <tr>
    <td>显示测试日志</td>
    <td>L</td>
  </tr>
<!-- //Ajouter ce raccourci quand il marchera (actuellement, le raccourci Ctrl/Cmd+F du navigateur a priorité sur celui de AJO).//
  <tr>
    <td>Page with a search bar</td>
    <td>Select the search bar</td>
    <td>Ctrl/Command + F</td>
  </tr>
-->
  <tr>
    <td>文本字段</td>
    <td>选择所选字段中的所有文本</td>
    <td>Ctrl + A (Windows)<br/>Command + A (Mac)</td>
  </tr>
  <tr>
    <td rowspan="2">弹出窗口</td>
    <td>保存更改或确认操作</td>
    <td>回车键</td>
  </tr>
  <tr>
    <td>关闭窗口</td>
    <td>Esc</td>
  </tr>
  <tr>
    <td>简单表达式编辑器</td>
    <td>选择并添加字段</td>
    <td>双击字段</td>
  </tr>
  <tr>
    <td>浏览 XDM 字段</td>
    <td>选择节点的所有字段</td>
    <td>选择父节点</td>
  </tr>
  <tr>
    <td>负载预览</td>
    <td>选择有效负载</td>
    <td>Ctrl + A (Windows)<br/>Command + A (Mac)</td>
  </tr>
</table>
