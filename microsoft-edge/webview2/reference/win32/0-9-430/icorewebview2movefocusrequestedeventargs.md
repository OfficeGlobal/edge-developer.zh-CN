---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 适用于 Win32 应用的 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/24/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html
ms.openlocfilehash: cd60598e220f4cf474a288a5120b7e75c2b5f0a3
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2020
ms.locfileid: "10653211"
---
# <span data-ttu-id="58c8d-104">interface ICoreWebView2MoveFocusRequestedEventArgs</span><span class="sxs-lookup"><span data-stu-id="58c8d-104">interface ICoreWebView2MoveFocusRequestedEventArgs</span></span> 

> [!NOTE]
> <span data-ttu-id="58c8d-105">此接口可能会在 SDK 版本0.9.430 后更改或不可用。</span><span class="sxs-lookup"><span data-stu-id="58c8d-105">This interface may be altered or unavailable for releases after SDK version 0.9.430.</span></span> <span data-ttu-id="58c8d-106">请参阅[参考](../../../webview2-api-reference.md)了解最新的 API 参考。</span><span class="sxs-lookup"><span data-stu-id="58c8d-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2MoveFocusRequestedEventArgs
  : public IUnknown
```

<span data-ttu-id="58c8d-107">MoveFocusRequested 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="58c8d-107">Event args for the MoveFocusRequested event.</span></span>

## <span data-ttu-id="58c8d-108">摘要</span><span class="sxs-lookup"><span data-stu-id="58c8d-108">Summary</span></span>

 <span data-ttu-id="58c8d-109">成员</span><span class="sxs-lookup"><span data-stu-id="58c8d-109">Members</span></span>                        | <span data-ttu-id="58c8d-110">描述</span><span class="sxs-lookup"><span data-stu-id="58c8d-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="58c8d-111">get_Reason</span><span class="sxs-lookup"><span data-stu-id="58c8d-111">get_Reason</span></span>](#get_reason) | <span data-ttu-id="58c8d-112">Web 视图触发 MoveFocus 请求事件的原因。</span><span class="sxs-lookup"><span data-stu-id="58c8d-112">The reason for WebView to fire the MoveFocus Requested event.</span></span>
[<span data-ttu-id="58c8d-113">get_Handled</span><span class="sxs-lookup"><span data-stu-id="58c8d-113">get_Handled</span></span>](#get_handled) | <span data-ttu-id="58c8d-114">指示事件是否已由应用处理。</span><span class="sxs-lookup"><span data-stu-id="58c8d-114">Indicate whether the event has been handled by the app.</span></span>
[<span data-ttu-id="58c8d-115">put_Handled</span><span class="sxs-lookup"><span data-stu-id="58c8d-115">put_Handled</span></span>](#put_handled) | <span data-ttu-id="58c8d-116">设置已处理的属性。</span><span class="sxs-lookup"><span data-stu-id="58c8d-116">Set the Handled property.</span></span>

## <span data-ttu-id="58c8d-117">成员</span><span class="sxs-lookup"><span data-stu-id="58c8d-117">Members</span></span>

#### <span data-ttu-id="58c8d-118">get_Reason</span><span class="sxs-lookup"><span data-stu-id="58c8d-118">get_Reason</span></span> 

<span data-ttu-id="58c8d-119">Web 视图触发 MoveFocus 请求事件的原因。</span><span class="sxs-lookup"><span data-stu-id="58c8d-119">The reason for WebView to fire the MoveFocus Requested event.</span></span>

> <span data-ttu-id="58c8d-120">public HRESULT [get_Reason](#get_reason)（CORE_WEBVIEW2_MOVE_FOCUS_REASON \* 值）</span><span class="sxs-lookup"><span data-stu-id="58c8d-120">public HRESULT [get_Reason](#get_reason)(CORE_WEBVIEW2_MOVE_FOCUS_REASON \* value)</span></span>

#### <span data-ttu-id="58c8d-121">get_Handled</span><span class="sxs-lookup"><span data-stu-id="58c8d-121">get_Handled</span></span> 

<span data-ttu-id="58c8d-122">指示事件是否已由应用处理。</span><span class="sxs-lookup"><span data-stu-id="58c8d-122">Indicate whether the event has been handled by the app.</span></span>

> <span data-ttu-id="58c8d-123">公共 HRESULT [get_Handled](#get_handled)（布尔 \* 值）</span><span class="sxs-lookup"><span data-stu-id="58c8d-123">public HRESULT [get_Handled](#get_handled)(BOOL \* value)</span></span>

<span data-ttu-id="58c8d-124">如果应用已将焦点移动到所需位置，则应将 "已处理" 属性设置为 TRUE。</span><span class="sxs-lookup"><span data-stu-id="58c8d-124">If the app has moved the focus to its desired location, it should set Handled property to TRUE.</span></span> <span data-ttu-id="58c8d-125">当已处理的属性在事件处理程序返回后为 false 时，将采取默认操作。</span><span class="sxs-lookup"><span data-stu-id="58c8d-125">When Handled property is false after the event handler returns, default action will be taken.</span></span> <span data-ttu-id="58c8d-126">默认操作是尝试在应用中查找下一个制表位子窗口，然后尝试将焦点移动到该窗口。</span><span class="sxs-lookup"><span data-stu-id="58c8d-126">The default action is to try to find the next tab stop child window in the app and try to move focus to that window.</span></span> <span data-ttu-id="58c8d-127">如果没有其他此类窗口将焦点移至，则焦点将在 web 视图的 web 内容中循环。</span><span class="sxs-lookup"><span data-stu-id="58c8d-127">If there is no other such window to move focus to, focus will be cycled within the WebView's web content.</span></span>

#### <span data-ttu-id="58c8d-128">put_Handled</span><span class="sxs-lookup"><span data-stu-id="58c8d-128">put_Handled</span></span> 

<span data-ttu-id="58c8d-129">设置已处理的属性。</span><span class="sxs-lookup"><span data-stu-id="58c8d-129">Set the Handled property.</span></span>

> <span data-ttu-id="58c8d-130">public HRESULT [put_Handled](#put_handled)（布尔值）</span><span class="sxs-lookup"><span data-stu-id="58c8d-130">public HRESULT [put_Handled](#put_handled)(BOOL value)</span></span>
