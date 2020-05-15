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
ms.openlocfilehash: 529f4a444b3ad6d0d5831da6015831b077102354
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2020
ms.locfileid: "10652836"
---
# <span data-ttu-id="23a1b-104">interface ICoreWebView2PermissionRequestedEventArgs</span><span class="sxs-lookup"><span data-stu-id="23a1b-104">interface ICoreWebView2PermissionRequestedEventArgs</span></span> 

> [!NOTE]
> <span data-ttu-id="23a1b-105">此接口可能会在 SDK 版本0.9.430 后更改或不可用。</span><span class="sxs-lookup"><span data-stu-id="23a1b-105">This interface may be altered or unavailable for releases after SDK version 0.9.430.</span></span> <span data-ttu-id="23a1b-106">请参阅[参考](../../../webview2-api-reference.md)了解最新的 API 参考。</span><span class="sxs-lookup"><span data-stu-id="23a1b-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2PermissionRequestedEventArgs
  : public IUnknown
```

<span data-ttu-id="23a1b-107">Webview.permissionrequested 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="23a1b-107">Event args for the PermissionRequested event.</span></span>

## <span data-ttu-id="23a1b-108">摘要</span><span class="sxs-lookup"><span data-stu-id="23a1b-108">Summary</span></span>

 <span data-ttu-id="23a1b-109">成员</span><span class="sxs-lookup"><span data-stu-id="23a1b-109">Members</span></span>                        | <span data-ttu-id="23a1b-110">描述</span><span class="sxs-lookup"><span data-stu-id="23a1b-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="23a1b-111">get_Uri</span><span class="sxs-lookup"><span data-stu-id="23a1b-111">get_Uri</span></span>](#get_uri) | <span data-ttu-id="23a1b-112">请求权限的 web 内容的来源。</span><span class="sxs-lookup"><span data-stu-id="23a1b-112">The origin of the web content that requests the permission.</span></span>
[<span data-ttu-id="23a1b-113">get_PermissionKind</span><span class="sxs-lookup"><span data-stu-id="23a1b-113">get_PermissionKind</span></span>](#get_permissionkind) | <span data-ttu-id="23a1b-114">所请求权限的类型。</span><span class="sxs-lookup"><span data-stu-id="23a1b-114">The type of the permission that is requested.</span></span>
[<span data-ttu-id="23a1b-115">get_IsUserInitiated</span><span class="sxs-lookup"><span data-stu-id="23a1b-115">get_IsUserInitiated</span></span>](#get_isuserinitiated) | <span data-ttu-id="23a1b-116">当权限请求通过用户手势启动时为 True。</span><span class="sxs-lookup"><span data-stu-id="23a1b-116">True when the permission request was initiated through a user gesture.</span></span>
[<span data-ttu-id="23a1b-117">get_State</span><span class="sxs-lookup"><span data-stu-id="23a1b-117">get_State</span></span>](#get_state) | <span data-ttu-id="23a1b-118">权限请求的状态，即</span><span class="sxs-lookup"><span data-stu-id="23a1b-118">The status of a permission request, i.e.</span></span>
[<span data-ttu-id="23a1b-119">put_State</span><span class="sxs-lookup"><span data-stu-id="23a1b-119">put_State</span></span>](#put_state) | <span data-ttu-id="23a1b-120">设置 State 属性。</span><span class="sxs-lookup"><span data-stu-id="23a1b-120">Set the State property.</span></span>
[<span data-ttu-id="23a1b-121">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="23a1b-121">GetDeferral</span></span>](#getdeferral) | <span data-ttu-id="23a1b-122">可调用 GetDeferral 以返回[ICoreWebView2Deferral](ICoreWebView2Deferral.md)对象。</span><span class="sxs-lookup"><span data-stu-id="23a1b-122">GetDeferral can be called to return an [ICoreWebView2Deferral](ICoreWebView2Deferral.md) object.</span></span>

## <span data-ttu-id="23a1b-123">成员</span><span class="sxs-lookup"><span data-stu-id="23a1b-123">Members</span></span>

#### <span data-ttu-id="23a1b-124">get_Uri</span><span class="sxs-lookup"><span data-stu-id="23a1b-124">get_Uri</span></span> 

<span data-ttu-id="23a1b-125">请求权限的 web 内容的来源。</span><span class="sxs-lookup"><span data-stu-id="23a1b-125">The origin of the web content that requests the permission.</span></span>

> <span data-ttu-id="23a1b-126">公共 HRESULT [get_Uri](#get_uri)（LPWSTR \* Uri）</span><span class="sxs-lookup"><span data-stu-id="23a1b-126">public HRESULT [get_Uri](#get_uri)(LPWSTR \* uri)</span></span>

#### <span data-ttu-id="23a1b-127">get_PermissionKind</span><span class="sxs-lookup"><span data-stu-id="23a1b-127">get_PermissionKind</span></span> 

<span data-ttu-id="23a1b-128">所请求权限的类型。</span><span class="sxs-lookup"><span data-stu-id="23a1b-128">The type of the permission that is requested.</span></span>

> <span data-ttu-id="23a1b-129">public HRESULT [get_PermissionKind](#get_permissionkind)（CORE_WEBVIEW2_PERMISSION_KIND \* 值）</span><span class="sxs-lookup"><span data-stu-id="23a1b-129">public HRESULT [get_PermissionKind](#get_permissionkind)(CORE_WEBVIEW2_PERMISSION_KIND \* value)</span></span>

#### <span data-ttu-id="23a1b-130">get_IsUserInitiated</span><span class="sxs-lookup"><span data-stu-id="23a1b-130">get_IsUserInitiated</span></span> 

<span data-ttu-id="23a1b-131">当权限请求通过用户手势启动时为 True。</span><span class="sxs-lookup"><span data-stu-id="23a1b-131">True when the permission request was initiated through a user gesture.</span></span>

> <span data-ttu-id="23a1b-132">public HRESULT [get_IsUserInitiated](#get_isuserinitiated)（BOOL \* IsUserInitiated）</span><span class="sxs-lookup"><span data-stu-id="23a1b-132">public HRESULT [get_IsUserInitiated](#get_isuserinitiated)(BOOL \* isUserInitiated)</span></span>

<span data-ttu-id="23a1b-133">注意，通过用户手势启动并不意味着用户打算访问关联的资源。</span><span class="sxs-lookup"><span data-stu-id="23a1b-133">Note that being initiated through a user gesture doesn't mean that user intended to access the associated resource.</span></span>

#### <span data-ttu-id="23a1b-134">get_State</span><span class="sxs-lookup"><span data-stu-id="23a1b-134">get_State</span></span> 

<span data-ttu-id="23a1b-135">权限请求的状态，即</span><span class="sxs-lookup"><span data-stu-id="23a1b-135">The status of a permission request, i.e.</span></span>

> <span data-ttu-id="23a1b-136">public HRESULT [get_State](#get_state)（CORE_WEBVIEW2_PERMISSION_STATE \* 值）</span><span class="sxs-lookup"><span data-stu-id="23a1b-136">public HRESULT [get_State](#get_state)(CORE_WEBVIEW2_PERMISSION_STATE \* value)</span></span>

<span data-ttu-id="23a1b-137">是否授予请求。</span><span class="sxs-lookup"><span data-stu-id="23a1b-137">whether the request is granted.</span></span> <span data-ttu-id="23a1b-138">默认值为 CORE_WEBVIEW2_PERMISSION_STATE_DEFAULT。</span><span class="sxs-lookup"><span data-stu-id="23a1b-138">Default value is CORE_WEBVIEW2_PERMISSION_STATE_DEFAULT.</span></span>

#### <span data-ttu-id="23a1b-139">put_State</span><span class="sxs-lookup"><span data-stu-id="23a1b-139">put_State</span></span> 

<span data-ttu-id="23a1b-140">设置 State 属性。</span><span class="sxs-lookup"><span data-stu-id="23a1b-140">Set the State property.</span></span>

> <span data-ttu-id="23a1b-141">public HRESULT [put_State](#put_state)（CORE_WEBVIEW2_PERMISSION_STATE 值）</span><span class="sxs-lookup"><span data-stu-id="23a1b-141">public HRESULT [put_State](#put_state)(CORE_WEBVIEW2_PERMISSION_STATE value)</span></span>

#### <span data-ttu-id="23a1b-142">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="23a1b-142">GetDeferral</span></span> 

<span data-ttu-id="23a1b-143">可调用 GetDeferral 以返回[ICoreWebView2Deferral](ICoreWebView2Deferral.md)对象。</span><span class="sxs-lookup"><span data-stu-id="23a1b-143">GetDeferral can be called to return an [ICoreWebView2Deferral](ICoreWebView2Deferral.md) object.</span></span>

> <span data-ttu-id="23a1b-144">公共 HRESULT [GetDeferral](#getdeferral)（[ICoreWebView2Deferral](ICoreWebView2Deferral.md) \* \* 延迟）</span><span class="sxs-lookup"><span data-stu-id="23a1b-144">public HRESULT [GetDeferral](#getdeferral)([ICoreWebView2Deferral](ICoreWebView2Deferral.md) \*\* deferral)</span></span>

<span data-ttu-id="23a1b-145">开发人员可以使用延迟对象在以后的时间做出权限决定。</span><span class="sxs-lookup"><span data-stu-id="23a1b-145">Developer can use the deferral object to make the permission decision at a later time.</span></span>
