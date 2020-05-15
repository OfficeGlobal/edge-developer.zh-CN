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
ms.openlocfilehash: c23e6bcd18e3b0fe7d2ee9b279e65fc81fe89d3d
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2020
ms.locfileid: "10652860"
---
# <span data-ttu-id="321b1-104">interface IWebView2WebResourceRequestedEventArgs2</span><span class="sxs-lookup"><span data-stu-id="321b1-104">interface IWebView2WebResourceRequestedEventArgs2</span></span> 

> [!NOTE]
> <span data-ttu-id="321b1-105">此接口可能会在 SDK 版本0.8.355 后更改或不可用。</span><span class="sxs-lookup"><span data-stu-id="321b1-105">This interface may be altered or unavailable for releases after SDK version 0.8.355.</span></span> <span data-ttu-id="321b1-106">请参阅[参考](../../../webview2-api-reference.md)了解最新的 API 参考。</span><span class="sxs-lookup"><span data-stu-id="321b1-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface IWebView2WebResourceRequestedEventArgs2
  : public IWebView2WebResourceRequestedEventArgs
```

<span data-ttu-id="321b1-107">WebResourceRequested 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="321b1-107">Event args for the WebResourceRequested event.</span></span>

## <span data-ttu-id="321b1-108">摘要</span><span class="sxs-lookup"><span data-stu-id="321b1-108">Summary</span></span>

 <span data-ttu-id="321b1-109">成员</span><span class="sxs-lookup"><span data-stu-id="321b1-109">Members</span></span>                        | <span data-ttu-id="321b1-110">描述</span><span class="sxs-lookup"><span data-stu-id="321b1-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="321b1-111">get_ResourceContext</span><span class="sxs-lookup"><span data-stu-id="321b1-111">get_ResourceContext</span></span>](#get_resourcecontext) | <span data-ttu-id="321b1-112">Web 资源请求上下文。</span><span class="sxs-lookup"><span data-stu-id="321b1-112">The web resource request contexts.</span></span>

## <span data-ttu-id="321b1-113">成员</span><span class="sxs-lookup"><span data-stu-id="321b1-113">Members</span></span>

#### <span data-ttu-id="321b1-114">get_ResourceContext</span><span class="sxs-lookup"><span data-stu-id="321b1-114">get_ResourceContext</span></span> 

<span data-ttu-id="321b1-115">Web 资源请求上下文。</span><span class="sxs-lookup"><span data-stu-id="321b1-115">The web resource request contexts.</span></span>

> <span data-ttu-id="321b1-116">公共 HRESULT [get_ResourceContext](#get_resourcecontext)（WEBVIEW2_WEB_RESOURCE_CONTEXT \* 上下文）</span><span class="sxs-lookup"><span data-stu-id="321b1-116">public HRESULT [get_ResourceContext](#get_resourcecontext)(WEBVIEW2_WEB_RESOURCE_CONTEXT \* context)</span></span>
