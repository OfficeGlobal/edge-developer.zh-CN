---
description: 在 Windows 窗体应用中将 web 内容与 Microsoft Edge Web 视图2控件一起托管
title: 适用于 Windows 表单应用的 Microsoft Edge Web 视图2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/12/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、WebView2、Web 视图、web 视图、winforms 应用、winforms、edge、CoreWebView2、浏览器控件、边缘 html、入门、入门、.NET、windows 窗体
ms.openlocfilehash: b2616eeed2a8e896889e2cc1a395c401a8aad435
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2020
ms.locfileid: "10652940"
---
# <span data-ttu-id="7e619-104">Windows 窗体应用中的 WebView2 入门（预览版）</span><span class="sxs-lookup"><span data-stu-id="7e619-104">Getting Started with WebView2 in Windows Forms apps (Preview)</span></span>  

<span data-ttu-id="7e619-105">在本文中，开始创建你的第一个 WebView2 应用，并了解[WebView2 （预览版）](/microsoft-edge/hosting/webview2/index)的主要功能。</span><span class="sxs-lookup"><span data-stu-id="7e619-105">In this article, get started creating your first WebView2 app and learn about the main features of [WebView2 (preview)](/microsoft-edge/hosting/webview2/index).</span></span>  <span data-ttu-id="7e619-106">有关单个 Api 的详细信息，请参阅[API 参考](../reference/dotnet/0-9-515-reference-webview2.md)。</span><span class="sxs-lookup"><span data-stu-id="7e619-106">For more information on individual APIs, see [API reference](../reference/dotnet/0-9-515-reference-webview2.md).</span></span>  

## <span data-ttu-id="7e619-107">必备条件</span><span class="sxs-lookup"><span data-stu-id="7e619-107">Prerequisites</span></span>  

<span data-ttu-id="7e619-108">请确保在继续之前安装了以下先决条件列表：</span><span class="sxs-lookup"><span data-stu-id="7e619-108">Ensure you installed the following list of pre-requisites before proceeding:</span></span>  

* <span data-ttu-id="7e619-109">安装在 Windows 10、Windows 8.1 或 Windows 7 上的[Microsoft Edge （Chromium）](https://www.microsoftedgeinsider.com/download/) 。</span><span class="sxs-lookup"><span data-stu-id="7e619-109">[Microsoft Edge (Chromium)](https://www.microsoftedgeinsider.com/download/) installed on Windows 10, Windows 8.1, or Windows 7.</span></span>  <span data-ttu-id="7e619-110">Microsoft Edge Web 视图团队建议使用 "未带" 通道。</span><span class="sxs-lookup"><span data-stu-id="7e619-110">The Microsoft Edge WebView team recommends using the Canary channel.</span></span>  
* <span data-ttu-id="7e619-111">[Visual Studio](https://visualstudio.microsoft.com/) 2015 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="7e619-111">[Visual Studio](https://visualstudio.microsoft.com/) 2015 or later.</span></span>

> [!NOTE]
> <span data-ttu-id="7e619-112">如果通过**Windows Forms .Net Core 3.0 或 .net 5**进行开发，请下载[Visual Studio （预览版）](https://visualstudio.microsoft.com/vs/preview/)</span><span class="sxs-lookup"><span data-stu-id="7e619-112">If developing with **Windows Forms .NET Core 3.0 or .NET 5**, download [Visual Studio (Preview)](https://visualstudio.microsoft.com/vs/preview/)</span></span>

## <span data-ttu-id="7e619-113">步骤 1-创建单个窗口应用程序</span><span class="sxs-lookup"><span data-stu-id="7e619-113">Step 1 - Create a single window application</span></span>

<span data-ttu-id="7e619-114">从包含单个主窗口的基本桌面项目开始。</span><span class="sxs-lookup"><span data-stu-id="7e619-114">Start with a basic desktop project containing a single main window.</span></span>  

1. <span data-ttu-id="7e619-115">打开**Visual Studio。**</span><span class="sxs-lookup"><span data-stu-id="7e619-115">Open **Visual Studio.**</span></span>

2. <span data-ttu-id="7e619-116">选择 " **Windows 窗体 .Net Framework 应用**" 或 " **windows 窗体 .net Core app**"，然后选择 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="7e619-116">Choose **Windows Forms .NET Framework App** or **Windows Forms .NET Core App**, and then choose **Next**.</span></span>

    ![newproject](./media/winforms-newproject.png)

3. <span data-ttu-id="7e619-118">输入 "**项目名称**" 和 "**位置**" 值。</span><span class="sxs-lookup"><span data-stu-id="7e619-118">Enter values for **Project name** and **Location**.</span></span>  <span data-ttu-id="7e619-119">选择 " **.Net Framework 4.6.2**或更高版本" 或 " **.net Core 3.0**或更高版本"。</span><span class="sxs-lookup"><span data-stu-id="7e619-119">Select **.NET Framework 4.6.2** or later, or **.NET Core 3.0** or later.</span></span>  

    ![startproject](./media/winforms-startproj.png)

4. <span data-ttu-id="7e619-121">选择 "**创建**" 以创建你的项目。</span><span class="sxs-lookup"><span data-stu-id="7e619-121">Choose **Create** to create your project.</span></span>

## <span data-ttu-id="7e619-122">步骤 2-安装 WebView2 SDK</span><span class="sxs-lookup"><span data-stu-id="7e619-122">Step 2 - Install WebView2 SDK</span></span>

<span data-ttu-id="7e619-123">接下来，将 WebView2 SDK 添加到项目。</span><span class="sxs-lookup"><span data-stu-id="7e619-123">Next add the WebView2 SDK to the project.</span></span>  <span data-ttu-id="7e619-124">对于预览，使用 Nuget 安装 WebView2 SDK。</span><span class="sxs-lookup"><span data-stu-id="7e619-124">For the preview, install the WebView2 SDK using Nuget.</span></span>  

1. <span data-ttu-id="7e619-125">打开项目上的上下文菜单 \ （右键单击 \），然后选择 "**管理 NuGet 程序包 ...**"。</span><span class="sxs-lookup"><span data-stu-id="7e619-125">Open the context menu on the project \(right-click\), and choose **Manage NuGet Packages...**.</span></span>  

    :::image type="complex" source="./media/wpf-gettingstarted-mngnuget.png" alt-text="Nuget.exe":::
       <span data-ttu-id="7e619-127">Nuget.exe</span><span class="sxs-lookup"><span data-stu-id="7e619-127">Nuget</span></span> :::image-end:::

2. <span data-ttu-id="7e619-128">`Microsoft.Web.WebView2`在搜索栏中输入。</span><span class="sxs-lookup"><span data-stu-id="7e619-128">Enter `Microsoft.Web.WebView2` in the search bar.</span></span>  <span data-ttu-id="7e619-129">从搜索结果中选择 " **WebView2** "。</span><span class="sxs-lookup"><span data-stu-id="7e619-129">Choose **Microsoft.Web.WebView2** from the search results.</span></span>  <span data-ttu-id="7e619-130">将 "程序包版本" 设置为 "**预发布**"，然后选择 "**安装**"。</span><span class="sxs-lookup"><span data-stu-id="7e619-130">Set the package version to **pre-release**, and then choose **Install**.</span></span>  

    ![nuget.exe](./media/installnuget.png)

<span data-ttu-id="7e619-132">全部设置为使用 WebView2 API 开始开发应用程序。</span><span class="sxs-lookup"><span data-stu-id="7e619-132">You are all set to start developing applications using the WebView2 API.</span></span>  <span data-ttu-id="7e619-133">选择 `F5` 以生成并运行项目。</span><span class="sxs-lookup"><span data-stu-id="7e619-133">Select `F5` to build and run the project.</span></span>  <span data-ttu-id="7e619-134">正在运行的项目显示一个空窗口。</span><span class="sxs-lookup"><span data-stu-id="7e619-134">The running project displays an empty window.</span></span>  

![emptyApp](./media/winforms-emptyApp.png)

## <span data-ttu-id="7e619-136">步骤 3-创建单个 Web 视图</span><span class="sxs-lookup"><span data-stu-id="7e619-136">Step 3 - Create a single WebView</span></span>  

<span data-ttu-id="7e619-137">接下来，将 Web 视图添加到你的应用程序。</span><span class="sxs-lookup"><span data-stu-id="7e619-137">Next add a WebView to your application.</span></span>  

1. <span data-ttu-id="7e619-138">打开**Windows 窗体设计器**。</span><span class="sxs-lookup"><span data-stu-id="7e619-138">Open the **Windows Forms Designer**.</span></span>  
2. <span data-ttu-id="7e619-139">在**工具箱**中搜索**WebView2** 。</span><span class="sxs-lookup"><span data-stu-id="7e619-139">Search for **WebView2** in the **Toolbox**.</span></span> <span data-ttu-id="7e619-140">将**WebView2**控件拖放到 Windows Forms 应用中</span><span class="sxs-lookup"><span data-stu-id="7e619-140">Drag and drop the **WebView2** control into the Windows Forms App</span></span>

    ![>](./media/winforms-toolbox.png)

3. <span data-ttu-id="7e619-142">将 `Name` 属性更改为 `webView`。</span><span class="sxs-lookup"><span data-stu-id="7e619-142">Change the `Name` property to `webView`.</span></span>

    ![>](./media/winforms-properties.png)

4. <span data-ttu-id="7e619-144">该 `Source` 属性设置 WebView2 控件中显示的初始 URI。</span><span class="sxs-lookup"><span data-stu-id="7e619-144">The `Source` property sets the initial URI displayed in the WebView2 control.</span></span> <span data-ttu-id="7e619-145">将 Source 属性设置为</span><span class="sxs-lookup"><span data-stu-id="7e619-145">Set the Source property to</span></span> <https://www.microsoft.com>

    ![>](./media/winforms-source.png)

<span data-ttu-id="7e619-147">选择 `F5` 生成并运行项目。</span><span class="sxs-lookup"><span data-stu-id="7e619-147">Select `F5` to build and run your project.</span></span>  <span data-ttu-id="7e619-148">确认你的 WebView2 控件是否显示 [https://www.microsoft.com](https://www.microsoft.com) 。</span><span class="sxs-lookup"><span data-stu-id="7e619-148">Confirm that your WebView2 control displays [https://www.microsoft.com](https://www.microsoft.com).</span></span>

![hellowebview](./media/winforms-hellowebview.png)

> [!NOTE]
> <span data-ttu-id="7e619-150">如果您使用的是高 DPI 监视器，则可能需要为[高 dpi 支持配置 Windows 窗体应用](https://docs.microsoft.com/dotnet/framework/winforms/high-dpi-support-in-windows-forms#configuring-your-windows-forms-app-for-high-dpi-support)。</span><span class="sxs-lookup"><span data-stu-id="7e619-150">If you are working on a high DPI monitor, you may have to [configure your Windows Forms app for high DPI support](https://docs.microsoft.com/dotnet/framework/winforms/high-dpi-support-in-windows-forms#configuring-your-windows-forms-app-for-high-dpi-support).</span></span>

## <span data-ttu-id="7e619-151">步骤 4-处理窗口调整大小事件</span><span class="sxs-lookup"><span data-stu-id="7e619-151">Step 4 - Handle Window Resize Events</span></span>

<span data-ttu-id="7e619-152">将更多控件从工具箱添加到 Windows 窗体，然后相应地处理窗口大小调整事件。</span><span class="sxs-lookup"><span data-stu-id="7e619-152">Add a few more controls to your Windows Forms from the toolbox, and then handle window resize events appropriately.</span></span>

1. <span data-ttu-id="7e619-153">在**Windows 窗体设计器**中打开**工具箱**</span><span class="sxs-lookup"><span data-stu-id="7e619-153">In the **Windows Forms Designer** open the **Toolbox**</span></span>
2. <span data-ttu-id="7e619-154">将**TextBox**拖放到 Windows Forms 应用中。</span><span class="sxs-lookup"><span data-stu-id="7e619-154">Drag and Drop a **TextBox** into the Windows Forms App.</span></span> <span data-ttu-id="7e619-155">**TextBox** `addressBar` 在 "**属性" 选项卡**中命名文本框。</span><span class="sxs-lookup"><span data-stu-id="7e619-155">Name the **TextBox** `addressBar` in the **Properties Tab**.</span></span>
3. <span data-ttu-id="7e619-156">将**按钮**拖放到 Windows 窗体应用中。</span><span class="sxs-lookup"><span data-stu-id="7e619-156">Drag and Drop a **Button** into the Windows Forms App.</span></span> <span data-ttu-id="7e619-157">将**按钮**中的文本更改为 `Go!` 并在**Button** `goButton` "**属性" 选项卡**中命名该按钮。</span><span class="sxs-lookup"><span data-stu-id="7e619-157">Change the text in the **Button** to `Go!` and name the **Button** `goButton` in the **Properties Tab**.</span></span>

<span data-ttu-id="7e619-158">应用在设计器中的外观应如下所示：</span><span class="sxs-lookup"><span data-stu-id="7e619-158">The app should look like the following in the designer:</span></span>

![设计器](./media/winforms-designer.png)

4. <span data-ttu-id="7e619-160">在**Form1.cs**定义 `Form_Resize` 以在调整应用窗口大小时保持控件的位置。</span><span class="sxs-lookup"><span data-stu-id="7e619-160">In **Form1.cs** define `Form_Resize` to keep the controls in place when the App Window is resized.</span></span>

```csharp
public Form1()
{
    InitializeComponent();
    this.Resize += new System.EventHandler(this.Form_Resize);
}

private void Form_Resize(object sender, EventArgs e)
{
    webView.Size = this.ClientSize - new System.Drawing.Size(webView.Location);
    goButton.Left = this.ClientSize.Width - goButton.Width;
    addressBar.Width = goButton.Left - addressBar.Left;
}
```

<span data-ttu-id="7e619-161">选择 `F5` 生成并运行项目。</span><span class="sxs-lookup"><span data-stu-id="7e619-161">Select `F5` to build and run your project.</span></span>  <span data-ttu-id="7e619-162">确认应用显示类似于以下屏幕截图。</span><span class="sxs-lookup"><span data-stu-id="7e619-162">Confirm that the app displays similar to the following screenshot.</span></span>

![应用](./media/winforms-app.png)

## <span data-ttu-id="7e619-164">步骤 5-导航</span><span class="sxs-lookup"><span data-stu-id="7e619-164">Step 5 - Navigation</span></span>

<span data-ttu-id="7e619-165">添加允许用户通过向应用添加地址栏来更改 WebView2 控件显示的 URL 的功能。</span><span class="sxs-lookup"><span data-stu-id="7e619-165">Add the ability to allow users to change the URL that the WebView2 control displays by adding an address bar to the app.</span></span>

1. <span data-ttu-id="7e619-166">在 `Form1.cs` "添加命名空间" 中，将 `CoreWebView2` 以下代码片段插入到顶部 `Form1.cs` 。</span><span class="sxs-lookup"><span data-stu-id="7e619-166">In `Form1.cs` add the `CoreWebView2` namespace by inserting the following code snippet at the top of `Form1.cs`.</span></span>  

    ```csharp
    using Microsoft.Web.WebView2.Core;
    ```

2. <span data-ttu-id="7e619-167">在**Windows 窗体设计器**中，双击 `Go!` 要在其中创建方法的按钮 `goButton_Click` `Form1.cs` 。</span><span class="sxs-lookup"><span data-stu-id="7e619-167">In the **Windows Forms Designer**, double-click on the `Go!` button to create the `goButton_Click` method in `Form1.cs`.</span></span> <span data-ttu-id="7e619-168">在函数内复制并粘贴以下代码段。</span><span class="sxs-lookup"><span data-stu-id="7e619-168">Copy and paste the following snippet inside the function.</span></span> <span data-ttu-id="7e619-169">现在，该 `goButton_Click` 函数将 Web 视图导航到在地址栏中输入的 URL。</span><span class="sxs-lookup"><span data-stu-id="7e619-169">Now, the `goButton_Click` function navigates the WebView to the URL entered in the address bar.</span></span>

    ```csharp
    private void goButton_Click(object sender, EventArgs e)
    {
        if (webView != null && webView.CoreWebView2 != null)
        {
            webView.CoreWebView2.Navigate(addressBar.Text);
        }
    }
    ```  

<span data-ttu-id="7e619-170">选择 `F5` 生成并运行项目。</span><span class="sxs-lookup"><span data-stu-id="7e619-170">Select `F5` to build and run your project.</span></span>  <span data-ttu-id="7e619-171">在地址栏中输入新的 URL，然后单击 "**转到**"。</span><span class="sxs-lookup"><span data-stu-id="7e619-171">Enter a new URL in the address bar, and click **Go**.</span></span>  <span data-ttu-id="7e619-172">例如，enter `https://www.bing.com` 。</span><span class="sxs-lookup"><span data-stu-id="7e619-172">For example, enter `https://www.bing.com`.</span></span>  <span data-ttu-id="7e619-173">确认 WebView2 控件导航到 URL。</span><span class="sxs-lookup"><span data-stu-id="7e619-173">Confirm that the WebView2 control navigates to the URL.</span></span>  

> [!NOTE]
> <span data-ttu-id="7e619-174">确保在地址栏中输入完整的 URL。</span><span class="sxs-lookup"><span data-stu-id="7e619-174">Ensure a complete URL is entered in the address bar.</span></span> <span data-ttu-id="7e619-175">`ArgumentException`如果 URL 不以 or 开头的 URL，则会引发 `http://`</span><span class="sxs-lookup"><span data-stu-id="7e619-175">An `ArgumentException` is thrown if the URL does not start with `http://` or</span></span> `https://`

![bing](./media/winforms-bing.png)

## <span data-ttu-id="7e619-177">步骤 6-导航事件</span><span class="sxs-lookup"><span data-stu-id="7e619-177">Step 6 - Navigation events</span></span>  

<span data-ttu-id="7e619-178">托管 WebView2 控件的应用程序将侦听在导航到网页期间由 WebView2 控件引发的以下事件。</span><span class="sxs-lookup"><span data-stu-id="7e619-178">The application that hosts WebView2 controls listens to the following events that are raised by the WebView2 control during navigation to web pages.</span></span>  

* `NavigationStarting`  
* `SourceChanged`  
* `ContentLoading`  
* `HistoryChanged`  
* `NavigationCompleted`  

<span data-ttu-id="7e619-179">有关详细信息，请参阅[导航事件](../reference/win32/0-9-488/icorewebview2.md#navigation-events)。</span><span class="sxs-lookup"><span data-stu-id="7e619-179">For more information, see [Navigation Events](../reference/win32/0-9-488/icorewebview2.md#navigation-events).</span></span>  

:::image type="complex" source="../media/navigation-events.png" alt-text="导航事件":::
   <span data-ttu-id="7e619-181">导航事件</span><span class="sxs-lookup"><span data-stu-id="7e619-181">Navigation events</span></span>
:::image-end:::

<span data-ttu-id="7e619-182">当发生错误时，将引发以下事件，并可能依赖于导航到错误页面。</span><span class="sxs-lookup"><span data-stu-id="7e619-182">When an error occurs, the following events are raised and may depend on navigation to an error page.</span></span>  

* `SourceChanged`  
* `ContentLoading`  
* `HistoryChanged`  

<span data-ttu-id="7e619-183">当存在 HTTP 重定向时，有多个 `NavigationStarting` 事件。</span><span class="sxs-lookup"><span data-stu-id="7e619-183">When there is an HTTP redirect, there are multiple `NavigationStarting` events.</span></span>  

<span data-ttu-id="7e619-184">若要演示如何使用这些事件，请首先注册 `NavigationStarting` 一个用于取消任何不使用 HTTPS 的请求的处理程序。</span><span class="sxs-lookup"><span data-stu-id="7e619-184">To demonstrate how to use these events, start by registering a handler for `NavigationStarting` that cancels any requests that do not use HTTPS.</span></span>  

<span data-ttu-id="7e619-185">在中 `Form1.cs` ，修改构造函数，如下所示，并添加 `EnsureHttps` 函数。</span><span class="sxs-lookup"><span data-stu-id="7e619-185">In `Form1.cs`, modify the constructor as shown below and add the `EnsureHttps` function.</span></span>  

```csharp
public Form1()
{
    InitializeComponent();
    this.Resize += new System.EventHandler(this.Form_Resize);

    webView.NavigationStarting += EnsureHttps;
}

void EnsureHttps(object sender, CoreWebView2NavigationStartingEventArgs args)
{
    String uri = args.Uri;
    if (!uri.StartsWith("https://"))
    {
        args.Cancel = true;
    }
}
```

<span data-ttu-id="7e619-186">在构造函数中，EnsureHttps 将注册为 WebView2 控件上事件的事件处理程序 `NavigationStarting` 。</span><span class="sxs-lookup"><span data-stu-id="7e619-186">In the constructor, EnsureHttps is registered as the event handler on the `NavigationStarting` event on the WebView2 control.</span></span>  

<span data-ttu-id="7e619-187">选择 `F5` 生成并运行项目。</span><span class="sxs-lookup"><span data-stu-id="7e619-187">Select `F5` to build and run your project.</span></span> <span data-ttu-id="7e619-188">确认在导航到 HTTP 站点时，Web 视图保持不变。</span><span class="sxs-lookup"><span data-stu-id="7e619-188">Confirm that when navigating to an HTTP site, the WebView remains unchanged.</span></span> <span data-ttu-id="7e619-189">但是，Web 视图将导航到 HTTPS 站点。</span><span class="sxs-lookup"><span data-stu-id="7e619-189">However, the WebView will navigate to HTTPS sites.</span></span>

## <span data-ttu-id="7e619-190">步骤 7-脚本</span><span class="sxs-lookup"><span data-stu-id="7e619-190">Step 7 - Scripting</span></span>  

<span data-ttu-id="7e619-191">在运行时，你可以使用主机应用程序将 JavaScript 代码注入 WebView2 控件。</span><span class="sxs-lookup"><span data-stu-id="7e619-191">You may use host applications to inject JavaScript code into WebView2 controls at runtime.</span></span>  <span data-ttu-id="7e619-192">插入的 JavaScript 将应用于所有新的顶级文档和任何子框架，直到删除了 JavaScript。</span><span class="sxs-lookup"><span data-stu-id="7e619-192">The injected JavaScript applies to all new top level documents and any child frames until the JavaScript is removed.</span></span>  <span data-ttu-id="7e619-193">插入的 JavaScript 将在创建全局对象后以及 HTML 文档中包含的任何其他脚本运行之前运行。</span><span class="sxs-lookup"><span data-stu-id="7e619-193">The injected JavaScript is run after creation of the global object, and before any other script included in the HTML document is run.</span></span>  

<span data-ttu-id="7e619-194">导航到非 HTTPS 网站时，可以使用脚本来提醒用户。</span><span class="sxs-lookup"><span data-stu-id="7e619-194">You can use scripting to alert the user when navigating to a non-HTTPS site.</span></span>  <span data-ttu-id="7e619-195">修改该 `EnsureHttps` 函数，以便它使用[ExecuteScriptAsync]()方法将脚本插入 web 内容。</span><span class="sxs-lookup"><span data-stu-id="7e619-195">Modify the `EnsureHttps` function so that it injects script into the web content using the [ExecuteScriptAsync]() method.</span></span>  

```csharp
void EnsureHttps(object sender, CoreWebView2NavigationStartingEventArgs args)
{
    String uri = args.Uri;
    if (!uri.StartsWith("https://"))
    {
        webView.CoreWebView2.ExecuteScriptAsync($"alert('{uri} is not safe, try an https link')");
        args.Cancel = true;
    }
}
```  

<span data-ttu-id="7e619-196">选择 `F5` 生成并运行项目。</span><span class="sxs-lookup"><span data-stu-id="7e619-196">Select `F5` to build and run your project.</span></span>  <span data-ttu-id="7e619-197">确认当导航到不使用 HTTPS 的网站时，应用程序是否显示警告。</span><span class="sxs-lookup"><span data-stu-id="7e619-197">Confirm that the application displays an alert when you navigate to a site that does not use HTTPS.</span></span>  

![https](./media/winforms-https.png)

## <span data-ttu-id="7e619-199">步骤 8-主机和 web 内容之间的通信</span><span class="sxs-lookup"><span data-stu-id="7e619-199">Step 8 - Communication between host and web content</span></span>  

<span data-ttu-id="7e619-200">宿主和 web 内容可以按如下方式进行通信 `postMessage` ：</span><span class="sxs-lookup"><span data-stu-id="7e619-200">The host and web content may communicate with each other using `postMessage` as follows:</span></span>  

* <span data-ttu-id="7e619-201">WebView2 控件中的 Web 内容可能会使用将消息发布到主机 `window.chrome.webview.postMessage` 。</span><span class="sxs-lookup"><span data-stu-id="7e619-201">Web content in a WebView2 control may post a message to the host using `window.chrome.webview.postMessage`.</span></span>  <span data-ttu-id="7e619-202">主机使用主机上已注册的任何内容处理消息 `WebMessageReceived` 。</span><span class="sxs-lookup"><span data-stu-id="7e619-202">The host handles the message using any registered `WebMessageReceived` on the host.</span></span>  
* <span data-ttu-id="7e619-203">使用 or 将消息发布到 WebView2 控件中的 web `CoreWebView2.PostWebMessageAsString` 内容 `CoreWebView2.PostWebMessageAsJSON` 。</span><span class="sxs-lookup"><span data-stu-id="7e619-203">Hosts post messages to web content in a WebView2 control using `CoreWebView2.PostWebMessageAsString` or `CoreWebView2.PostWebMessageAsJSON`.</span></span>  <span data-ttu-id="7e619-204">这些消息由添加到的处理程序捕获 `window.chrome.webview.addEventListener` 。</span><span class="sxs-lookup"><span data-stu-id="7e619-204">These messages are caught by handlers added to `window.chrome.webview.addEventListener`.</span></span>  

<span data-ttu-id="7e619-205">此通信机制允许 web 内容使用本机功能将消息传递到主机。</span><span class="sxs-lookup"><span data-stu-id="7e619-205">This communication mechanism allows web content to pass messages to the host using native capabilities.</span></span>  

<span data-ttu-id="7e619-206">在你的项目中，当 WebView2 控件导航到 URL 时，它将在地址栏中显示 URL，并向 WebView2 控件中显示的 URL 的用户发出警报。</span><span class="sxs-lookup"><span data-stu-id="7e619-206">In your project, when the WebView2 control navigates to a URL, it displays the URL in the address bar and alerts the user of the URL displayed in the WebView2 control.</span></span>  

1. <span data-ttu-id="7e619-207">在**Form1.cs**中，更新你的构造函数并创建 `InitializeAsync` 函数，如以下代码片段所示。</span><span class="sxs-lookup"><span data-stu-id="7e619-207">In **Form1.cs**, update your constructor and create an `InitializeAsync` function as shown in the following code snippet.</span></span>  <span data-ttu-id="7e619-208">`InitializeAsync`函数会等待[EnsureCoreWebView2Async]() ，因为它的初始化 `CoreWebView2` 是异步的。</span><span class="sxs-lookup"><span data-stu-id="7e619-208">The `InitializeAsync` function awaits [EnsureCoreWebView2Async]() because the initialization of `CoreWebView2` is asynchronous.</span></span>  

    ```csharp
    public Form1()
    {
        InitializeComponent();
        this.Resize += new System.EventHandler(this.Form_Resize);
        webView.NavigationStarting += EnsureHttps;
        InitializeAsync();
    }

    async void InitializeAsync()
    {
        await webView.EnsureCoreWebView2Async(null);
    }
    ```  

2. <span data-ttu-id="7e619-209">初始化**CoreWebView2**后，注册一个事件处理程序以响应 `WebMessageReceived` 。</span><span class="sxs-lookup"><span data-stu-id="7e619-209">After **CoreWebView2** is initialized, register an event handler to respond to `WebMessageReceived`.</span></span>  <span data-ttu-id="7e619-210">在 " `Form1.cs` 更新" `InitializeAsync` 和 " `UpdateAddressBar` 使用以下代码片段添加" 中。</span><span class="sxs-lookup"><span data-stu-id="7e619-210">In `Form1.cs` update `InitializeAsync` and add `UpdateAddressBar` using the following code snippet.</span></span>  

    ```csharp
    async void InitializeAsync()
    {
        await webView.EnsureCoreWebView2Async(null);
        webView.CoreWebView2.WebMessageReceived += UpdateAddressBar;
    }

    void UpdateAddressBar(object sender, CoreWebView2WebMessageReceivedEventArgs args)
    {
        String uri = args.TryGetWebMessageAsString();
        addressBar.Text = uri;
        webView.CoreWebView2.PostWebMessageAsString(uri);
    }
    ```  

3. <span data-ttu-id="7e619-211">为了让 web 视图发送和响应 web 消息，在 `CoreWebView2` 初始化后，主机会将 web 内容中的脚本插入到：</span><span class="sxs-lookup"><span data-stu-id="7e619-211">In order for the WebView to send and respond to the web message, after `CoreWebView2` is initialized, the host injects a script in the web content to:</span></span>  

    1. <span data-ttu-id="7e619-212">使用将 URL 发送给主机 `postMessage` 。</span><span class="sxs-lookup"><span data-stu-id="7e619-212">Send the URL to the host using `postMessage`.</span></span>
    2. <span data-ttu-id="7e619-213">注册一个事件处理程序以打印从主机发送的消息。</span><span class="sxs-lookup"><span data-stu-id="7e619-213">Register an event handler to print a message sent from the host.</span></span>  

<span data-ttu-id="7e619-214">在中 `Form1.cs` ，更新， `InitializeAsync` 如以下代码片段所示。</span><span class="sxs-lookup"><span data-stu-id="7e619-214">In `Form1.cs`, update `InitializeAsync` as shown in the following code snippet.</span></span>  

```csharp
async void InitializeAsync()
{
    await webView.EnsureCoreWebView2Async(null);
    webView.CoreWebView2.WebMessageReceived += UpdateAddressBar;

    await webView.CoreWebView2.AddScriptToExecuteOnDocumentCreatedAsync("window.chrome.webview.postMessage(window.document.URL);");
    await webView.CoreWebView2.AddScriptToExecuteOnDocumentCreatedAsync("window.chrome.webview.addEventListener(\'message\', event => alert(event.data));");
}
```  

<span data-ttu-id="7e619-215">选择 `F5` 生成并运行应用。</span><span class="sxs-lookup"><span data-stu-id="7e619-215">Select `F5` to build and run the app.</span></span>  <span data-ttu-id="7e619-216">确认地址栏显示在 Web 视图中显示的网站的 URL。</span><span class="sxs-lookup"><span data-stu-id="7e619-216">Confirm that the address bar displays the URL of the site displayed in the WebView.</span></span> <span data-ttu-id="7e619-217">此外，当你成功导航到新 URL 时，Web 视图会警告 Web 视图中显示的 URL 的用户。</span><span class="sxs-lookup"><span data-stu-id="7e619-217">Also, when you successfully navigate to a new URL, the WebView alerts the user of the URL displayed in the WebView.</span></span>  

![finalapp](./media/winforms-finalapp.png)

<span data-ttu-id="7e619-219">恭喜，你已构建了你的第一个 WebView2 应用！</span><span class="sxs-lookup"><span data-stu-id="7e619-219">Congratulations, you built your first WebView2 app!</span></span>  

## <span data-ttu-id="7e619-220">后续步骤</span><span class="sxs-lookup"><span data-stu-id="7e619-220">Next Steps</span></span>  

<span data-ttu-id="7e619-221">有关本演练中未涉及的 WebView2 功能的详细信息，请参阅[API 参考](../reference/dotnet/0-9-515-reference-webview2.md)。</span><span class="sxs-lookup"><span data-stu-id="7e619-221">For more information on WebView2 features not covered in this walkthrough, see the [API reference](../reference/dotnet/0-9-515-reference-webview2.md).</span></span>

## <span data-ttu-id="7e619-222">与 Microsoft Edge Web 上的 Web Edge 团队取得联系</span><span class="sxs-lookup"><span data-stu-id="7e619-222">Getting in touch with the Microsoft Edge WebView team</span></span>  

<span data-ttu-id="7e619-223">通过分享你的反馈来帮助构建更丰富的 WebView2 体验！</span><span class="sxs-lookup"><span data-stu-id="7e619-223">Help build a richer WebView2 experience by sharing your feedback!</span></span>  <span data-ttu-id="7e619-224">访问 Microsoft Edge Web 视图[反馈](https://aka.ms/webviewfeedback)存储库以提交功能请求或 bug 报告或搜索已知问题。</span><span class="sxs-lookup"><span data-stu-id="7e619-224">Visit the Microsoft Edge WebView [feedback repo](https://aka.ms/webviewfeedback) to submit feature requests or bug reports or search for known issues.</span></span>  