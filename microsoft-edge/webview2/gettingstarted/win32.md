---
description: 适用于 Win32 应用的 WebView2 入门指南
title: 适用于 Win32 应用的 WebView2 入门
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/19/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: 20d830e2c8b95213b223da46f9afd9f69a137946
ms.sourcegitcommit: af91bfc3e6d8afc51f0fbbc0fe392262f424225c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/19/2020
ms.locfileid: "11120380"
---
# WebView2 入门  

以下内容将指导你完成 [WebView2][Webview2Index] 的常用功能，并提供了创建你的第一个 WebView2 应用的起始点。  有关单个 WebView2 Api 的详细信息，请参阅 [API 参考][Webview2ReferenceWin32]。  

## 必备条件  

*   [WebView2 运行时][Webview2Installer] 或任何 Microsoft Edge (Chromium 在支持的操作系统 \ (当前 windows 10、windows 8.1 和 windows 7 \ ) 上安装了 [) 非稳定通道][MicrosoftedgeinsiderDownload] 。  
    
    > [!NOTE]
    > Web 视图团队建议使用 "82.0.488.0" 通道，并且所需的最低版本是 ""。  
    
*   安装了 c + + 支持的[Visual Studio][MicrosoftVisualstudioMain] 2015 或更高版本。  

## 步骤 1-创建单窗口 win32 应用程序  

从包含单个主窗口的基本桌面项目开始。  为了更好地重点介绍本演练，你使用的是示例中的修改后的示例代码：为你的示例应用 [创建一个传统的 Windows 桌面应用程序 (c + +) ][CppWindowsWalkthroughCreatingDesktopApplication] 。  若要下载修改后的示例并开始使用，请导航到 [WebView2 示例][GithubMicrosoftedgeWebview2samplesGettingStartedGuide]。  

在 Visual Studio 中，打开 `WebView2GettingStarted.sln` 。  如果使用的是早期版本的 Visual Studio，请将鼠标悬停在 **WebView2GettingStarted** 项目上，打开上下文菜单 \ (右键单击 "\ ) "，然后选择 " **属性**"。  在 "**配置属性**" 下的 "  >  **常规**" 下，修改**Windows SDK 版本**和**平台工具集**以使用 Win10 SDK 和 Visual Studio 工具集 \ (VS 工具集 \ ) 。  

:::image type="complex" source="../media/tool-version.png" alt-text="工具版本" lightbox="../media/tool-version.png":::
   工具版本  
:::image-end:::  

Visual Studio 可能会显示一些错误，因为缺少 WebView2 头文件，该文件应在步骤2完成后消失。  

## 步骤 2-安装 WebView2 SDK  

将 WebView2 SDK 添加到项目中。  你可以使用 NuGet 安装 Win32 SDK。  

1.  将鼠标悬停在项目上，打开上下文菜单 \ (右键单击 "\ ) "，然后选择 " **管理 NuGet 程序包**"。  
    
    :::image type="complex" source="../media/manage-nuget-packages.png" alt-text="工具版本" lightbox="../media/manage-nuget-packages.png":::
       管理 NuGet 程序包  
    :::image-end:::  
    
1.  安装 Windows 实现库。  
    1.  `Microsoft.Windows.ImplementationLibrary`在搜索栏中输入 "ImplementationLibrary"，从结果中选择 "**微软**"，然后在右侧窗口中选择 "**安装**"。  NuGet 将 SDK 下载到您的计算机。  
        
        > [!NOTE] 
        > [Windows 实现库][GithubMicrosoftWilMain]和[Windows 运行时 c + + 模板库][CppCxWrlTemplateLibraryVS2019]是可选的，并且已添加以使该示例更易于使用 COM。  
        
        :::image type="complex" source="../media/wil.png" alt-text="工具版本" lightbox="../media/wil.png":::
           Windows 实现库  
        :::image-end:::  
        
1.  安装 WebView2 SDK。  
    1.  `Microsoft.Web.WebView2`在搜索栏中输入 "WebView2"，从结果中选择 "**微软**"，然后在右侧窗口中选择 "**安装**"。  NuGet 将 SDK 下载到您的计算机。  
        
        :::image type="complex" source="../media/nuget.png" alt-text="工具版本" lightbox="../media/nuget.png":::
           Nuget 程序包管理器
        :::image-end:::  
        
1.  将 WebView2 标头添加到你的项目。  
    :::row:::
       :::column span="1":::
          打开 `HelloWebView.cpp` 、复制以下代码片段并粘贴到 `HelloWebView.cpp` 最后一行后 `#include` 。  
          
          ```cpp
          // include WebView2 header
          #include "WebView2.h"
          ```  
       :::column-end:::
       :::column span="1":::
          "包含" 部分应类似于以下代码片段。  
          
          ```cpp
          ...
          #include <wrl.h>
          #include <wil/com.h>
          // include WebView2 header
          #include "WebView2.h"
          ```  
       :::column-end:::
    :::row-end:::
    
你已设置为对 WebView2 API 使用和构建。  

### 构建空示例应用  

选择 `F5` 以生成并运行示例应用。  此时将显示一个应用，显示一个空窗口。  

:::image type="complex" source="../media/empty-app.png" alt-text="工具版本" lightbox="../media/empty-app.png":::
   空应用  
:::image-end:::  

## 步骤 3-在父窗口中创建单个 Web 视图  

将 Web 视图添加到主窗口。  使用 `CreateCoreWebView2Environment` 方法设置环境并找到 Microsoft Edge \ (Chromium \ ) 浏览器为控件供电。  `CreateCoreWebView2EnvironmentWithOptions`如果你希望指定浏览器位置、用户文件夹、浏览器标记等，而不是使用默认设置，也可以使用该方法。  完成该 `CreateCoreWebView2Environment` 方法后，你可以在 `ICoreWebView2Environment::CreateCoreWebView2Controller` 回调内运行该方法 `ICoreWebView2CreateCoreWebView2EnvironmentCompletedHandler` ，然后运行该 `ICoreWebView2Controller::get_CoreWebView2` 方法以获取关联的 web 视图。  

在回调中，设置一些其他设置，调整 Web 视图大小以占用父窗口的100%，然后导航到 Bing。  

复制以下代码片段，并将 `HelloWebView.cpp` 其粘贴到 `// <-- WebView2 sample code starts here -->` 笔记之后和注释之前 `// <-- WebView2 sample code ends here -->` 。  

```cpp
// Step 3 - Create a single WebView within the parent window
// Locate the browser and set up the environment for WebView
CreateCoreWebView2EnvironmentWithOptions(nullptr, nullptr, nullptr,
    Callback<ICoreWebView2CreateCoreWebView2EnvironmentCompletedHandler>(
        [hWnd](HRESULT result, ICoreWebView2Environment* env) -> HRESULT {
        
            // Create a CoreWebView2Controller and get the associated CoreWebView2 whose parent is the main window hWnd
            env->CreateCoreWebView2Controller(hWnd, Callback<ICoreWebView2CreateCoreWebView2ControllerCompletedHandler>(
                [hWnd](HRESULT result, ICoreWebView2Controller* controller) -> HRESULT {
                if (controller != nullptr) {
                    webviewController = controller;
                    webviewController->get_CoreWebView2(&webviewWindow);
                }
                
                // Add a few settings for the webview
                // The demo step is redundant since the values are the default settings
                ICoreWebView2Settings* Settings;
                webviewWindow->get_Settings(&Settings);
                Settings->put_IsScriptEnabled(TRUE);
                Settings->put_AreDefaultScriptDialogsEnabled(TRUE);
                Settings->put_IsWebMessageEnabled(TRUE);
                
                // Resize WebView to fit the bounds of the parent window
                RECT bounds;
                GetClientRect(hWnd, &bounds);
                webviewController->put_Bounds(bounds);
                
                // Schedule an async task to navigate to Bing
                webviewWindow->Navigate(L"https://www.bing.com/");
                
                // Step 4 - Navigation events
                
                // Step 5 - Scripting
                
                // Step 6 - Communication between host and web content
                
                return S_OK;
            }).Get());
        return S_OK;
    }).Get());
```  

### 构建必应示例应用  

选择 `F5` 生成并运行应用。  现在，你已有一个显示 "必应" 页面的 Web 视图窗口。  

:::image type="complex" source="../media/bing-window.png" alt-text="工具版本" lightbox="../media/bing-window.png":::
   必应窗口  
:::image-end:::  

## 步骤 4-导航事件  

在上一步中，Web 视图团队已涵盖使用方法导航到 URL `ICoreWebView2::Navigate` 。  在导航过程中，Web 视图将引发主机可能侦听的一系列事件。  

1.  `NavigationStarting`  
1.  `SourceChanged`  
1.  `ContentLoading`  
1.  `HistoryChanged`   
1.  `NavigationCompleted`   

有关详细信息，请导航到 [导航事件][Webview2ConceptsNavigationEvents]。  

:::image type="complex" source="../media/navigation-events.png" alt-text="工具版本" lightbox="../media/navigation-events.png":::
   导航事件  
:::image-end:::  

在错误情况下，可能会发生以下一个或多个事件，具体取决于是否将导航转到错误页面。  

*   `SourceChanged`  
*   `ContentLoading`  
*   `HistoryChanged`

如果发生 HTTP 重定向，一行中有多个 `NavigationStarting` 事件。  

作为使用事件的示例，注册事件的处理程序 `NavigationStarting` 以取消任何非 https 请求。  复制以下代码片段并粘贴到其中 `HelloWebView.cpp` 。  

```cpp
// register an ICoreWebView2NavigationStartingEventHandler to cancel any non-https navigation
EventRegistrationToken token;
webviewWindow->add_NavigationStarting(Callback<ICoreWebView2NavigationStartingEventHandler>(
    [](ICoreWebView2* webview, ICoreWebView2NavigationStartingEventArgs * args) -> HRESULT {
        PWSTR uri;
        args->get_Uri(&uri);
        std::wstring source(uri);
        if (source.substr(0, 5) != L"https") {
            args->put_Cancel(true);
        }
        CoTaskMemFree(uri);
        return S_OK;
    }).Get(), &token);
```  

现在，应用不会导航到任何非 https 网站。  您可以使用类似的机制来完成其他任务，如限制导航到您自己的域中。  

## 步骤 5-脚本  

托管应用还可以将 JavaScript 插入 Web 视图。  你可以通过任务 Web 视图运行任意 JavaScript 或添加初始化脚本。  已添加的初始化脚本将应用于所有未来的顶级文档和子框架导航，直到删除。  在创建全局对象之后、运行 HTML 文档包含的任何其他脚本之前，将运行初始化脚本。  

复制以下代码片段并粘贴到其中 `HelloWebView.cpp` 。  

```cpp
// Schedule an async task to add initialization script that freezes the Object object
webviewWindow->AddScriptToExecuteOnDocumentCreated(L"Object.freeze(Object);", nullptr);
// Schedule an async task to get the document URL
webviewWindow->ExecuteScript(L"window.document.URL;", Callback<ICoreWebView2ExecuteScriptCompletedHandler>(
    [](HRESULT errorCode, LPCWSTR resultObjectAsJson) -> HRESULT {
        LPCWSTR URL = resultObjectAsJson;
        //doSomethingWithURL(URL);
        return S_OK;
    }).Get());
```  

现在，Web 视图应始终冻结 `Object` 对象并返回页面文档一次。  

> [!NOTE] 
> 脚本注入 Api \ (和某些其他 WebView2 Api \ ) 是异步的，如果必须以特定顺序运行代码，则应使用回调。  

## 步骤 6-主机和 web 内容之间的通信  

宿主和 web 内容也可能通过该方法互相通信 `postMessage` 。  在 web 视图内运行的 web 内容可能会通过该方法向主机发布 `window.chrome.webview.postMessage` ，并且消息由主机上任何注册的 `ICoreWebView2WebMessageReceivedEventHandler` 事件处理程序处理。  同样，主机可以通过 " `ICoreWebView2::PostWebMessageAsString` 或" `ICoreWebView2::PostWebMessageAsJSON` 方法处理 web 内容，这由从侦听器添加的处理程序捕获 `window.chrome.webview.addEventListener` 。  通信机制允许 web 内容通过传递消息来使用本机功能，以便让主机运行本机 Api。  

作为了解机制的示例，当你尝试在 Web 视图中打印文档 URL 时，将发生以下步骤。  

1.  主机注册处理程序以返回收到的消息，返回到 web 内容  
1.  主机将向注册处理程序的 web 内容插入脚本，以便从主机打印消息  
1.  主机为将 URL 发布到主机的 web 内容插入脚本  
1.  将触发主机的处理程序，并返回消息 \ (URL \ ) 到 web 内容  
1.  将触发 web 内容的处理程序并打印来自主机 \ (URL \ ) 的消息  

复制以下代码片段并粘贴到其中 `HelloWebView.cpp` 。    

```cpp
// Set an event handler for the host to return received message back to the web content
webviewWindow->add_WebMessageReceived(Callback<ICoreWebView2WebMessageReceivedEventHandler>(
    [](ICoreWebView2* webview, ICoreWebView2WebMessageReceivedEventArgs * args) -> HRESULT {
        PWSTR message;
        args->TryGetWebMessageAsString(&message);
        // processMessage(&message);
        webview->PostWebMessageAsString(message);
        CoTaskMemFree(message);
        return S_OK;
    }).Get(), &token);

// Schedule an async task to add initialization script that
// 1) Add an listener to print message from the host
// 2) Post document URL to the host
webviewWindow->AddScriptToExecuteOnDocumentCreated(
    L"window.chrome.webview.addEventListener(\'message\', event => alert(event.data));" \
    L"window.chrome.webview.postMessage(window.document.URL);",
nullptr);
```  

### 构建你的显示 URL 示例应用  

选择 `F5` 生成并运行应用。  在导航到页面之前，该 URL 显示在弹出窗口中。  

:::image type="complex" source="../media/show-url.png" alt-text="工具版本" lightbox="../media/show-url.png":::
   显示 url  
:::image-end:::  

恭喜，你刚刚构建了你的第一个 WebView2 应用。  

## 后续步骤  

此页面上未介绍的许多 WebView2 功能，以下部分提供了其他资源。  

### 另请参阅  

*   有关 WebView2 功能的完整示例，请导航到 [WEBVIEW2 API 示例][GithubMicrosoftedgeWebview2samplesApisample]。  
*   对于使用 WebView2 生成的示例应用程序，请导航到 [WebView2Browser][GithubMicrosoftedgeWebview2browser]。  
*   有关 WebView2 API 的详细信息，请导航到 [API 参考][Webview2ReferenceWin32]。  

## 与 Microsoft Edge Web 上的 Web Edge 团队取得联系  

[!INCLUDE [contact WebView team note](../includes/contact-webview-team-note.md)]  

<!-- links -->  

[Webview2Index]: ../index.md "Microsoft Edge WebView2 简介 (预览版) |Microsoft 文档"  
[Webview2ReferenceWin32]: /microsoft-edge/webview2/reference/win32 "WebView2 Win32 c + + 参考 |Microsoft 文档"  
[Webview2ConceptsNavigationEvents]: ../concepts/navigation-events.md "导航事件 |Microsoft 文档"  

[CppCxWrlTemplateLibraryVS2019]: /cpp/cppcx/wrl/windows-runtime-cpp-template-library-wrl?view=vs-2019&preserve-view=true "Windows 运行时 c + + 模板库 (WRL) |Microsoft 文档"  
[CppWindowsWalkthroughCreatingDesktopApplication]: /cpp/windows/walkthrough-creating-windows-desktop-applications-cpp?view=vs-2019&preserve-view=true "演练：创建传统的 Windows 桌面应用程序 (c + +) |Microsoft 文档"  

[GithubMicrosoftedgeWebview2browser]: https://github.com/MicrosoftEdge/WebView2Browser "WebView2Browser-MicrosoftEdge/WebView2Browser |GitHub"  

[GithubMicrosoftedgeWebviewfeedback]: https://github.com/MicrosoftEdge/WebViewFeedback "Web 视图反馈-MicrosoftEdge/WebViewFeedback |GitHub"  

[GithubMicrosoftedgeWebview2samplesApisample]: https://github.com/MicrosoftEdge/WebView2Samples/blob/master/SampleApps/WebView2APISample/README.md "WebView2 API Sample-MicrosoftEdge/WebView2Samples |GitHub"  
[GithubMicrosoftedgeWebview2samplesGettingStartedGuide]: https://github.com/MicrosoftEdge/WebView2Samples#1-getting-started-guide "WebView2 示例-MicrosoftEdge/WebView2Samples |GitHub"  

[GithubMicrosoftWilMain]: https://github.com/Microsoft/wil "Windows 实施库 () -microsoft/中 |GitHub"  

[MicrosoftedgeinsiderDownload]: https://www.microsoftedgeinsider.com/download "下载 Microsoft Edge 预览体验成员频道"  

[MicrosoftVisualstudioMain]: https://visualstudio.microsoft.com "Visual Studio"  

[Webview2Installer]: https://developer.microsoft.com/microsoft-edge/webview2 "WebView2 安装程序"  
