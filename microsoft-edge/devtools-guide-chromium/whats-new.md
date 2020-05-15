---
description: 2019年3月在 Microsoft Edge （Chromium） DevTools 中添加的功能
title: 2019年3月的 Microsoft Edge （Chromium） DevTools 中的新增功能
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/11/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: bf1919b0ab46df378880d664dd4e59aee96605e5
ms.sourcegitcommit: 24430258f363b7dd85f7067afd4565bf102b4a1f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "10645320"
---
# <span data-ttu-id="3292c-104">Microsoft Edge 中的新增功能（Chromium） DevTools</span><span class="sxs-lookup"><span data-stu-id="3292c-104">What's new in the Microsoft Edge (Chromium) DevTools</span></span>

<span data-ttu-id="3292c-105">非常感谢你试用下一版本的 Microsoft Edge 的预览版！</span><span class="sxs-lookup"><span data-stu-id="3292c-105">Thank you so much for trying out a preview of the next version of Microsoft Edge!</span></span> <span data-ttu-id="3292c-106">在此版本中，我们通过使用 Chromium 开源项目，在 Microsoft Edge 的基础 web 平台中进行了重大转变。</span><span class="sxs-lookup"><span data-stu-id="3292c-106">With this release, we've undertaken a major shift in the underlying web platform of Microsoft Edge by adopting the Chromium open source project.</span></span> <span data-ttu-id="3292c-107">通过此更改，你可以更轻松地在 Microsoft Edge 中构建和测试你的网站，并确保即使你的用户在不同的基于 Chromium 的浏览器中浏览（如 Google Chrome、Vivaldi、Opera 或 Brave），它们仍将按预期工作。</span><span class="sxs-lookup"><span data-stu-id="3292c-107">With this change, it will be easier for you to build and test your web sites in Microsoft Edge and ensure they will still work as expected even if your users are browsing in a different Chromium-based browser, like Google Chrome, Vivaldi, Opera, or Brave.</span></span>

## <span data-ttu-id="3292c-108">新的 Microsoft Edge （Chromium） DevTools</span><span class="sxs-lookup"><span data-stu-id="3292c-108">The new Microsoft Edge (Chromium) DevTools</span></span>

<span data-ttu-id="3292c-109">如果您要签出 Microsoft Edge，并且主要是在基于 Chromium 的浏览器中开发，则应立即体验。</span><span class="sxs-lookup"><span data-stu-id="3292c-109">If you are checking out Microsoft Edge and you mainly develop in a Chromium-based browser, you should feel right at home.</span></span> <span data-ttu-id="3292c-110">Microsoft Edge （Chromium）开发人员工具与你已了解和使用的开发人员工具完全一样！</span><span class="sxs-lookup"><span data-stu-id="3292c-110">The Microsoft Edge (Chromium) Developer Tools are exactly like the developer tools you already know and use!</span></span>

![Microsoft Edge （Chromium） DevTools](./media/devtools.png)

<span data-ttu-id="3292c-112">如果你要签出下一版本的 Microsoft Edge，并且主要是在 Microsoft Edge （EdgeHTML）中开发的，我们将获得一些非常好的新工具，让你能够更轻松、更快地在 Microsoft Edge 中构建和测试你的网站！</span><span class="sxs-lookup"><span data-stu-id="3292c-112">If you are checking out the next version of Microsoft Edge and you mainly developed in Microsoft Edge (EdgeHTML), we have got some great new tools that we hope will make it easier and faster for you to build and test your web sites in Microsoft Edge!</span></span> <span data-ttu-id="3292c-113">若要了解有关这些新工具的详细信息，请参阅[Microsoft Edge （Chromium） DevTools 指南](../devtools-guide-chromium.md)。</span><span class="sxs-lookup"><span data-stu-id="3292c-113">To learn more about these new tools, check out [The Microsoft Edge (Chromium) DevTools Guide](../devtools-guide-chromium.md).</span></span>

## <span data-ttu-id="3292c-114">适用于 DevTools 的全新深色和浅色主题</span><span class="sxs-lookup"><span data-stu-id="3292c-114">New dark and light themes for the DevTools</span></span>

<span data-ttu-id="3292c-115">我们为 DevTools 设计了一些新的深色和浅色主题，我们认为你会喜欢！</span><span class="sxs-lookup"><span data-stu-id="3292c-115">We've designed some new dark and light themes for the DevTools that we think you'll love!</span></span> <span data-ttu-id="3292c-116">默认情况下，Microsoft Edge （Chromium） DevTools 将使用深色主题。</span><span class="sxs-lookup"><span data-stu-id="3292c-116">By default, the Microsoft Edge (Chromium) DevTools will use the Dark theme.</span></span> <span data-ttu-id="3292c-117">若要更改 DevTools 的主题，请按 `Fn`  +  `F1` Windows 或 Mac 或使用 DevTools 右上角的按钮导航到 "设置" `...` 。</span><span class="sxs-lookup"><span data-stu-id="3292c-117">To change the theme of the DevTools, press `Fn` + `F1` on Windows or Mac or navigate to Settings using the `...` button in the top right corner of the DevTools.</span></span>

![Microsoft Edge （Chromium） DevTools 主菜单](./media/devtools-main-menu.png)

<span data-ttu-id="3292c-119">从 "设置" 中，您可以更改 DevTools 的主题。</span><span class="sxs-lookup"><span data-stu-id="3292c-119">From Settings, you can change the theme of the DevTools.</span></span> <span data-ttu-id="3292c-120">如果你喜欢 DevTools 在基于 Chromium 的浏览器中的显示方式，则可以通过分别选择 "**深色" （Chromium** ）或 "**浅色" （Chromium）** 主题，使 Microsoft Edge （Chromium） DevTools 看起来完全类似。</span><span class="sxs-lookup"><span data-stu-id="3292c-120">If you liked the way the DevTools looked in your Chromium-based browser, you can make the Microsoft Edge (Chromium) DevTools look exactly like them by selecting the **Dark (Chromium)** or **Light (Chromium)** themes respectively.</span></span> 

## <span data-ttu-id="3292c-121">从 VS 代码调试 Microsoft Edge （Chromium）</span><span class="sxs-lookup"><span data-stu-id="3292c-121">Debug Microsoft Edge (Chromium) from VS Code</span></span>

<span data-ttu-id="3292c-122">通过[适用于 Microsoft Edge](https://marketplace.visualstudio.com/items?itemName=msjsdiag.debugger-for-edge)和代码扩展的调试器，现在可以直接从 VS 代码调试 microsoft Edge （EdgeHTML）和 microsoft Edge （Chromium）！</span><span class="sxs-lookup"><span data-stu-id="3292c-122">With the [Debugger for Microsoft Edge](https://marketplace.visualstudio.com/items?itemName=msjsdiag.debugger-for-edge) VS Code extension, you can now debug both Microsoft Edge (EdgeHTML) and Microsoft Edge (Chromium) directly from VS Code!</span></span>

![用于边缘与代码扩展的调试器](./media/vscode-debugger.png)

<span data-ttu-id="3292c-124">若要从 VS 代码启动 Microsoft Edge （Chromium）而不是 Microsoft Edge （EdgeHTML），需要 `version` 使用要启动的 Microsoft edge **launch.json** （ `dev` 、 `beta` 或）版本将属性添加到现有的启动配置 `canary` 。</span><span class="sxs-lookup"><span data-stu-id="3292c-124">To launch Microsoft Edge (Chromium) instead of Microsoft Edge (EdgeHTML) from VS Code, you need to add a `version` attribute to your existing **launch.json** configuration with the version of Microsoft Edge (Chromium) you want to launch (`dev`, `beta`, or `canary`).</span></span> <span data-ttu-id="3292c-125">下面是一个示例**启动**配置，它将启动将 "Chromium" 版本的 Microsoft Edge （）设置为[bing.com](https://www.bing.com/)：</span><span class="sxs-lookup"><span data-stu-id="3292c-125">Here's a sample **launch.json** configuration that will launch the Canary version of Microsoft Edge (Chromium) to [bing.com](https://www.bing.com/):</span></span>

```json
{
    "type": "edge",
    "request": "launch",
    "version": "canary",
    "name": "Launch Microsoft Edge (Chromium) Canary against Bing",
    "url": "https://bing.com"
}
```

<span data-ttu-id="3292c-126">有关详细信息，请参阅[如何从 VS 代码调试 Microsoft Edge （Chromium）](../visual-studio-code/debugger-for-edge.md)。</span><span class="sxs-lookup"><span data-stu-id="3292c-126">For more information, check out [how to debug Microsoft Edge (Chromium) from VS Code](../visual-studio-code/debugger-for-edge.md).</span></span>

## <span data-ttu-id="3292c-127">Edge DevTools 协议更新</span><span class="sxs-lookup"><span data-stu-id="3292c-127">Edge DevTools Protocol update</span></span>

<span data-ttu-id="3292c-128">通过 Microsoft Edge 基础 web 平台中的班次，Edge DevTools 协议将不会收到任何进一步的更新。</span><span class="sxs-lookup"><span data-stu-id="3292c-128">With the shift in the underlying web platform of Microsoft Edge, the Edge DevTools Protocol will not be receiving any further updates.</span></span> <span data-ttu-id="3292c-129">Microsoft Edge （Chromium） DevTools 将使用 Chrome DevTools 协议或 CDP。</span><span class="sxs-lookup"><span data-stu-id="3292c-129">The Microsoft Edge (Chromium) DevTools will use the Chrome DevTools Protocol or CDP.</span></span> <span data-ttu-id="3292c-130">若要参考 CDP 中的域和方法的文档，请参阅[cdp 查看器](https://chromedevtools.github.io/devtools-protocol/tot/Accessibility)。</span><span class="sxs-lookup"><span data-stu-id="3292c-130">To reference documentation on the domains and methods in CDP, please refer to [the CDP viewer](https://chromedevtools.github.io/devtools-protocol/tot/Accessibility).</span></span>

<span data-ttu-id="3292c-131">在下一版本的 Microsoft Edge 中，将不支持任何带前缀的方法 `ms` 。</span><span class="sxs-lookup"><span data-stu-id="3292c-131">In the next version of Microsoft Edge, any methods that are prefixed with `ms` will not be supported.</span></span> <span data-ttu-id="3292c-132">若要了解有关如何在 Microsoft Edge （Chromium）中使用 CDP 的详细信息，请参阅[DevTools 协议（Chromium）](../devtools-protocol-chromium.md)。</span><span class="sxs-lookup"><span data-stu-id="3292c-132">To learn more about how to use CDP in Microsoft Edge (Chromium), please refer to [DevTools Protocol (Chromium)](../devtools-protocol-chromium.md).</span></span>

## <span data-ttu-id="3292c-133">已知问题</span><span class="sxs-lookup"><span data-stu-id="3292c-133">Known issues</span></span>

<span data-ttu-id="3292c-134">从 Microsoft Edge （Chromium） DevTools 到托管在第三方网站上的内容的许多链接已被暂时删除。</span><span class="sxs-lookup"><span data-stu-id="3292c-134">Many links from the Microsoft Edge (Chromium) DevTools to content hosted on third-party sites have been removed temporarily.</span></span> <span data-ttu-id="3292c-135">一旦可以替换这些链接，我们会立即将其添加回 DevTools。</span><span class="sxs-lookup"><span data-stu-id="3292c-135">As soon as we can replace these links, we will add them back to the DevTools.</span></span>


<span data-ttu-id="3292c-136">从 Microsoft Edge （Chromium）调试 Android 设备上的 web 内容时，当您单击 "**远程设备**" 工具中的 "**检查**" 按钮时，启动的 DevTools 版本可能与 Android 设备上的浏览器版本不匹配。</span><span class="sxs-lookup"><span data-stu-id="3292c-136">When debugging web content on an Android device from Microsoft Edge (Chromium), the version of the DevTools that launches when you click the **Inspect** button from the **Remote devices** tool may not match the version of the browser on your Android device.</span></span> <span data-ttu-id="3292c-137">因此，你可能会在 DevTools 中看到不能在 Android 设备上使用浏览器的新功能。</span><span class="sxs-lookup"><span data-stu-id="3292c-137">As a result, you may see new features in the DevTools that will not work against the browser on your Android device.</span></span> <span data-ttu-id="3292c-138">如果这是你遇到的问题，我们希望听到它，请您的[反馈](../devtools-guide-chromium.md#getting-in-touch-with-the-microsoft-edge-devtools-team)！</span><span class="sxs-lookup"><span data-stu-id="3292c-138">If this is something you encounter, we'd love to hear about it so please [file feedback](../devtools-guide-chromium.md#getting-in-touch-with-the-microsoft-edge-devtools-team)!</span></span>

<span data-ttu-id="3292c-139">最后，Windows 和 Mac 上的 Visual Studio 尚不支持 Microsoft Edge （Chromium）。</span><span class="sxs-lookup"><span data-stu-id="3292c-139">Finally, Visual Studio on Windows and Mac does not yet support Microsoft Edge (Chromium).</span></span> <span data-ttu-id="3292c-140">请先注册[此处](https://visualstudio.microsoft.com/vs/preview/)，了解当我们拥有 Visual Studio 预览版（支持在 Microsoft Edge （Chromium）内为 ASP.NET 项目进行 JavaScript 调试时）的第一个版本！</span><span class="sxs-lookup"><span data-stu-id="3292c-140">Sign up [here](https://visualstudio.microsoft.com/vs/preview/) to be the first to know when we have a preview version of Visual Studio that supports JavaScript debugging inside Microsoft Edge (Chromium) for ASP.NET projects!</span></span>  