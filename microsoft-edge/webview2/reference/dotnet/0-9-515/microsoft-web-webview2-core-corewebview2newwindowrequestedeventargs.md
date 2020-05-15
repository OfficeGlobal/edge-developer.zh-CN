---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 适用于 Win32 应用的 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/12/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: cca15ccc5292f5eaf6f317ffb657f46fcd84b4a9
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2020
ms.locfileid: "10653176"
---
# <span data-ttu-id="c8349-104">CoreWebView2NewWindowRequestedEventArgs 类的 WebView2</span><span class="sxs-lookup"><span data-stu-id="c8349-104">Microsoft.Web.WebView2.Core.CoreWebView2NewWindowRequestedEventArgs class</span></span> 

<span data-ttu-id="c8349-105">命名空间： Microsoft WebView2 </span><span class="sxs-lookup"><span data-stu-id="c8349-105">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="c8349-106">程序集： Microsoft WebView2</span><span class="sxs-lookup"><span data-stu-id="c8349-106">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="c8349-107">Webview.newwindowrequested 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="c8349-107">Event args for the NewWindowRequested event.</span></span>

## <span data-ttu-id="c8349-108">摘要</span><span class="sxs-lookup"><span data-stu-id="c8349-108">Summary</span></span>

 <span data-ttu-id="c8349-109">成员</span><span class="sxs-lookup"><span data-stu-id="c8349-109">Members</span></span>                        | <span data-ttu-id="c8349-110">描述</span><span class="sxs-lookup"><span data-stu-id="c8349-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="c8349-111">Handled</span><span class="sxs-lookup"><span data-stu-id="c8349-111">Handled</span></span>](#handled) | <span data-ttu-id="c8349-112">NewWindowRequestedEvent 是否由主机处理。</span><span class="sxs-lookup"><span data-stu-id="c8349-112">Whether the NewWindowRequestedEvent is handled by host.</span></span>
[<span data-ttu-id="c8349-113">IsUserInitiated</span><span class="sxs-lookup"><span data-stu-id="c8349-113">IsUserInitiated</span></span>](#isuserinitiated) | <span data-ttu-id="c8349-114">通过用户笔势（如单击带有目标的定位点标记）启动新的窗口请求时，IsUserInitiated 为 true。</span><span class="sxs-lookup"><span data-stu-id="c8349-114">IsUserInitiated is true when the new window request was initiated through a user gesture such as clicking an anchor tag with target.</span></span>
[<span data-ttu-id="c8349-115">NewWindow</span><span class="sxs-lookup"><span data-stu-id="c8349-115">NewWindow</span></span>](#newwindow) | <span data-ttu-id="c8349-116">获取新窗口。</span><span class="sxs-lookup"><span data-stu-id="c8349-116">Gets the new window.</span></span>
[<span data-ttu-id="c8349-117">Uri</span><span class="sxs-lookup"><span data-stu-id="c8349-117">Uri</span></span>](#uri) | <span data-ttu-id="c8349-118">NewWindowRequest 的目标 uri。</span><span class="sxs-lookup"><span data-stu-id="c8349-118">The target uri of the NewWindowRequest.</span></span>
[<span data-ttu-id="c8349-119">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="c8349-119">GetDeferral</span></span>](#getdeferral) | <span data-ttu-id="c8349-120">获取 CoreWebView2Deferral 对象并将事件置于延迟状态。</span><span class="sxs-lookup"><span data-stu-id="c8349-120">Obtain a CoreWebView2Deferral object and put the event into a deferred state.</span></span>

<span data-ttu-id="c8349-121">如果 web 视图中的内容请求打开一个新窗口（通过 "打开" （）等），将引发此事件。</span><span class="sxs-lookup"><span data-stu-id="c8349-121">The event is fired when content inside webview requested to a open a new window (through window.open() and so on.)</span></span>

## <span data-ttu-id="c8349-122">成员</span><span class="sxs-lookup"><span data-stu-id="c8349-122">Members</span></span>

#### <span data-ttu-id="c8349-123">Handled</span><span class="sxs-lookup"><span data-stu-id="c8349-123">Handled</span></span> 

<span data-ttu-id="c8349-124">NewWindowRequestedEvent 是否由主机处理。</span><span class="sxs-lookup"><span data-stu-id="c8349-124">Whether the NewWindowRequestedEvent is handled by host.</span></span>

> <span data-ttu-id="c8349-125">公共 bool 已[处理](#handled)</span><span class="sxs-lookup"><span data-stu-id="c8349-125">public bool [Handled](#handled)</span></span>

<span data-ttu-id="c8349-126">如果此参数为 false 且未设置 NewWindow，则 Web 视图将打开一个弹出窗口，并且该窗口将以打开的 WindowProxy 的形式返回。</span><span class="sxs-lookup"><span data-stu-id="c8349-126">If this is false and no NewWindow is set, the WebView will open a popup window and it will be returned as opened WindowProxy.</span></span> <span data-ttu-id="c8349-127">如果设置为 true 且没有为窗口设置 NewWindow，则打开的 WindowProxy 将针对虚拟窗口对象，并且不会加载任何窗口。</span><span class="sxs-lookup"><span data-stu-id="c8349-127">If set to true and no NewWindow is set for a window.open call, the opened WindowProxy will be for an dummy window object and no window will load.</span></span> <span data-ttu-id="c8349-128">默认值为 false。</span><span class="sxs-lookup"><span data-stu-id="c8349-128">Default is false.</span></span>

#### <span data-ttu-id="c8349-129">IsUserInitiated</span><span class="sxs-lookup"><span data-stu-id="c8349-129">IsUserInitiated</span></span> 

<span data-ttu-id="c8349-130">通过用户笔势（如单击带有目标的定位点标记）启动新的窗口请求时，IsUserInitiated 为 true。</span><span class="sxs-lookup"><span data-stu-id="c8349-130">IsUserInitiated is true when the new window request was initiated through a user gesture such as clicking an anchor tag with target.</span></span>

> <span data-ttu-id="c8349-131">公共 bool [IsUserInitiated](#isuserinitiated)</span><span class="sxs-lookup"><span data-stu-id="c8349-131">public bool [IsUserInitiated](#isuserinitiated)</span></span>

#### <span data-ttu-id="c8349-132">NewWindow</span><span class="sxs-lookup"><span data-stu-id="c8349-132">NewWindow</span></span> 

<span data-ttu-id="c8349-133">获取新窗口。</span><span class="sxs-lookup"><span data-stu-id="c8349-133">Gets the new window.</span></span>

> <span data-ttu-id="c8349-134">公共 CoreWebView2 [NewWindow](#newwindow)</span><span class="sxs-lookup"><span data-stu-id="c8349-134">public CoreWebView2 [NewWindow](#newwindow)</span></span>

#### <span data-ttu-id="c8349-135">Uri</span><span class="sxs-lookup"><span data-stu-id="c8349-135">Uri</span></span> 

<span data-ttu-id="c8349-136">NewWindowRequest 的目标 uri。</span><span class="sxs-lookup"><span data-stu-id="c8349-136">The target uri of the NewWindowRequest.</span></span>

> <span data-ttu-id="c8349-137">公共字符串[Uri](#uri)</span><span class="sxs-lookup"><span data-stu-id="c8349-137">public string [Uri](#uri)</span></span>

<span data-ttu-id="c8349-138">不应导航目标 web 视图。</span><span class="sxs-lookup"><span data-stu-id="c8349-138">The target webview should not be navigated.</span></span> <span data-ttu-id="c8349-139">如果设置了 NewWindow，其顶级窗口将返回为打开的 WindowProxy。</span><span class="sxs-lookup"><span data-stu-id="c8349-139">If the NewWindow is set, its top level window will return as the opened WindowProxy.</span></span>

#### <span data-ttu-id="c8349-140">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="c8349-140">GetDeferral</span></span> 

<span data-ttu-id="c8349-141">获取 CoreWebView2Deferral 对象并将事件置于延迟状态。</span><span class="sxs-lookup"><span data-stu-id="c8349-141">Obtain a CoreWebView2Deferral object and put the event into a deferred state.</span></span>

> <span data-ttu-id="c8349-142">公共 CoreWebView2Deferral [GetDeferral](#getdeferral)（）</span><span class="sxs-lookup"><span data-stu-id="c8349-142">public CoreWebView2Deferral [GetDeferral](#getdeferral)()</span></span>

<span data-ttu-id="c8349-143">你可以使用 CoreWebView2Deferral 对象在以后的时间完成窗口打开请求。</span><span class="sxs-lookup"><span data-stu-id="c8349-143">You can use the CoreWebView2Deferral object to complete the window open request at a later time.</span></span> <span data-ttu-id="c8349-144">当此事件延迟时，opener 窗口将返回到 unnavigated 窗口的 WindowProxy，该窗口将在延迟完成时进行导航。</span><span class="sxs-lookup"><span data-stu-id="c8349-144">While this event is deferred the opener window will be returned a WindowProxy to an unnavigated window, which will navigate when the deferral is complete.</span></span>
