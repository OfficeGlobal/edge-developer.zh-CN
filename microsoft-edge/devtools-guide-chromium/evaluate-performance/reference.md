---
title: 性能分析参考
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/29/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: acd6e3e68f89096cf80c08f0d0c3430ab31eaec1
ms.sourcegitcommit: 50991a04c18283a8890ae33fcc3491c0476c7684
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/30/2020
ms.locfileid: "10611746"
---
<!-- Copyright Kayce Basques 

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       https://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.  -->  







# 性能分析参考   



此页面是与分析性能相关的 Microsoft Edge DevTools 功能的完整参考。  

有关如何使用[Microsoft Edge DevTools][MicrosoftEdgeDevTools]分析页面性能的引导式教程，请参阅[分析运行时性能开始][DevtoolsEvaluatePerformanceGettingStarted]。  

## 记录性能   

### 记录运行时性能   

当您希望分析页面的性能（相对于加载）时，请记录运行时性能。  

1.  转到要分析的页面。  
1.  单击 "DevTools" 中的 "**性能**" 选项卡。  
1.  单击 "**录制** ![ 记录" ][ImageRecordIcon] 。  
    
    > ##### 图 1  
    > **记录**  
    > ![记录][ImageRecord]  

1.  与页面交互。  DevTools 记录作为交互的结果而发生的所有页面活动。  
1.  再次单击 "**录制**" 或单击 "**停止**" 停止录制。  

### 记录加载性能   

当你希望在加载时分析页面性能（而不是运行）时，请记录加载性能。  

1.  转到要分析的页面。  
1.  打开 DevTools 的**性能**面板。  
1.  单击 "**刷新页面** ![ 刷新页面" ][ImageRefreshPageIcon] 。  DevTools 在页面刷新时记录性能指标，然后在加载完成后的几秒钟内自动停止录制。  
    
    > ##### 图 2  
    > **刷新页面**  
    > ![刷新页面][ImageRefreshPage]  

DevTools 会自动放大大部分活动发生的录制部分。  

> ##### 图 3  
> 页面加载录制  
> ![页面加载录制][ImageLoadRecording]  

### 录制时捕获屏幕截图   

启用 "**屏幕截图**" 复选框，以便在录制时捕获每个帧的屏幕截图。  

> ##### 图 4  
> "**屏幕截图**" 复选框  
> !["屏幕截图" 复选框][ImageScreenshots]  

请参阅[查看屏幕截图](#view-a-screenshot)，了解如何与屏幕截图交互。  

### 录制时强制垃圾回收   

录制页面时，请单击 "**收集垃圾**回收 ![ 垃圾" ][ImageCollectGarbageIcon] 以强制进行垃圾回收。  

> ##### 图 5  
> 收集垃圾  
> ![收集垃圾][ImageCollectGarbage]  

### 显示录制设置   

单击 "**捕获设置** ![ 捕获设置" ][ImageCaptureSettingsIcon] 以显示有关 DevTools 如何捕获性能录制的更多设置。  

> ##### 图 6  
> "**捕获设置**" 部分  
> !["捕获设置" 部分][ImageCaptureSettings]  

### 禁用 JavaScript 示例   

默认情况下，录制的**主要**部分显示在录制期间调用的 JavaScript 函数的详细调用堆栈。  要禁用这些调用堆栈，请执行以下操作：  

1.  打开 "**捕获设置**" 菜单。  请参阅[显示录制设置](#show-recording-settings)。  
1.  启用 "**禁用 JavaScript 示例**" 复选框。  
1.  记录页面。  

[图 7](#figure-7)和[图 8](#figure-8)显示了禁用和启用 JavaScript 示例之间的区别。  在禁用采样时，录制的**主要**部分会更短，因为它省略了所有 JavaScript 调用堆栈。  

> ##### 图 7  
> 禁用 JS 示例时录制的示例  
> ![禁用 JS 示例时录制的示例][ImageJSSamplesDisabled]  

> ##### 图 8  
> 启用 JS 示例时录制的示例  
> ![启用 JS 示例时录制的示例][ImageJSSamplesEnabled]  

### 录制时阻止网络   

要在录制时阻止网络，请执行以下操作：  

1.  打开 "**捕获设置**" 菜单。  请参阅[显示录制设置](#show-recording-settings)。  
1.  将 "**网络**" 设置为所需的带宽限制级别。  

### 在录制时调节 CPU   

要在录制时调节 CPU，请执行以下操作：  

1.  打开 "**捕获设置**" 菜单。  请参阅[显示录制设置](#show-recording-settings)。  
1.  将**CPU**设置为所需的带宽限制级别。  

"限制" 相对于计算机的功能。  例如， **2x 减速**选项使 CPU 的运行速度比正常速度慢2倍。  DevTools 不会真正模拟移动设备的 Cpu，因为移动设备的体系结构与台式计算机和笔记本电脑的体系结构截然不同。  

### 启用高级画图工具   

查看详细的画图工具：  

1.  打开 "**捕获设置**" 菜单。  请参阅[显示录制设置](#show-recording-settings)。  
1.  选中 "**启用高级画图工具（慢）** " 复选框。  

若要了解如何与画图信息交互，请参阅[查看图层](#view-layers-information)和[查看画图探查器](#view-paint-profiler)。  

## 保存录制   

若要保存录制，请右键单击，然后选择 "**保存配置文件**"。  

> ##### 图 9  
> **保存配置文件**  
> ![保存配置文件][ImageSaveProfile]  

## 加载录制   

若要加载录制，请右键单击，然后选择 "**加载配置文件**"。  

> ##### 图 10  
> **加载配置文件**  
> ![加载配置文件][ImageLoadProfile]  

## 清除上一个录制   

录制后，按 "**清除**录制 ![ " 清除录制 ][ImageClearRecordingIcon] 以从 "**性能**" 面板中清除该录制内容。  

> ##### 图 11  
> 清除录制  
> ![清除录制][ImageClearRecording]  

## 分析性能记录   

在[记录运行时性能](#record-runtime-performance)或[记录加载性能](#record-load-performance)后，"**性能**" 面板会提供大量数据来分析所发生的情况的性能。  

### 选择部分录制   

在**概述**中向左或向右拖动鼠标，选择部分录制。  **概述**是包含**FPS**、 **CPU**和**网络**图表的部分。  

> ##### 图 12  
> 在概述中拖动鼠标以缩放  
> ![在概述中拖动鼠标以缩放][ImageZoom]  

要使用键盘选择某个部分，请执行以下操作：  

1.  单击**主**节的背景，或单击它旁边的任何部分（如**交互**、**网络**或**GPU**）。  只有当其中一个分区处于焦点时，此键盘工作流才有效。  
1.  使用 `W` 、 `A` 、 `S` 、 `D` 键进行放大、向左移动、缩小和向右移动。  

若要使用触控板选择部分，请执行以下操作：  

1.  将鼠标悬停在 "**概述**" 部分或 "**详细信息**" 部分。  "**概述**" 部分是包含 " **FPS**"、" **CPU**" 和 "**网络**" 图表的区域。  "**详细信息**" 部分是包含**主要**部分、"**交互**" 部分等的区域。  
1.  使用两根手指，向上轻扫以缩小，向左轻扫可向左移动，向下轻扫以放大，向右轻扫以向右移动。  

若要在**主**分区或任何邻居中滚动较长的火焰图表，请单击并按住鼠标上下拖动。  向左和向右拖动以移动所选录制部分。  

### 搜索活动   

按 `Control` + `F` \ （Windows \）或 `Command` + `F` \ （macOS \）打开 "**性能**" 面板底部的 "搜索" 框。  

> ##### 图 13  
> 在窗口底部的 "搜索" 框中使用 regex 查找以 ... 开头的任何活动 `E`  
> ![搜索框][ImageSearch]  

若要导航与查询匹配的活动，请执行以下操作：  

*   使用**前面**的 "上一个" 和 "下一个" ![ ][ImagePreviousIcon] **Next** ![ ][ImageNextIcon] 按钮。  
*   按下 `Shift` + `Enter` 选择 "上一 `Enter` 步" 或选择下一个。  

修改查询设置：  

*   按**大小**写区分大小 ![ 写 ][ImageSearchCaseIcon] 以使查询区分大小写。  
*   按**regex** ![ regex ][ImageSearchRegexIcon] 在查询中使用正则表达式。  

若要隐藏搜索框，请按 "**取消**"。  

### 查看主线程活动   

使用**主**部分查看在页面的主线程上发生的活动。  

> ##### 图 14  
> **主要**部分  
> ![主要部分][ImageMain]  

单击事件可在 "**摘要**" 选项卡中查看有关它的详细信息。 DevTools 概述所选事件。  

> ##### 图 15  
> 有关 `anonymous` "**摘要**" 选项卡中的函数的详细信息  
> ![有关 "摘要" 选项卡中的匿名函数的详细信息][ImageMainEventSummary]  

DevTools 表示带有火焰图表的主线程活动。  X 轴表示一段时间内的录制。  Y 轴表示调用堆栈。  顶部的事件会导致其下方的事件。  

> ##### 图 16  
> **主**部分中的火焰图  
> ![火焰图][ImageFlameChart]  

在[图 16](#figure-16)中， `click` 事件导致 `Function Call` `activitytabs.js` 行53上出现 a。  `Function Call`你将看到调用了一个匿名函数。  调用了称为的匿名函数 `a` `wait` `Minor GC` 。  

DevTools 分配脚本随机颜色。  在[图 16](#figure-16)中，一个脚本的函数调用的颜色为浅绿色。  来自另一个脚本的通话的颜色为米色。  较深的黄色表示脚本活动，紫色事件表示呈现活动。  这些较暗的黄色和紫色事件在所有录制中保持一致。  

如果想要隐藏 JavaScript 调用的详细火焰图表，请参阅[禁用 javascript 示例](#disable-javascript-samples)。  如果已禁用 JS 示例，则只能查看 `Event: click` `Function Call` [图 16](#figure-16)中的高级别事件，例如和。  

### 查看表中的活动   

录制页面后，不需要仅依赖**主要**部分来分析活动。  DevTools 还提供了用于分析活动的三个表格视图。  每个视图为您提供了不同的活动视角：  

*   当您想要查看导致大部分工作的根活动时，请使用["**调用树**" 选项卡](#the-call-tree-tab)。  
*   当您想要查看最常被直接花费的时间的活动时，请使用["**下**" 选项卡](#the-bottom-up-tab)。  
*   如果要按录制期间的顺序查看活动，请使用["**事件日志**" 选项卡](#the-event-log-tab)。  

> [!NOTE]
> 接下来的三个部分都是指同一演示。  在 "[活动" 选项卡演示][ActivityTabsDemo]中自行运行演示。  

#### 根活动   

下面是 "**调用树**" 选项卡、"**下移至**" 选项卡和 "**事件日志**" 部分中提及的**根活动**概念的说明。  

根活动是导致浏览器执行某些工作的操作。  例如，当您单击页面时，浏览器会将 `Event` 活动作为根活动触发。  这 `Event` 可能会导致处理程序运行，依此类推。  

在**主**区域的火焰图表中，根活动位于图表顶部。  在 "**调用树**" 和 "**事件日志**" 选项卡中，根活动是顶级项目。  

有关根活动的示例，请参阅["调用树" 选项卡](#the-call-tree-tab)。  

#### "调用树" 选项卡   

使用 "**调用树**" 选项卡查看哪些[根活动](#root-activities)导致最大的工作。  

"**调用树**" 选项卡仅在录制的选定部分中显示活动。  请参阅[选择部分录制](#select-a-portion-of-a-recording)内容，了解如何选择部分内容。  

> ##### 图 17  
> "**调用树**" 选项卡  
> !["调用树" 选项卡][ImageCallTree]  

在[图 17](#figure-17)中，"**活动**" 列中的项目的顶级级别，例如 " `Evaluate Script` 根活动" 和 " `Parse HTML` 是根活动"。  嵌套表示调用堆栈。  例如，如[图 17](#figure-17)所示，导致出现 `Parse HTML` `Evaluate Script` `Compile Script` 和 `(anonymous)` 。  

**自我时间**表示该活动直接花费的时间。  "**总时间**" 表示该活动或任何子活动所花费的时间。  

单击 "**自时间**"、"**总时间**" 或 "**活动**"，按该列对表格进行排序。  

使用 "**筛选**" 文本框按活动名称筛选事件。  

默认情况下，"**分组**" 菜单设置为 "**无分组**"。  使用 "**分组**" 菜单基于各种条件对活动表进行排序。  

单击 "**显示**最繁忙 ![ 的堆栈 ][ImageShowHeaviestStackIcon] " 显示最大的堆栈，将另一个表显示在**活动**表的右侧。  单击活动以填充最大的**堆栈**表。  "最**繁忙的堆栈**" 表显示所选活动的哪些子元素运行时间最长。  

#### "下" 选项卡   

使用 "**下**" 选项卡查看哪些活动直接占用总时间。  

**自下而上**的选项卡仅显示录制的选定部分中的活动。  请参阅[选择部分录制](#select-a-portion-of-a-recording)内容，了解如何选择部分内容。  

> ##### 图18  
> "**下**" 选项卡  
> !["下" 选项卡][ImageBottomUp]  

在[图 18](#figure-18)的 "**主要**" 部分的 "火焰" 部分中，查看几乎几乎没有运行所有时间 `Parse HTML` 。  [图 18](#figure-18)的 "**下**" 选项卡中的最高活动是 `Parse HTML` 。  <!--In the flame chart of [Figure 18](#figure-18), the yellow below the calls to `wait` are actually thousands of `Minor GC` calls.  -->  请参阅下一个最昂贵的活动（在 "**下**" 选项卡中） `Layout` 。  

"**自时间**" 列表示在该活动中直接占用的所有事件的总时间。  

"**总时间**" 列表示该活动或任何子活动所用的聚合时间。  

#### "事件日志" 选项卡   

使用 "**事件日志**" 选项卡，按录制过程中发生的顺序查看活动。  

"**事件日志**" 选项卡仅显示录制的选定部分中的活动。  请参阅[选择部分录制](#select-a-portion-of-a-recording)内容，了解如何选择部分内容。  

> ##### 图19  
> "**事件日志**" 选项卡  
> !["事件日志" 选项卡][ImageEventLog]  

"**开始时间**" 列表示活动开始的点，相对于录制的开始时间。  例如， `175.7 ms` [图 19](#figure-19)中所选项目的开始时间表示活动在录制开始后启动175.7 毫秒。  

"**自时间**" 列表示直接在该活动中花费的时间。  

"**总时间**" 列表示直接在该活动或任何子活动中所花费的时间。  

单击 "**开始时间**"、"**自时间**" 或 "**总时间**"，按该列对表格进行排序。

使用 "**筛选**" 文本框按名称筛选活动。  

使用 "**工期**" 菜单筛选出所有时间不超过1毫秒或15毫秒的活动。  默认情况下，"**持续时间**" 菜单设置为 "**全部**"，表示显示所有活动。  

禁用**加载**、**脚本**、**呈现**或**绘制**复选框，以筛选出这些类别中的所有活动。  

### 查看 GPU 活动   

查看**gpu**部分中的 gpu 活动。  

> ##### 图20  
> **GPU**部分  
> ![GPU 部分][ImageGpu]  

### 查看光栅活动   

查看**光栅**区中的 "光栅" 活动。  

> ##### 图21  
> "**光栅**" 部分  
> !["光栅" 部分][ImageRaster]  

### 查看交互   

使用 "**交互**" 部分查找和分析录制期间发生的用户交互。  

> ##### 图22  
> "**交互**" 部分  
> !["交互" 部分][ImageInteractions]  

交互底部的红线表示等待主线程所用的时间。  

单击交互以在 "**摘要**" 选项卡中查看有关它的详细信息。  

### 分析每秒帧数（FPS）   

DevTools 提供多种方法来分析每秒帧数：  

*   使用[ **fps**图](#the-fps-chart)大致了解录制期间的 FPS。  
*   使用["**框架**" 部分](#the-frames-section)可查看特定帧所用时间。  
*   当页面运行时，使用**fps 计量**器以实时估计 fps。  请参阅以[FPS 计量器实时查看每秒帧数](#view-frames-per-second-in-realtime-with-the-fps-meter)。  

#### FPS 图表   

**FPS**图表提供整个录制期间的帧速率的概览。  通常情况下，绿色条越高，帧速率越好。  

**FPS**图表上方的红色条是一条警告，表明帧速率降低的可能会损坏用户的体验。  

> ##### 图23  
> FPS 图表  
> ![FPS 图表][ImageFpsChart]  

#### "框架" 部分   

"**框架**" 部分告诉你特定帧所花时间的确切时间。  

将鼠标悬停在框架上方以查看工具提示，了解有关它的详细信息。  

> ##### 图24  
> 将鼠标悬停在框架上  
> ![将鼠标悬停在框架上][ImageFramesSection]  

单击框架可在 "**摘要**" 选项卡中查看有关该帧的详细信息。 DevTools 以蓝色显示所选帧的轮廓。  

> ##### 图25  
> 在 "**摘要**" 选项卡中查看框架  
> ![在 "摘要" 选项卡中查看框架][ImageFrameSummary]  

### 查看网络请求   

展开 "**网络**" 部分，查看录制期间出现的网络请求的瀑布。  

> ##### 图26  
> "**网络**" 部分  
> !["网络" 部分][ImageNetworkRequest]  

请求按如下方式进行颜色编码：  

*   HTML： Blue  
*   CSS：紫色  
*   JS：黄色  
*   图像：绿色  

单击请求可在 "**摘要**" 选项卡中查看有关它的详细信息。 例如，在[图 26](#figure-26)中，"**摘要**" 选项卡显示有关 "**网络**" 部分中所选蓝色请求的详细信息。  

请求左上角的蓝色正方形表示它是优先级较高的请求。  较浅的蓝色正方形意味着优先级较低。  例如，在[图 26](#figure-26)中，所选请求的优先级较高，其下方的绿色为较低优先级。  

在[图 27](#figure-27)中，请求由 `www.bing.com` 左侧的一条线、中间有一个深色部分和一个浅色部分以及右侧的线条表示。  [图 28](#figure-28)显示了 "**网络**" 面板的 "**计时**" 选项卡中相同请求的对应表示形式。  下面介绍这两种表示形式如何相互映射：

*   左侧线条是所有 `Connection Start` 事件组中的所有内容，包括一组事件。  换句话说，它是在独占之前的所有内容 `Request Sent` 。  
*   条的灯部分为 `Request Sent` 和 `Waiting (TTFB)` 。  
*   条的深色部分为 `Content Download` 。  
*   右线实质上是等待主线程所用的时间。  这不在 "**计时**" 选项卡中表示。  

> ##### 图27  
> 请求的行条形图表示形式 `www.bing.com`  
> ![Www.bing.com 请求的行条形图表示形式][ImageLineBar]  

> ##### 图28  
> 请求的**计时**选项卡表示形式 `www.bing.com`  
> !["网络" 部分][ImageTiming]  

### 查看内存度量值   

启用 "**内存**" 复选框以查看上次录制中的内存指标。  

> ##### 图29  
> "**内存**" 复选框  
> !["内存" 复选框][ImageMemory]  

DevTools 将在 "**摘要**" 选项卡上方显示一个新的 "**内存**" 图表。 **NET**图表下方还有一个新图表，称为**堆**。  **堆**图表提供的信息与**内存**图表中的**JS 堆**行相同。  

> ##### 图30  
> 内存指标，在 "**摘要**" 选项卡上方  
> ![内存指标][ImageMemoryMetrics]  

图表上的彩色线条将映射到图表上方的彩色复选框。  
禁用复选框以从图表中隐藏该类别。  

图表仅显示当前所选录制的区域。  例如，在[图 30](#figure-30)中，**内存**图表仅显示 400 ms 标记到 1750 ms 标记之间的内存使用。  

### 查看部分录制的持续时间   

分析类似于**网络**或**主**分区的分区时，有时需要对特定事件所花费的时间进行更精确的估计。  按住 `Shift` ，单击并按住，然后向左或向右拖动以选择部分录制。  在所选内容的底部，DevTools 显示该部分花费的时间。  

> ##### 图31  
> `9.47ms`所选部分底部的时间戳表示该部分所花费的时间。  
> ![查看部分录制的持续时间][ImageDuration]  

### 查看屏幕截图   

请参阅[在录制时捕获屏幕截图](#capture-screenshots-while-recording)，了解如何启用屏幕截图。  

将鼠标悬停在**概述**上以查看屏幕的屏幕截图，了解在录制期间如何查看页面。  **概述**是包含**CPU**、 **FPS**和**NET**图表的部分。  

> ##### 图32  
> 查看屏幕截图  
> ![查看屏幕截图][ImageViewScreenshot]  

您也可以通过单击 "**框架**" 部分中的帧来查看屏幕截图。  DevTools 在 "**摘要**" 选项卡中显示小版本的屏幕截图。  

> ##### 图33  
> 单击 " `233.9ms` **框架**" 部分中的帧后，将在 "**摘要**" 选项卡中显示该帧的屏幕截图。  
> ![在 "摘要" 选项卡中查看屏幕截图][ImageFrameScreenshotSummary]  

单击 "**摘要**" 选项卡中的缩略图以放大屏幕截图。  

> ##### 图34  
> 单击 "**摘要**" 选项卡中的缩略图后，DevTools 将放大屏幕截图  
> ![从 "摘要" 选项卡放大屏幕截图][ImageFrameScreenshotZoom]  

### 查看层信息   

要查看有关框架的高级图层信息，请执行以下操作：  

1.  [启用高级画图工具](#enable-advanced-paint-instrumentation)。  
1.  在 "**框架**" 部分中选择一个帧。  DevTools 显示 "新建**图层**" 选项卡上 "**事件日志**" 选项卡旁边的图层的信息。  
    
    > ##### 图35  
    > "**图层**" 窗格  
    > !["图层" 窗格][ImageLayers]  
    
将鼠标悬停在某个图层上，将其在图表中突出显示。  

> ##### 图36  
> 突出显示图层 **#39**  
> ![突出显示图层][ImageLayerHover]  

若要移动图表，请执行以下操作：  

*   单击 "**平移模式** ![ 平移模式 ][ImagePanModeIcon] " 沿 X 轴和 Y 轴移动。  
*   单击 "**旋转模式** ![ 旋转模式 ][ImageRotateModeIcon] " 沿 Z 轴旋转。  
*   单击 "**重置转换** ![ 重置转换" ][ImageResetTransformIcon] 以将图表重置为原始位置。  

### 查看画图档案器   

若要查看有关画图事件的高级信息，请执行以下操作：  

1.  [启用高级画图工具](#enable-advanced-paint-instrumentation)。  
1.  在 "**主要**" 部分中选择一个**绘制**事件。  
    
    > ##### 图37  
    > "**画图" 事件探查器**选项卡  
    > !["画图" 事件探查器选项卡][ImagePaintProfiler]  
    
## 通过 "渲染" 选项卡分析渲染性能   

使用 "**呈现**" 选项卡的功能来帮助可视化页面的呈现性能。  

若要打开 "**呈现**" 选项卡：  

1.  [打开 "命令" 菜单][DevToolsCommandMenu]。  
1.  开始键入 `Rendering` 并选择 `Show Rendering` 。  DevTools 显示 DevTools 窗口底部的 "**呈现**" 选项卡。  
    
    > ##### 图38  
    > "**呈现**" 选项卡  
    > !["呈现" 选项卡][ImageRenderingTab]  
    
### 以 FPS 计量器实时查看每秒帧数   

**FPS 指示器**是出现在视区右上角的覆盖图。  它在页面运行时提供对 FPS 的实时估计。  要打开**FPS 指示器**，请执行以下操作：  

1.  打开 "**呈现**" 选项卡。 请参阅[用渲染选项卡分析渲染性能](#analyze-rendering-performance-with-the-rendering-tab)。  
1.  启用 " **FPS 指示器**" 复选框。  
    
    > ##### 图39  
    > FPS 指示器  
    > ![FPS 指示器][ImageFpsMeter]  
    
### 通过画图闪烁实时查看绘图事件   

使用 "绘画闪烁" 获取页面上的所有绘制事件的实时视图。  只要重新绘制了页面的一部分，DevTools 将以绿色显示该部分。  

启用画图闪烁：  

1.  打开 "**呈现**" 选项卡。 请参阅[用渲染选项卡分析渲染性能](#analyze-rendering-performance-with-the-rendering-tab)。  
1.  启用 "**绘画闪烁**" 复选框。  
    
    > ##### 图40  
    > **绘画闪烁**  
    > ![绘画闪烁][ImagePaintFlashing]  
    
### 查看带有图层边框的图层叠加   

使用**图层边框**查看图层边框和图块在页面顶部的覆盖图。  

要启用图层边框，请执行以下操作：  

1.  打开 "**呈现**" 选项卡。 请参阅[用渲染选项卡分析渲染性能](#analyze-rendering-performance-with-the-rendering-tab)。  
1.  启用 "**图层边框**" 复选框。  
    
    > ##### 图41  
    > **图层边框**  
    > ![图层边框][ImageLayerBorders]  
    
有关颜色 codings 的说明，请参阅中的批注 [`debug_colors.cc`][ChromiumDebugColors] 。  

### 查找实时滚动性能问题   

使用滚动性能问题来标识页面中具有与滚动相关的事件侦听器的元素，这些事件侦听器可能会损害页面的性能。  
DevTools 概述了蓝色的有问题的元素。  

要查看滚动性能问题，请执行以下操作：  

1.  打开 "**呈现**" 选项卡。 请参阅[用渲染选项卡分析渲染性能](#analyze-rendering-performance-with-the-rendering-tab)。  
1.  启用 "**滚动性能问题**" 复选框。  
 
    > ##### 图42  
    > **滚动性能问题**表示非层视区约束的对象可能会损害滚动性能  
    > ![滚动性能问题表示非层视区约束的对象可能会损害滚动性能][ImageScrollingPerformanceIssues]  
    

<!--    -->  



<!-- image links -->  

[ImageCaptureSettingsIcon]: /microsoft-edge/devtools-guide-chromium/media/capture-settings-icon.msft.png  
[ImageClearRecordingIcon]: /microsoft-edge/devtools-guide-chromium/media/clear-recording-icon.msft.png  
[ImageCollectGarbageIcon]: /microsoft-edge/devtools-guide-chromium/media/collect-garbage-icon.msft.png  
[ImageNextIcon]: /microsoft-edge/devtools-guide-chromium/media/next-icon.msft.png  
[ImagePanModeIcon]: /microsoft-edge/devtools-guide-chromium/media/pan-mode-icon.msft.png  
[ImagePreviousIcon]: /microsoft-edge/devtools-guide-chromium/media/previous-icon.msft.png  
[ImageRecordIcon]: /microsoft-edge/devtools-guide-chromium/media/record-icon.msft.png
[ImageRefreshPageIcon]: /microsoft-edge/devtools-guide-chromium/media/refresh-page-icon.msft.png  
[ImageResetTransformIcon]: /microsoft-edge/devtools-guide-chromium/media/reset-transform-icon.msft.png  
[ImageRotateModeIcon]: /microsoft-edge/devtools-guide-chromium/media/rotate-mode-icon.msft.png  
[ImageSearchCaseIcon]: /microsoft-edge/devtools-guide-chromium/media/search-case-icon.msft.png  
[ImageSearchRegexIcon]: /microsoft-edge/devtools-guide-chromium/media/search-regex-icon.msft.png  
[ImageShowHeaviestStackIcon]: /microsoft-edge/devtools-guide-chromium/media/show-heaviest-stack-icon.msft.png  

[ImageRecord]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-record-highlight.msft.png "图1：记录"  
[ImageRefreshPage]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-refresh-button.msft.png "图2：刷新页面"  
[ImageLoadRecording]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-refreshed.msft.png "图3：页面加载录制"  
[ImageScreenshots]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-capture-screenshots-checkbox.msft.png "图4： "屏幕截图" 复选框"  
[ImageCollectGarbage]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-collect-garbage-button.msft.png "图5：收集垃圾"  
[ImageCaptureSettings]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-capture-settings-button-open-drawer.msft.png "图6： "捕获设置" 部分"  
[ImageJSSamplesDisabled]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-on.msft.png "图7：在禁用 JS 样本时录制的示例"  
[ImageJSSamplesEnabled]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-off.msft.png "图8：启用了 JS 样本时录制的示例"  
[ImageSaveProfile]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-off-save-profile.msft.png "图9：保存配置文件"  
[ImageLoadProfile]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-off-load-profile.msft.png "图10：加载配置文件"  
[ImageClearRecording]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-off-clear-button.msft.png "图11：清除录制"  
[ImageZoom]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-zoom-highlighted.msft.png "图12：在概述中拖动鼠标以缩放"  
[ImageSearch]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-search-regex.msft.png "图13： "搜索" 框"  
[ImageMain]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-main-zoomed.msft.png "图14：主要部分"  
[ImageMainEventSummary]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-summary-me.msft.png "图15：有关 "摘要" 选项卡中的匿名函数的详细信息"  
[ImageFlameChart]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-main-flame-chart.msft.png "图16：火焰图"  
[ImageCallTree]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-call-tree.msft.png "图17： "调用树" 选项卡"  
[ImageBottomUp]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-bottoms-up.msft.png "图18：自下而上的选项卡"  
[ImageEventLog]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-event-log.msft.png "图19： "事件日志" 选项卡"  
[ImageGpu]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-gpu-zoomed.msft.png "图20： GPU 部分"  
[ImageRaster]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-raster.msft.png "图21： "光栅" 部分"  
[ImageInteractions]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-interactions-animation.msft.png "图22： "交互" 部分"  
[ImageFpsChart]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-fps-highlight.msft.png "图23： FPS 图表"  
[ImageFramesSection]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-frames-hover.msft.png "图24：将鼠标悬停在框架上"  
[ImageFrameSummary]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-frames-summary.msft.png "图25：在 "摘要" 选项卡中查看帧"  
[ImageNetworkRequest]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-network.msft.png "图26： "网络" 部分"  
[ImageLineBar]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-bing-performance-network.msft.png "图27： www.bing.com 请求的行条形图表示形式"  
[ImageTiming]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-bing-network-timing.msft.png "图28： "网络" 部分"  
[ImageMemory]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-memory-highlight.msft.png "图29： "内存" 复选框"  
[ImageMemoryMetrics]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-memory-chart.msft.png "图30：内存指标"  
[ImageDuration]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-main-duration.msft.png "图31：查看部分录制的持续时间"  
[ImageViewScreenshot]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-screenshots-hover.msft.png "图32：查看屏幕截图"  
[ImageFrameScreenshotSummary]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-summary-preview.msft.png "图33：在 "摘要" 选项卡中查看屏幕截图"  
[ImageFrameScreenshotZoom]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-summary-preview-select.msft.png "图34：放大 "摘要" 选项卡上的屏幕截图"  
[ImageLayers]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-layers-all.msft.png "图35： "层" 窗格"  
[ImageLayerHover]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-frames-document-nav-bar-highlighted.msft.png "图36：突出显示图层"  
[ImagePaintProfiler]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-paint-profiler.msft.png "图37： "画图" 事件探查器选项卡"  
[ImageRenderingTab]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-console-drawer-rendering.msft.png "图38： "呈现" 选项卡"  
[ImageFpsMeter]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-jank-console-rendering-frame-rate.msft.png "图39： FPS 指示器"  
[ImagePaintFlashing]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-jank-console-rendering-paint-flashing.msft.png "图40：绘画闪烁"  
[ImageLayerBorders]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-devtools-console-rendering-layer-borders.msft.png "图41：图层边框"  
[ImageScrollingPerformanceIssues]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-bing-console-drawer-rendering-scrolling-performance-issues.msft.png "图42：滚动性能问题指示非层视区约束的对象可能会损害滚动性能"  

<!-- links -->  

[MicrosoftEdgeDevTools]: /microsoft-edge/devtools-guide-chromium "Microsoft Edge （Chromium）开发人员工具"  
[DevToolsCommandMenu]: /microsoft-edge/devtools-guide-chromium/command-menu/index#open-the-command-menu "通过 Microsoft Edge DevTools "命令" 菜单打开命令菜单-运行命令"  
[DevtoolsEvaluatePerformanceGettingStarted]: /microsoft-edge/devtools-guide-chromium/evaluate-performance/index "分析运行时性能入门"  

[ActivityTabsDemo]: https://microsoft-edge-chromium-devtools.glitch.me/perf/activitytabs.html "活动选项卡演示"  

[ChromiumDebugColors]: https://cs.chromium.org/chromium/src/cc/debug/debug_colors.cc "debug_colors 抄送-代码搜索"  

> [!NOTE]
> 此页面的某些部分是基于[由 Google][GoogleSitePolicies]创建和共享的工作的修改，并根据 "[创造性 Commons 归属4.0 国际许可证][CCA4IL]" 中所述的条款使用。  
> 原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/evaluate-performance/reference)，由[Kayce Basques][KayceBasques] \ （技术作者、Chrome DevTools \ & Lighthouse \）创作。  

[![创造性 Commons 许可证][CCby4Image]][CCA4IL]  
此作品通过 [Creative Commons Attribution 4.0 国际许可证][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  