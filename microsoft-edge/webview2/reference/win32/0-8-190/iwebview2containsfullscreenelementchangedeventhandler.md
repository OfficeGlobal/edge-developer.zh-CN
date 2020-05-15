---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 适用于 Win32 应用的 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/09/2019
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge
ms.openlocfilehash: f659e6de5cb5bf88593403fad77e56dd1bdcd976
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2020
ms.locfileid: "10653165"
---
# <span data-ttu-id="a8f5a-104">interface IWebView2ContainsFullScreenElementChangedEventHandler</span><span class="sxs-lookup"><span data-stu-id="a8f5a-104">interface IWebView2ContainsFullScreenElementChangedEventHandler</span></span> 

> [!NOTE]
> <span data-ttu-id="a8f5a-105">此接口可能会在 SDK 版本0.8.355 后更改或不可用。</span><span class="sxs-lookup"><span data-stu-id="a8f5a-105">This interface may be altered or unavailable for releases after SDK version 0.8.355.</span></span> <span data-ttu-id="a8f5a-106">请参阅[参考](../../../webview2-api-reference.md)了解最新的 API 参考。</span><span class="sxs-lookup"><span data-stu-id="a8f5a-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface IWebView2ContainsFullScreenElementChangedEventHandler
  : public IUnknown
```

<span data-ttu-id="a8f5a-107">调用方实现此方法以接收 ContainsFullScreenElementChanged 事件。</span><span class="sxs-lookup"><span data-stu-id="a8f5a-107">The caller implements this method to receive the ContainsFullScreenElementChanged events.</span></span>

## <span data-ttu-id="a8f5a-108">摘要</span><span class="sxs-lookup"><span data-stu-id="a8f5a-108">Summary</span></span>

 <span data-ttu-id="a8f5a-109">成员</span><span class="sxs-lookup"><span data-stu-id="a8f5a-109">Members</span></span>                        | <span data-ttu-id="a8f5a-110">描述</span><span class="sxs-lookup"><span data-stu-id="a8f5a-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="a8f5a-111">调用</span><span class="sxs-lookup"><span data-stu-id="a8f5a-111">Invoke</span></span>](#invoke) | <span data-ttu-id="a8f5a-112">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="a8f5a-112">Called to provide the implementer with the event args for the corresponding event.</span></span>

<span data-ttu-id="a8f5a-113">此事件没有事件参数。</span><span class="sxs-lookup"><span data-stu-id="a8f5a-113">There are no event args for this event.</span></span>

## <span data-ttu-id="a8f5a-114">成员</span><span class="sxs-lookup"><span data-stu-id="a8f5a-114">Members</span></span>

#### <span data-ttu-id="a8f5a-115">调用</span><span class="sxs-lookup"><span data-stu-id="a8f5a-115">Invoke</span></span> 

<span data-ttu-id="a8f5a-116">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="a8f5a-116">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="a8f5a-117">公共 HRESULT[调用](#invoke)（[IWebView2WebView5](IWebView2WebView5.md) \* web 视图、IUnknown \* 参数）</span><span class="sxs-lookup"><span data-stu-id="a8f5a-117">public HRESULT [Invoke](#invoke)([IWebView2WebView5](IWebView2WebView5.md) \* webview,IUnknown \* args)</span></span>

<span data-ttu-id="a8f5a-118">没有事件参数，args 参数将为 null。</span><span class="sxs-lookup"><span data-stu-id="a8f5a-118">There are no event args and the args parameter will be null.</span></span>
