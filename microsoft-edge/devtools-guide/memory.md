---
description: 使用 "内存" 面板
title: DevTools-内存
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/05/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools、内存、堆、GC、垃圾回收、保留的大小、dominators
ms.custom: seodec18
ms.openlocfilehash: 416ba144f7e22bd50f5d2a3437bc21d9d31a9035
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563476"
---
# 内存

使用 " **内存** " 面板测量系统资源的使用情况，并在不同的代码执行状态中比较堆快照。 有了它，您可以：

- [实时绘制页面的内存占用情况](#memory-usage-timeline) 并拍摄堆的快照
- [确定代码中可能存在的内存问题](#snapshot-summary) ，例如未附加到 DOM 的保留对象
- 按对象类型、实例计数、大小和引用[查看内存使用数据](#snapshot-details)以帮助隔离问题
- [应用快照数据筛选器](#filters) 以减少不可操作的信息的干扰
- [确定特定对象的内存开销](#object-references) ，并且引用保持活动状态
- [在调查的不同阶段比较堆](#snapshot-comparison) 以跟踪内存泄漏和其他问题的来源

![Microsoft Edge DevTools 内存面板](./media/memory.png)


## 工具栏

1. **开始/停止分析会话 (Ctrl + E) **：打开探查器可让你跟踪内存使用情况并拍摄堆的快照。
2. ** (Ctrl + O) 导入性能分析会话 **：加载已保存的 DevTools 内存诊断会话。
3. ** (Ctrl + S) 导出性能分析会话 **：将当前的诊断会话保存到磁盘。
4. **采用堆快照 (Ctrl + Shift + T) **：记录给定时间点的当前内存分配。


## 内存使用日程表

内存问题可能是性能问题的主要原因，导致你的页面在一段时间内变得越来越慢和 laggy。

分析页面的内存使用的第一步是 [启动性能分析会话](#toolbar) ，以便在你重现导致内存膨胀或可疑内存泄漏的步骤之前和之后执行堆栈快照。

启动内存探查器时，你将看到一个进程内存图，使你能够观察整个专用工作集， (页面随时间推移) 占用的内存量。 "内存" 图显示了选项卡的进程内存的实时视图，其中包括专用字节、本机内存和 JavaScript 堆。 

![内存使用日程表](./media/memory_timeline.png)

 该图提供了页面的内存趋势的指示，使你能够判断何时适合将 [堆快照](#toolbar) 用作后续比较，例如当你看到意外内存保留期间。

### 性能。标记 ( # A1

你可以将自定义 **用户标记** 添加到日程表，以通过 [`Performance.mark()`](https://developer.mozilla.org/docs/Web/API/Performance/mark) 从你的代码或 DevTools [**控制台**](./console.md)调用该方法来帮助标识分析会话期间的关键事件。

### TakeheapSnapshot ( # A1

有时，你需要在非常具体的时间点拍摄快照，例如在 DOM 的较大变化之前。 在这些情况下，你可以采用编程方式获取快照 [`Console.takeHeapSnapshot()`](./console/console-api.md#taking-heap-snapshots) 。

## 快照摘要

[拍摄快照](#toolbar) 将生成一个摘要磁贴，该图块指示拍摄快照时 JavaScript 堆的大小以及所分配的对象数和页面的屏幕截图。 在运行需要分析的用户方案时，你可以随时继续拍摄快照。 快照会生成其他磁贴，每个磁贴指示 JavaScript 内存中来自上一个快照的差异。

![堆快照](./media/memory_snapshot.png)

单击摘要磁贴中的值将切换到显示 [快照数据详细信息](#snapshot-details)的窗格。 使用蓝色信息 ( "i" ) 图标表示潜在的 [内存问题](#snapshot-details) 。

## 快照详细信息

" *快照* " 窗格中的数据显示由您的页面创建的对象以及你可能需要使用的 JavaScript 框架分配的任何内存。

![快照详细信息表](./media/memory_details.png)

这三个选项卡代表数据的不同视图：

#### 类型

显示堆上的对象的实例计数和总大小，按对象类型分组。 默认情况下，这些按实例计数进行排序。

在 "上部 *类型* " 窗格中选择对象时，下方窗格中的 " [对象引用](#object-references) " 表将列出指向该对象的所有对象。

#### 方根

显示子引用的分层视图，以描述对象如何成为全局对象的根，从而阻止它们被垃圾回收。

默认情况下，子节点按 "保留的大小" 列进行排序，最大的值位于顶部。

#### Dominators

显示堆上具有对其他对象的独占引用的对象的列表。 Dominators 按保留大小排序，以指示占用最容易自由的内存的对象。

下面介绍了如何解释 *类型、根* 和 *Dominators* 视图中的列：

列 | 描述
:------------ | :-------------
 (s 的标识符)  | 最能识别对象的名称。 例如，对于 HTML 元素，快照详细信息显示 ID 属性值（如果使用了一个）。
类型 | 对象类型 (例如， *HTMLDivElement*) 。
大小 | 对象大小，不包括任何引用对象的大小。
保留大小 | 对象大小加上没有其他父对象的所有子对象的大小。 为了便于使用，这是由对象保留的内存量，因此，如果你删除了指定的内存量，则会删除该对象。
Count | 对象实例数。 此值仅在 "类型" 视图中显示。

在上方的 *Dominators* 窗格中选择对象时，下方窗格中的 " [对象引用](#object-references) " 表将列出指向该对象的所有对象。

### 筛选器

你可以通过以下方式进一步调整表中的数据：

![筛选内置和对象 Id](./media/memory_filter.png)

1. **标识符筛选器**：通过搜索特定对象标识符来筛选数据
2. **按 Dominator 分组**：只有对其他对象具有 *独占* 引用的对象才会显示在对象的顶级视图中， (这是 *Dominators* 选项卡中的默认视图) 。
3. **内置/IDs 筛选器**：默认情况下，列表中包含 [JavaScript 内置对象](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects) 。 如果存在多个需要区分的匿名对象，则列出对象 Id 可能很有用。

每个 *类型、根* 和 *Dominators* 视图都有其自己的筛选器，因此切换到另一个视图时不会保留筛选器。

### 对象引用

在 " [**类型**](#types) " 和 " [**Dominators**](#dominators) " 视图中，下方窗格包含显示共享引用的 " **对象引用** " 列表。 当您在上部窗格中选择一个对象时，此列表将显示指向该对象的所有对象，换句话说，是使所选对象保持活动状态的对象。

循环引用以星号 ( * ) 和信息工具提示显示，并且不能展开。 否则，它们将阻止你向上遍历引用树和标识保留内存的对象。

若要快速识别等效对象，请勾选 " [*显示对象 id*](#filters) " 筛选器选项，以便在 " *标识符 (s) * " 列中的对象名称旁显示对象 id。 具有相同 ID 的对象为共享引用。

### 快照比较

单击 "[快照摘要" 图块](#snapshot-summary)上的 "[快照比较" 选项卡](#snapshot-details)或比较链接将显示两个快照之间的信息的比较。 在 "比较" 窗格中，" *Dominators"、"类型* " 和 " *根* " 视图提供了相同的 [*快照详细信息*](#snapshot-details) ，你可以看到一个快照的详细信息，包括以下其他值：

列 | 描述
:------------ | :-------------
大小差异。 | 当前快照中对象的大小与上一快照中的对象大小之间的差异，不包括任何引用对象的大小。
保留大小差异。 | 当前快照中对象的保留大小与上一快照中的保留大小之间的差异。 保留的大小包括对象大小加上没有其他父对象的所有子对象的大小。 为了实用，保留大小是指由对象保留的内存量，因此，如果你删除了指定的内存量，则会删除该对象。

你可以使用 **范围** 下拉列表来筛选快照之间的差异信息：

![快照 comparisions 的作用域筛选器](./media/memory_comparison_scope_filter.png)

- <strong>从快照 # 中留下的对象 # <number></strong> ：显示添加到堆中的对象与从基线快照到上一个快照的堆栈之间的比较。 例如，如果 "快照摘要" <em> 在对象计数中显示 + 205/-195 </em> ，此筛选器将显示已添加但未删除的十个对象。

- <strong>在快照 # <number> 和 #：之间添加 <number></strong> 的对象显示从以前的快照添加到堆的所有对象。

- <strong>快照 #：中的所有对象都 <number></strong> 显示堆上的所有对象 (换言之，"未 <em> 筛选的视图" </em>) 。

默认情况下，" *显示不匹配的引用* " 筛选器将应用于 "比较" 视图，以指示与当前范围筛选器不匹配的对象引用。 您可以从下拉菜单中将其关闭：

![不匹配的引用筛选快照比较](./media/memory_comparison_matching_filter.png)


## 快捷方式

 操作 | 快捷方式
:------------ | :-------------
开始/停止分析会话  | `Ctrl` + `E`
导入性能分析会话 | `Ctrl` + `O`
导出分析会话 | `Ctrl` + `S`
获取堆快照 | `Ctrl` + `Shift` + `T`

## 已知问题

### 启动分析会话时出错

如果你看到此错误消息：在内存工具中 **启动分析会话时出错** ，请按照以下步骤进行解决。

1. 按 `Windows Key`  +  `R` 。

2. 在 "运行" 对话框中，输入 **services.msc**。
![已知问题-1](./media/known_issues_1.PNG)

3. 找到 **Microsoft (R) 诊断中心标准收集器服务** ，然后右键单击它。
![已知问题-2](./media/known_issues_2.PNG)

4. 重新启动 **Microsoft (R) 诊断中心标准收集器服务**。
![已知问题-3](./media/known_issues_3.PNG)

5. 关闭 Microsoft Edge 开发人员工具和选项卡。打开新选项卡，导航到您的页面，然后按 `F12` 。

6. 现在，你应该能够开始分析。 
![已知问题-4](./media/known_issues_4-memory.PNG)

仍遇到问题？ 请使用 " **发送反馈** " 图标向我们发送您的反馈！ 

![已知问题-5](./media/known_issues_5.PNG)
