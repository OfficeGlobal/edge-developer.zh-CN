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
ms.openlocfilehash: 28ed6db251095e2baf6474950c6839dc4a5a8633
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2020
ms.locfileid: "10653238"
---
# <span data-ttu-id="773f2-104">CoreWebView2PhysicalKeyStatus 结构的 WebView2</span><span class="sxs-lookup"><span data-stu-id="773f2-104">Microsoft.Web.WebView2.Core.CoreWebView2PhysicalKeyStatus struct</span></span> 

<span data-ttu-id="773f2-105">命名空间： Microsoft WebView2 </span><span class="sxs-lookup"><span data-stu-id="773f2-105">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="773f2-106">程序集： Microsoft WebView2</span><span class="sxs-lookup"><span data-stu-id="773f2-106">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="773f2-107">一个结构，表示打包到给定给 Win32 键事件的 LPARAM 中的信息。</span><span class="sxs-lookup"><span data-stu-id="773f2-107">A structure representing the information packed into the LPARAM given to a Win32 key event.</span></span>

## <span data-ttu-id="773f2-108">摘要</span><span class="sxs-lookup"><span data-stu-id="773f2-108">Summary</span></span>

 <span data-ttu-id="773f2-109">成员</span><span class="sxs-lookup"><span data-stu-id="773f2-109">Members</span></span>                        | <span data-ttu-id="773f2-110">描述</span><span class="sxs-lookup"><span data-stu-id="773f2-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="773f2-111">IsExtendedKey</span><span class="sxs-lookup"><span data-stu-id="773f2-111">IsExtendedKey</span></span>](#isextendedkey) | <span data-ttu-id="773f2-112">指示该键是否为扩展键。</span><span class="sxs-lookup"><span data-stu-id="773f2-112">Indicates whether the key is an extended key.</span></span>
[<span data-ttu-id="773f2-113">IsKeyReleased</span><span class="sxs-lookup"><span data-stu-id="773f2-113">IsKeyReleased</span></span>](#iskeyreleased) | <span data-ttu-id="773f2-114">切换状态。</span><span class="sxs-lookup"><span data-stu-id="773f2-114">The transition state.</span></span>
[<span data-ttu-id="773f2-115">IsMenuKeyDown</span><span class="sxs-lookup"><span data-stu-id="773f2-115">IsMenuKeyDown</span></span>](#ismenukeydown) | <span data-ttu-id="773f2-116">上下文代码。</span><span class="sxs-lookup"><span data-stu-id="773f2-116">The context code.</span></span>
[<span data-ttu-id="773f2-117">RepeatCount</span><span class="sxs-lookup"><span data-stu-id="773f2-117">RepeatCount</span></span>](#repeatcount) | <span data-ttu-id="773f2-118">当前消息的重复次数。</span><span class="sxs-lookup"><span data-stu-id="773f2-118">The repeat count for the current message.</span></span>
[<span data-ttu-id="773f2-119">ScanCode</span><span class="sxs-lookup"><span data-stu-id="773f2-119">ScanCode</span></span>](#scancode) | <span data-ttu-id="773f2-120">扫描代码。</span><span class="sxs-lookup"><span data-stu-id="773f2-120">The scan code.</span></span>
[<span data-ttu-id="773f2-121">WasKeyDown</span><span class="sxs-lookup"><span data-stu-id="773f2-121">WasKeyDown</span></span>](#waskeydown) | <span data-ttu-id="773f2-122">以前的键状态。</span><span class="sxs-lookup"><span data-stu-id="773f2-122">The previous key state.</span></span>

<span data-ttu-id="773f2-123">有关详细信息，请参阅 WM_KEYDOWN 的文档 [https://docs.microsoft.com/windows/win32/inputdev/wm-keydown](https://docs.microsoft.com/windows/win32/inputdev/wm-keydown) 。</span><span class="sxs-lookup"><span data-stu-id="773f2-123">See the documentation for WM_KEYDOWN for details at [https://docs.microsoft.com/windows/win32/inputdev/wm-keydown](https://docs.microsoft.com/windows/win32/inputdev/wm-keydown).</span></span>

## <span data-ttu-id="773f2-124">成员</span><span class="sxs-lookup"><span data-stu-id="773f2-124">Members</span></span>

#### <span data-ttu-id="773f2-125">IsExtendedKey</span><span class="sxs-lookup"><span data-stu-id="773f2-125">IsExtendedKey</span></span> 

<span data-ttu-id="773f2-126">指示该键是否为扩展键。</span><span class="sxs-lookup"><span data-stu-id="773f2-126">Indicates whether the key is an extended key.</span></span>

> <span data-ttu-id="773f2-127">公共 int [IsExtendedKey](#isextendedkey)</span><span class="sxs-lookup"><span data-stu-id="773f2-127">public int [IsExtendedKey](#isextendedkey)</span></span>

#### <span data-ttu-id="773f2-128">IsKeyReleased</span><span class="sxs-lookup"><span data-stu-id="773f2-128">IsKeyReleased</span></span> 

<span data-ttu-id="773f2-129">切换状态。</span><span class="sxs-lookup"><span data-stu-id="773f2-129">The transition state.</span></span>

> <span data-ttu-id="773f2-130">公共 int [IsKeyReleased](#iskeyreleased)</span><span class="sxs-lookup"><span data-stu-id="773f2-130">public int [IsKeyReleased](#iskeyreleased)</span></span>

#### <span data-ttu-id="773f2-131">IsMenuKeyDown</span><span class="sxs-lookup"><span data-stu-id="773f2-131">IsMenuKeyDown</span></span> 

<span data-ttu-id="773f2-132">上下文代码。</span><span class="sxs-lookup"><span data-stu-id="773f2-132">The context code.</span></span>

> <span data-ttu-id="773f2-133">公共 int [IsMenuKeyDown](#ismenukeydown)</span><span class="sxs-lookup"><span data-stu-id="773f2-133">public int [IsMenuKeyDown](#ismenukeydown)</span></span>

#### <span data-ttu-id="773f2-134">RepeatCount</span><span class="sxs-lookup"><span data-stu-id="773f2-134">RepeatCount</span></span> 

<span data-ttu-id="773f2-135">当前消息的重复次数。</span><span class="sxs-lookup"><span data-stu-id="773f2-135">The repeat count for the current message.</span></span>

> <span data-ttu-id="773f2-136">公共 uint [RepeatCount](#repeatcount)</span><span class="sxs-lookup"><span data-stu-id="773f2-136">public uint [RepeatCount](#repeatcount)</span></span>

#### <span data-ttu-id="773f2-137">ScanCode</span><span class="sxs-lookup"><span data-stu-id="773f2-137">ScanCode</span></span> 

<span data-ttu-id="773f2-138">扫描代码。</span><span class="sxs-lookup"><span data-stu-id="773f2-138">The scan code.</span></span>

> <span data-ttu-id="773f2-139">公共 uint [ScanCode](#scancode)</span><span class="sxs-lookup"><span data-stu-id="773f2-139">public uint [ScanCode](#scancode)</span></span>

#### <span data-ttu-id="773f2-140">WasKeyDown</span><span class="sxs-lookup"><span data-stu-id="773f2-140">WasKeyDown</span></span> 

<span data-ttu-id="773f2-141">以前的键状态。</span><span class="sxs-lookup"><span data-stu-id="773f2-141">The previous key state.</span></span>

> <span data-ttu-id="773f2-142">公共 int [WasKeyDown](#waskeydown)</span><span class="sxs-lookup"><span data-stu-id="773f2-142">public int [WasKeyDown](#waskeydown)</span></span>
