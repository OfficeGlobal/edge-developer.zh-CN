---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 适用于 Win32 应用的 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/26/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html
ms.openlocfilehash: 2f376cdd7098c512a8c7a0a3a463f5302f0bfbd7
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2020
ms.locfileid: "10653236"
---
# <span data-ttu-id="52f10-104">interface ICoreWebView2Environment</span><span class="sxs-lookup"><span data-stu-id="52f10-104">interface ICoreWebView2Environment</span></span> 

> [!NOTE]
> <span data-ttu-id="52f10-105">此接口可能会在 SDK 版本0.9.430 后更改或不可用。</span><span class="sxs-lookup"><span data-stu-id="52f10-105">This interface may be altered or unavailable for releases after SDK version 0.9.430.</span></span> <span data-ttu-id="52f10-106">请参阅[参考](../../../webview2-api-reference.md)了解最新的 API 参考。</span><span class="sxs-lookup"><span data-stu-id="52f10-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2Environment
  : public IUnknown
```

<span data-ttu-id="52f10-107">这表示 WebView2 环境。</span><span class="sxs-lookup"><span data-stu-id="52f10-107">This represents the WebView2 Environment.</span></span>

## <span data-ttu-id="52f10-108">摘要</span><span class="sxs-lookup"><span data-stu-id="52f10-108">Summary</span></span>

 <span data-ttu-id="52f10-109">成员</span><span class="sxs-lookup"><span data-stu-id="52f10-109">Members</span></span>                        | <span data-ttu-id="52f10-110">描述</span><span class="sxs-lookup"><span data-stu-id="52f10-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="52f10-111">CreateCoreWebView2Host</span><span class="sxs-lookup"><span data-stu-id="52f10-111">CreateCoreWebView2Host</span></span>](#createcorewebview2host) | <span data-ttu-id="52f10-112">异步创建新的 Web 视图。</span><span class="sxs-lookup"><span data-stu-id="52f10-112">Asynchronously create a new WebView.</span></span>
[<span data-ttu-id="52f10-113">CreateWebResourceResponse</span><span class="sxs-lookup"><span data-stu-id="52f10-113">CreateWebResourceResponse</span></span>](#createwebresourceresponse) | <span data-ttu-id="52f10-114">创建新的 web 资源响应对象。</span><span class="sxs-lookup"><span data-stu-id="52f10-114">Create a new web resource response object.</span></span>
[<span data-ttu-id="52f10-115">get_BrowserVersionInfo</span><span class="sxs-lookup"><span data-stu-id="52f10-115">get_BrowserVersionInfo</span></span>](#get_browserversioninfo) | <span data-ttu-id="52f10-116">当前[ICoreWebView2Environment]()的浏览器版本信息，包括频道名称（如果不是稳定频道）。</span><span class="sxs-lookup"><span data-stu-id="52f10-116">The browser version info of the current [ICoreWebView2Environment](), including channel name if it is not the stable channel.</span></span>
[<span data-ttu-id="52f10-117">add_NewBrowserVersionAvailable</span><span class="sxs-lookup"><span data-stu-id="52f10-117">add_NewBrowserVersionAvailable</span></span>](#add_newbrowserversionavailable) | <span data-ttu-id="52f10-118">当已安装更高版本的 Edge 浏览器并可通过 WebView2 使用时，将引发 NewBrowserVersionAvailable 事件。</span><span class="sxs-lookup"><span data-stu-id="52f10-118">The NewBrowserVersionAvailable event fires when a newer version of the Edge browser is installed and available to use via WebView2.</span></span>
[<span data-ttu-id="52f10-119">remove_NewBrowserVersionAvailable</span><span class="sxs-lookup"><span data-stu-id="52f10-119">remove_NewBrowserVersionAvailable</span></span>](#remove_newbrowserversionavailable) | <span data-ttu-id="52f10-120">删除以前使用 add_NewBrowserVersionAvailable 添加的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="52f10-120">Remove an event handler previously added with add_NewBrowserVersionAvailable.</span></span>

<span data-ttu-id="52f10-121">在使用环境参数指定的浏览器进程中运行的环境中创建的 WebViews，应在同一环境中使用。</span><span class="sxs-lookup"><span data-stu-id="52f10-121">WebViews created from an environment run on the Browser process specified with environment parameters and objects created from an environment should be used in the same environment.</span></span> <span data-ttu-id="52f10-122">在不同的环境中使用它不保证兼容，并且可能会失败。</span><span class="sxs-lookup"><span data-stu-id="52f10-122">Using it in different environments are not guaranteed to be compatible and may fail.</span></span>

## <span data-ttu-id="52f10-123">成员</span><span class="sxs-lookup"><span data-stu-id="52f10-123">Members</span></span>

#### <span data-ttu-id="52f10-124">CreateCoreWebView2Host</span><span class="sxs-lookup"><span data-stu-id="52f10-124">CreateCoreWebView2Host</span></span> 

<span data-ttu-id="52f10-125">异步创建新的 Web 视图。</span><span class="sxs-lookup"><span data-stu-id="52f10-125">Asynchronously create a new WebView.</span></span>

> <span data-ttu-id="52f10-126">公共 HRESULT [CreateCoreWebView2Host](#createcorewebview2host)（HWND ParentWindow，[ICoreWebView2CreateCoreWebView2HostCompletedHandler](ICoreWebView2CreateCoreWebView2HostCompletedHandler.md) \* 处理程序）</span><span class="sxs-lookup"><span data-stu-id="52f10-126">public HRESULT [CreateCoreWebView2Host](#createcorewebview2host)(HWND parentWindow,[ICoreWebView2CreateCoreWebView2HostCompletedHandler](ICoreWebView2CreateCoreWebView2HostCompletedHandler.md) \* handler)</span></span>

<span data-ttu-id="52f10-127">parentWindow 是应在其中显示 Web 视图和接收输入的 HWND。</span><span class="sxs-lookup"><span data-stu-id="52f10-127">parentWindow is the HWND in which the WebView should be displayed and from which receive input.</span></span> <span data-ttu-id="52f10-128">在创建 Web 视图期间，Web 视图会将子窗口添加到提供的窗口中。</span><span class="sxs-lookup"><span data-stu-id="52f10-128">The WebView will add a child window to the provided window during WebView creation.</span></span> <span data-ttu-id="52f10-129">由同辈窗口顺序影响的 Z 顺序和其他项目将相应受到影响。</span><span class="sxs-lookup"><span data-stu-id="52f10-129">Z-order and other things impacted by sibling window order will be affected accordingly.</span></span>

<span data-ttu-id="52f10-130">建议为进程或应用程序窗口设置应用程序用户模型 ID。</span><span class="sxs-lookup"><span data-stu-id="52f10-130">It is recommended that the application set Application User Model ID for the process or the application window.</span></span> <span data-ttu-id="52f10-131">如果未设置，则在创建 Web 视图期间生成的应用程序用户模型 ID 将设置为 parentWindow 的根窗口。</span><span class="sxs-lookup"><span data-stu-id="52f10-131">If none is set, during WebView creation a generated Application User Model ID is set to root window of parentWindow.</span></span> 

```cpp
// Create or recreate the WebView and its environment.
void AppWindow::InitializeWebView()
{
    // To ensure browser switches get applied correctly, we need to close
    // the existing WebView. This will result in a new browser process
    // getting created which will apply the browser switches.
    CloseWebView();

    LPCWSTR subFolder = nullptr;
    LPCWSTR additionalBrowserSwitches = nullptr;
    HRESULT hr = CreateCoreWebView2EnvironmentWithDetails(
        subFolder, nullptr, additionalBrowserSwitches,
        Callback<ICoreWebView2CreateCoreWebView2EnvironmentCompletedHandler>(
            this, &AppWindow::OnCreateEnvironmentCompleted)
            .Get());
    if (!SUCCEEDED(hr))
    {
        if (hr == HRESULT_FROM_WIN32(ERROR_FILE_NOT_FOUND))
        {
            MessageBox(
                m_mainWindow,
                L"Couldn't find Edge installation. "
                "Do you have a version installed that's compatible with this "
                "WebView2 SDK version?",
                nullptr, MB_OK);
        }
        else
        {
            ShowFailure(hr, L"Failed to create webview environment");
        }
    }
}

// This is the callback passed to CreateWebViewEnvironmnetWithDetails.
// Here we simply create the WebView.
HRESULT AppWindow::OnCreateEnvironmentCompleted(
    HRESULT result, ICoreWebView2Environment* environment)
{
    CHECK_FAILURE(result);

    CHECK_FAILURE(environment->QueryInterface(IID_PPV_ARGS(&m_webViewEnvironment)));
        CHECK_FAILURE(m_webViewEnvironment->CreateCoreWebView2Host(
            m_mainWindow, Callback<ICoreWebView2CreateCoreWebView2HostCompletedHandler>(
                              this, &AppWindow::OnCreateCoreWebView2HostCompleted)
                              .Get()));
    return S_OK;
}
```

 <span data-ttu-id="52f10-132">建议应用程序处理重启管理器消息，以便当应用在特定安装中使用 web 视图的边缘且正在卸载该安装时，它可以正常重启。</span><span class="sxs-lookup"><span data-stu-id="52f10-132">It is recommended that the application handles restart manager messages so that it can be restarted gracefully in the case when the app is using Edge for webview from a certain installation and that installation is being uninstalled.</span></span> <span data-ttu-id="52f10-133">例如，如果用户从开发频道安装 Edge，并使用该通道中的边缘来测试应用，然后从该通道卸载 Edge 而不关闭应用，则应用将重新启动以允许卸载开发人员通道。</span><span class="sxs-lookup"><span data-stu-id="52f10-133">For example, if a user installs Edge from Dev channel and opts to use Edge from that channel for testing the app, and then uninstalls Edge from that channel without closing the app, the app will be restarted to allow uninstallation of the dev channel to succeed.</span></span> 

```cpp
    case WM_QUERYENDSESSION:
    {
        // yes, we can shut down
        // Register how we might be restarted
        RegisterApplicationRestart(L"--restore", RESTART_NO_CRASH | RESTART_NO_HANG);
        *result = TRUE;
        return true;
    }
    break;
    case WM_ENDSESSION:
    {
        if (wParam == TRUE)
        {
            // save app state and exit.
            PostQuitMessage(0);
            return true;
        }
    }
    break;
```

#### <span data-ttu-id="52f10-134">CreateWebResourceResponse</span><span class="sxs-lookup"><span data-stu-id="52f10-134">CreateWebResourceResponse</span></span> 

<span data-ttu-id="52f10-135">创建新的 web 资源响应对象。</span><span class="sxs-lookup"><span data-stu-id="52f10-135">Create a new web resource response object.</span></span>

> <span data-ttu-id="52f10-136">public HRESULT [CreateWebResourceResponse](#createwebresourceresponse)（IStream \* 内容、int STATUSCODE、LPCWSTR REASONPHRASE、LPCWSTR 标头、[ICoreWebView2WebResourceResponse](ICoreWebView2WebResourceResponse.md) \* \* \* response）</span><span class="sxs-lookup"><span data-stu-id="52f10-136">public HRESULT [CreateWebResourceResponse](#createwebresourceresponse)(IStream \* content,int statusCode,LPCWSTR reasonPhrase,LPCWSTR headers,[ICoreWebView2WebResourceResponse](ICoreWebView2WebResourceResponse.md) \*\* response)</span></span>

<span data-ttu-id="52f10-137">标头是由换行符分隔的原始响应标题字符串。</span><span class="sxs-lookup"><span data-stu-id="52f10-137">The headers is the raw response header string delimited by newline.</span></span> <span data-ttu-id="52f10-138">也可以使用空的标头字符串创建此对象，然后使用[ICoreWebView2HttpResponseHeaders](ICoreWebView2HttpResponseHeaders.md)来逐行构造标题。</span><span class="sxs-lookup"><span data-stu-id="52f10-138">It's also possible to create this object with empty headers string and then use the [ICoreWebView2HttpResponseHeaders](ICoreWebView2HttpResponseHeaders.md) to construct the headers line by line.</span></span> <span data-ttu-id="52f10-139">有关其他参数的信息，请参阅[ICoreWebView2WebResourceResponse](ICoreWebView2WebResourceResponse.md)。</span><span class="sxs-lookup"><span data-stu-id="52f10-139">For information on other parameters see [ICoreWebView2WebResourceResponse](ICoreWebView2WebResourceResponse.md).</span></span>

```cpp
        if (m_blockImages)
        {
            m_webView->AddWebResourceRequestedFilter(L"*", CORE_WEBVIEW2_WEB_RESOURCE_CONTEXT_IMAGE);
            CHECK_FAILURE(m_webView->add_WebResourceRequested(
                Callback<ICoreWebView2WebResourceRequestedEventHandler>(
                    [this](
                        ICoreWebView2* sender,
                        ICoreWebView2WebResourceRequestedEventArgs* args) {
                        CORE_WEBVIEW2_WEB_RESOURCE_CONTEXT resourceContext;
                        CHECK_FAILURE(
                            args->get_ResourceContext(&resourceContext));
                        // Ensure that the type is image
                        if (resourceContext != CORE_WEBVIEW2_WEB_RESOURCE_CONTEXT_IMAGE)
                        {
                            return E_INVALIDARG;
                        }
                        // Override the response with an empty one to block the image.
                        // If put_Response is not called, the request will continue as normal.
                        wil::com_ptr<ICoreWebView2WebResourceResponse> response;
                        CHECK_FAILURE(m_webViewEnvironment->CreateWebResourceResponse(
                            nullptr, 403 /*NoContent*/, L"Blocked", L"", &response));
                        CHECK_FAILURE(args->put_Response(response.get()));
                        return S_OK;
                    })
                    .Get(),
                &m_webResourceRequestedTokenForImageBlocking));
        }
        else
        {
            CHECK_FAILURE(m_webView->remove_WebResourceRequested(
                m_webResourceRequestedTokenForImageBlocking));
        }
```

#### <span data-ttu-id="52f10-140">get_BrowserVersionInfo</span><span class="sxs-lookup"><span data-stu-id="52f10-140">get_BrowserVersionInfo</span></span> 

<span data-ttu-id="52f10-141">当前[ICoreWebView2Environment]()的浏览器版本信息，包括频道名称（如果不是稳定频道）。</span><span class="sxs-lookup"><span data-stu-id="52f10-141">The browser version info of the current [ICoreWebView2Environment](), including channel name if it is not the stable channel.</span></span>

> <span data-ttu-id="52f10-142">公共 HRESULT [get_BrowserVersionInfo](#get_browserversioninfo)（LPWSTR \* versionInfo）</span><span class="sxs-lookup"><span data-stu-id="52f10-142">public HRESULT [get_BrowserVersionInfo](#get_browserversioninfo)(LPWSTR \* versionInfo)</span></span>

<span data-ttu-id="52f10-143">这与 GetCoreWebView2BrowserVersionInfo API 的格式相匹配。</span><span class="sxs-lookup"><span data-stu-id="52f10-143">This matches the format of the GetCoreWebView2BrowserVersionInfo API.</span></span> <span data-ttu-id="52f10-144">信道名称为 "beta"、"dev" 和 "未设备"。</span><span class="sxs-lookup"><span data-stu-id="52f10-144">Channel names are 'beta', 'dev', and 'canary'.</span></span>

```cpp
        wil::unique_cotaskmem_string version_info;
        m_webViewEnvironment->get_BrowserVersionInfo(&version_info);
        MessageBox(
            m_mainWindow, version_info.get(), L"Browser Version Info After WebView Creation",
            MB_OK);
```

#### <span data-ttu-id="52f10-145">add_NewBrowserVersionAvailable</span><span class="sxs-lookup"><span data-stu-id="52f10-145">add_NewBrowserVersionAvailable</span></span> 

<span data-ttu-id="52f10-146">当已安装更高版本的 Edge 浏览器并可通过 WebView2 使用时，将引发 NewBrowserVersionAvailable 事件。</span><span class="sxs-lookup"><span data-stu-id="52f10-146">The NewBrowserVersionAvailable event fires when a newer version of the Edge browser is installed and available to use via WebView2.</span></span>

> <span data-ttu-id="52f10-147">public HRESULT [add_NewBrowserVersionAvailable](#add_newbrowserversionavailable)（[ICoreWebView2NewBrowserVersionAvailableEventHandler](ICoreWebView2NewBrowserVersionAvailableEventHandler.md) \* eventHandler，EventRegistrationToken \* token）</span><span class="sxs-lookup"><span data-stu-id="52f10-147">public HRESULT [add_NewBrowserVersionAvailable](#add_newbrowserversionavailable)([ICoreWebView2NewBrowserVersionAvailableEventHandler](ICoreWebView2NewBrowserVersionAvailableEventHandler.md) \* eventHandler,EventRegistrationToken \* token)</span></span>

<span data-ttu-id="52f10-148">若要使用较新版本的浏览器，必须创建新的环境和 Web 视图。</span><span class="sxs-lookup"><span data-stu-id="52f10-148">To use the newer version of the browser you must create a new environment and WebView.</span></span> <span data-ttu-id="52f10-149">将仅针对从其运行代码的同一边缘通道中的新版本引发此事件。</span><span class="sxs-lookup"><span data-stu-id="52f10-149">This event will only be fired for new version from the same Edge channel that the code is running from.</span></span> <span data-ttu-id="52f10-150">当不运行安装的边缘时，将不会触发任何事件。</span><span class="sxs-lookup"><span data-stu-id="52f10-150">When not running with installed Edge, no event will be fired.</span></span>

<span data-ttu-id="52f10-151">由于用户数据文件夹一次只能由一个浏览器进程使用，如果要在 WebViews 中使用新版本的浏览器使用同一用户数据文件夹，则必须先关闭使用早期版本的浏览器的环境和 WebViews。</span><span class="sxs-lookup"><span data-stu-id="52f10-151">Because a user data folder can only be used by one browser process at a time, if you want to use the same user data folder in the WebViews using the new version of the browser, you must close the environment and WebViews that are using the older version of the browser first.</span></span> <span data-ttu-id="52f10-152">或者只提示用户重新启动应用。</span><span class="sxs-lookup"><span data-stu-id="52f10-152">Or simply prompt the user to restart the app.</span></span>

```cpp
    // After the environment is successfully created,
    // register a handler for the NewBrowserVersionAvailable event.
    // This handler tells when there is a new Edge version available on the machine.
    CHECK_FAILURE(m_webViewEnvironment->add_NewBrowserVersionAvailable(
        Callback<ICoreWebView2NewBrowserVersionAvailableEventHandler>(
            [this](
                ICoreWebView2Environment* sender,
                ICoreWebView2NewBrowserVersionAvailableEventArgs* args) -> HRESULT {
                // Get the version value from args
                wil::unique_cotaskmem_string newVersion;
                CHECK_FAILURE(args->get_NewVersion(&newVersion));
                std::wstring message = L"We detected there is a new version for the browser.";
                message += L"\n\nVersion number: ";
                message += newVersion.get();
                message += L"\n\n";
                if (m_webView)
                {
                    message += L"Do you want to restart the app? \n\n";
                    message += L"Click No if you only want to re-create the webviews. \n";
                    message += L"Click Cancel for no action. \n";
                }
                int response = MessageBox(
                    m_mainWindow, message.c_str(), L"New available version",
                    m_webView ? MB_YESNOCANCEL : MB_OK);

                if (response == IDYES)
                {
                    RestartApp();
                }
                else if (response == IDNO)
                {
                    ReinitializeWebViewWithNewBrowser();
                }
                else
                {
                    // do nothing
                }

                return S_OK;
            })
            .Get(),
        nullptr));
```

#### <span data-ttu-id="52f10-153">remove_NewBrowserVersionAvailable</span><span class="sxs-lookup"><span data-stu-id="52f10-153">remove_NewBrowserVersionAvailable</span></span> 

<span data-ttu-id="52f10-154">删除以前使用 add_NewBrowserVersionAvailable 添加的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="52f10-154">Remove an event handler previously added with add_NewBrowserVersionAvailable.</span></span>

> <span data-ttu-id="52f10-155">public HRESULT [remove_NewBrowserVersionAvailable](#remove_newbrowserversionavailable)（EventRegistrationToken 标记）</span><span class="sxs-lookup"><span data-stu-id="52f10-155">public HRESULT [remove_NewBrowserVersionAvailable](#remove_newbrowserversionavailable)(EventRegistrationToken token)</span></span>
