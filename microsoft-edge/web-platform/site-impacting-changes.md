---
description: 此页面提供可能会影响网站兼容性的高影响更改的摘要
title: 网站兼容性-影响到 Microsoft Edge 的更改
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/13/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、兼容性、web 平台
ms.openlocfilehash: c35f38bd43255ab9a8c965c8fa9f3b1c8a95bff6
ms.sourcegitcommit: 1760ea15e83045168aec6bf507bc4fe7dfb5568f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2020
ms.locfileid: "10652298"
---
# <span data-ttu-id="cb6a2-104">网站兼容性-影响到 Microsoft Edge 的更改</span><span class="sxs-lookup"><span data-stu-id="cb6a2-104">Site compatibility-impacting changes coming to Microsoft Edge</span></span>  

<span data-ttu-id="cb6a2-105">Web 不断发展，以改进用户体验、安全性和隐私。</span><span class="sxs-lookup"><span data-stu-id="cb6a2-105">The web is constantly evolving to improve the user experience, security, and privacy.</span></span>  <span data-ttu-id="cb6a2-106">在某些情况下，所做的更改可能会显著影响现有页面的功能。</span><span class="sxs-lookup"><span data-stu-id="cb6a2-106">In some cases, changes may be significant enough to impact the functionality of existing pages.</span></span>  <span data-ttu-id="cb6a2-107">下表总结了 Microsoft Edge 团队当前正在跟踪的最高影响的更改。</span><span class="sxs-lookup"><span data-stu-id="cb6a2-107">The table below summarizes particularly high-impact changes that the Microsoft Edge team is currently tracking.</span></span>  <span data-ttu-id="cb6a2-108">请经常回来查看;Microsoft Edge 团队将在思考演变、时间表实体化和新更改发布时更新此页面。</span><span class="sxs-lookup"><span data-stu-id="cb6a2-108">Please check back often; the Microsoft Edge team updates this page as thinking evolves, timelines solidify, and new changes are announced.</span></span>  

| <span data-ttu-id="cb6a2-109">“更改”</span><span class="sxs-lookup"><span data-stu-id="cb6a2-109">Change</span></span> | <span data-ttu-id="cb6a2-110">Stable 渠道</span><span class="sxs-lookup"><span data-stu-id="cb6a2-110">Stable Channel</span></span> | <span data-ttu-id="cb6a2-111">实验</span><span class="sxs-lookup"><span data-stu-id="cb6a2-111">Experimentation</span></span> | <span data-ttu-id="cb6a2-112">其他信息</span><span class="sxs-lookup"><span data-stu-id="cb6a2-112">Additional information</span></span> |  
|:--- |:--- |:--- |:--- |
| <span data-ttu-id="cb6a2-113">Cookie 默认为</span><span class="sxs-lookup"><span data-stu-id="cb6a2-113">Cookies default to</span></span> `SameSite=Lax` | [<span data-ttu-id="cb6a2-114">Chrome 或 Chrome + 1</span><span class="sxs-lookup"><span data-stu-id="cb6a2-114">Chrome or Chrome+1</span></span>](#release-comments)  | <span data-ttu-id="cb6a2-115">V82、Dev v82</span><span class="sxs-lookup"><span data-stu-id="cb6a2-115">Canary v82, Dev v82</span></span> | <span data-ttu-id="cb6a2-116">此更改在 Chromium 项目中发生，Microsoft Edge 基于该项目。</span><span class="sxs-lookup"><span data-stu-id="cb6a2-116">This change is happening in the Chromium project, on which Microsoft Edge is based.</span></span>  <span data-ttu-id="cb6a2-117">有关此更改的 Google 的详细信息（包括 Google 的计划时序表），请查看[Chrome 平台状态条目][ChromePlatformStatus5088147346030592]。</span><span class="sxs-lookup"><span data-stu-id="cb6a2-117">For more information, including the planned timeline by Google for this change, please review the [Chrome Platform Status entry][ChromePlatformStatus5088147346030592].</span></span>  |  
| <span data-ttu-id="cb6a2-118">引用策略：默认为</span><span class="sxs-lookup"><span data-stu-id="cb6a2-118">Referrer Policy: Default to</span></span> `strict-origin-when-cross-origin` | [<span data-ttu-id="cb6a2-119">Chrome 或 Chrome + 1</span><span class="sxs-lookup"><span data-stu-id="cb6a2-119">Chrome or Chrome+1</span></span>](#release-comments)  | <span data-ttu-id="cb6a2-120">V79、Dev v79</span><span class="sxs-lookup"><span data-stu-id="cb6a2-120">Canary v79, Dev v79</span></span> | <span data-ttu-id="cb6a2-121">此更改在 Chromium 项目中发生，Microsoft Edge 基于该项目。</span><span class="sxs-lookup"><span data-stu-id="cb6a2-121">This change is happening in the Chromium project, on which Microsoft Edge is based.</span></span>  <span data-ttu-id="cb6a2-122">有关此更改的 Google 的详细信息（包括 Google 的计划时序表），请查看[Chrome 平台状态条目][ChromePlatformStatus6251880185331712]。</span><span class="sxs-lookup"><span data-stu-id="cb6a2-122">For more information, including the planned timeline by Google for this change, please review the [Chrome Platform Status entry][ChromePlatformStatus6251880185331712].</span></span>  |  
| <span data-ttu-id="cb6a2-123">在页面消除期间禁止同步 XmlHttpRequest</span><span class="sxs-lookup"><span data-stu-id="cb6a2-123">Disallow synchronous XmlHttpRequest in page dismissal</span></span> | <span data-ttu-id="cb6a2-124">[Chrome + 1](#release-comments) \ （Edge v83 \）</span><span class="sxs-lookup"><span data-stu-id="cb6a2-124">[Chrome+1](#release-comments) \(Edge v83\)</span></span> |  | <span data-ttu-id="cb6a2-125">此更改在 Chromium 项目中发生，Microsoft Edge 基于该项目。</span><span class="sxs-lookup"><span data-stu-id="cb6a2-125">This change is happening in the Chromium project, on which Microsoft Edge is based.</span></span>  <span data-ttu-id="cb6a2-126">匹配的 Chrome，Microsoft Edge 将提供一个组策略来禁用此更改，直到 Edge 88。</span><span class="sxs-lookup"><span data-stu-id="cb6a2-126">Matching Chrome, Microsoft Edge offers a Group Policy to disable this change until Edge 88.</span></span>  <span data-ttu-id="cb6a2-127">有关此更改的 Google 的详细信息（包括 Google 的计划时序表），请查看[Chrome 平台状态条目][ChromePlatformStatus4664843055398912]。</span><span class="sxs-lookup"><span data-stu-id="cb6a2-127">For more information, including the planned timeline by Google for this change, please review the [Chrome Platform Status entry][ChromePlatformStatus4664843055398912].</span></span>  |  
| <span data-ttu-id="cb6a2-128">显示提示权限请求的微妙提示</span><span class="sxs-lookup"><span data-stu-id="cb6a2-128">Display subtle prompt for notification permissions requests</span></span> |  | <span data-ttu-id="cb6a2-129">V83、Dev v83</span><span class="sxs-lookup"><span data-stu-id="cb6a2-129">Canary v83, Dev v83</span></span> | <span data-ttu-id="cb6a2-130">用户现在可以选择在中发出静音通知请求 `edge://settings/content/notifications` 。</span><span class="sxs-lookup"><span data-stu-id="cb6a2-130">Users may now opt into Quiet Notification Requests in `edge://settings/content/notifications`.</span></span>  <span data-ttu-id="cb6a2-131">启用此设置后，Microsoft Edge 将在地址栏中为请求使用或 API 向用户发送通知的网站显示一个微妙的请求图标 `Notifications` `Push` 。</span><span class="sxs-lookup"><span data-stu-id="cb6a2-131">With this setting enabled, Microsoft Edge displays a subtle request icon in the address bar for sites which request to send users future notifications using the `Notifications` or `Push` API.</span></span>  <span data-ttu-id="cb6a2-132">这种精致的图标取代了浮出权限提示。</span><span class="sxs-lookup"><span data-stu-id="cb6a2-132">This subtle icon replaces the flyout permission prompt.</span></span>  <span data-ttu-id="cb6a2-133">在所有请求通知权限的网站上，在 "未线" 和 "开发" 的实验中，对于某些用户，默认情况下会打开此行为。</span><span class="sxs-lookup"><span data-stu-id="cb6a2-133">An experiment in Canary and Dev turns this behavior on by default for some users, on all sites that request notifications permissions.</span></span>  <span data-ttu-id="cb6a2-134">用户可能会选择退出 `edge://settings/content/notifications` 。</span><span class="sxs-lookup"><span data-stu-id="cb6a2-134">Users may opt out in `edge://settings/content/notifications`.</span></span>  <span data-ttu-id="cb6a2-135">将来，Microsoft edge 团队可能会根据用户行为和其他输入来浏览在特定情况下显示出控件提示。</span><span class="sxs-lookup"><span data-stu-id="cb6a2-135">In the future, the Microsoft edge team may explore displaying the flyout prompt in specific situations based on user behaviors and other input.</span></span>  |  
| <span data-ttu-id="cb6a2-136">默认情况下禁用 TLS/1.0 和 TLS/1。1</span><span class="sxs-lookup"><span data-stu-id="cb6a2-136">Disable TLS/1.0 and TLS/1.1 by default</span></span> | <span data-ttu-id="cb6a2-137">Edge v84</span><span class="sxs-lookup"><span data-stu-id="cb6a2-137">Edge v84</span></span> |  | <span data-ttu-id="cb6a2-138">若要帮助发现受影响的网站，你可以将该 `edge://flags/#display-legacy-tls-warnings` 标志设置为导致 Microsoft Edge 在加载需要旧版 TLS 协议的页面时显示非阻止 "不安全" 通知。</span><span class="sxs-lookup"><span data-stu-id="cb6a2-138">To help discover impacted sites, you may set the `edge://flags/#display-legacy-tls-warnings` flag to cause Microsoft Edge to display a non-blocking "Not Secure" notice when loading pages that require legacy TLS protocols.</span></span>  <span data-ttu-id="cb6a2-139">[SSLMinVersion][DeployedEdgePoliciesSSLMinVersion]组策略允许重新启用 TLS/1.0 和 tls/1.1;该策略将保持可用，直到 Edge 88。</span><span class="sxs-lookup"><span data-stu-id="cb6a2-139">The [SSLMinVersion][DeployedEdgePoliciesSSLMinVersion] Group Policy permits re-enabling of TLS/1.0 and TLS/1.1; the policy remains available until Edge 88.</span></span>  |  
| <span data-ttu-id="cb6a2-140">阻止混合内容下载</span><span class="sxs-lookup"><span data-stu-id="cb6a2-140">Block mixed content downloads</span></span> | <span data-ttu-id="cb6a2-141">[Chrome + 1](#release-comments) \ （Edge v85 \）</span><span class="sxs-lookup"><span data-stu-id="cb6a2-141">[Chrome+1](#release-comments) \(Edge v85\)</span></span>  |  | <span data-ttu-id="cb6a2-142">此更改在 Chromium 项目中发生，Microsoft Edge 基于该项目。</span><span class="sxs-lookup"><span data-stu-id="cb6a2-142">This change is happening in the Chromium project, on which Microsoft Edge is based.</span></span>  <span data-ttu-id="cb6a2-143">有关此更改的 Google 的详细信息（包括 Google 的计划时序表），请查看[google 安全博客条目][GoogleBlogSecurity20200206]。</span><span class="sxs-lookup"><span data-stu-id="cb6a2-143">For more information, including the planned timeline by Google for this change, please review the [Google security blog entry][GoogleBlogSecurity20200206].</span></span>  <span data-ttu-id="cb6a2-144">在 Chrome 之后的一个版本计划中，Microsoft 推出针对警告或阻止的文件类型的推出计划。</span><span class="sxs-lookup"><span data-stu-id="cb6a2-144">The Microsoft rollout schedule on file types to warn or block is planned for one release after Chrome.</span></span>  |  

##### <span data-ttu-id="cb6a2-145">发布评论</span><span class="sxs-lookup"><span data-stu-id="cb6a2-145">Release comments</span></span>  

:::row:::
   :::column span="1":::
      <span data-ttu-id="cb6a2-146">Chrome + 1</span><span class="sxs-lookup"><span data-stu-id="cb6a2-146">Chrome+1</span></span>
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="cb6a2-147">根据用户和开发人员的反馈，指示的功能或更改将在 Chrome 后附带一个版本。</span><span class="sxs-lookup"><span data-stu-id="cb6a2-147">Based on user and developer feedback, the indicated feature or change ships one release after Chrome.</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="1":::
      <span data-ttu-id="cb6a2-148">Chrome 或 Chrome + 1</span><span class="sxs-lookup"><span data-stu-id="cb6a2-148">Chrome or Chrome+1</span></span>
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="cb6a2-149">根据用户和开发人员的反馈，指定的功能或更改将在同一时间或在 Chrome 后发布。</span><span class="sxs-lookup"><span data-stu-id="cb6a2-149">Based on user and developer feedback, the indicated feature or change ships at the same time or one release after Chrome.</span></span>
   :::column-end:::
:::row-end:::


<!-- image links -->  

<!-- links -->  

[DeployedEdgePoliciesSSLMinVersion]: /deployedge/microsoft-edge-policies#sslversionmin "SSLVersionMin-Microsoft Edge-策略"  

[ChromePlatformStatus4664843055398912]: https://www.chromestatus.com/feature/4664843055398912 "不允许 XHR 中的同步页面消除 JavaScript-Chrome 平台状态"  
[ChromePlatformStatus5088147346030592]: https://www.chromestatus.com/feature/5088147346030592 "Cookie 默认为 SameSite = 不严格-Chrome 平台状态"  
[ChromePlatformStatus6251880185331712]: https://www.chromestatus.com/feature/6251880185331712 "引用策略：默认情况下为 "严格"-"在原点时"-"交叉时"-Chrome 平台状态"  

[GoogleBlogSecurity20200206]: https://security.googleblog.com/2020/02/protecting-users-from-insecure_6.html "保护用户不受 Google Chrome-Google Online 安全博客中的不安全下载"  