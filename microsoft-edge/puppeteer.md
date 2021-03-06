---
description: 在 Microsoft Edge 中使用 Puppeteer 自动处理和测试
title: Puppeteer
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/01/2020
ms.topic: article
ms.prod: microsoft-edge
ms.technology: devtools
keywords: microsoft edge，web 开发，开发人员，工具，自动化，测试
ms.openlocfilehash: bef3f0d7472f7bc595998829546fb540041f20fc
ms.sourcegitcommit: b88d2a55a59db8373ff2bac275d3730977bf19c9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/01/2020
ms.locfileid: "10986155"
---
# Puppeteer  

[Puppeteer][|::ref1::|Main] 是一个 [节点][NodejsMain] 库，它提供了一个高级 API，可通过 [DevTools 协议][GithubChromedevtoolsProtocol]控制 Microsoft Edge \ (Chromium \ ) 。  默认情况下，Puppeteer 运行无 [头][WikiHeadlessBrowser] ，这意味着你看不到 UI，而是必须使用命令行。  您也可以将 Puppeteer 配置为运行完整 \ (非外设 \ ) Microsoft Edge 或 Chromium。  

默认情况下，当你安装 Puppeteer 时，安装程序将下载 [Chromium][ChromiumHome]的最新版本， [还会生成 Microsoft Edge][MicrosoftBlogsWindowsExperience20181206]的 "开放源代码浏览器"。  如果已安装了 Microsoft Edge \ (Chromium \ ) ，则可以使用 [puppeteer-core][PuppeteerApivscore]。  `puppeteer-core` 是一种轻量级版本的 Puppeteer，用于启动现有的浏览器安装，如 Microsoft Edge \ (Chromium \ ) 。  若要下载 Microsoft Edge \ (Chromium \ ) ，请参阅 [下载 Microsoft Edge 预览体验成员频道][MicrosoftedgeinsiderDownload]。

## 安装 puppeteer  

你可以 `puppeteer-core` 通过以下命令之一添加到你的网站或应用。  

```shell
npm i puppeteer-core
```  

```shell
yarn add puppeteer-core
```  

## 通过 puppeteer 启动 Microsoft Edge  

> [!NOTE]
> `puppeteer-core` 依赖于节点 v 8.9.0 或更高版本。  下面的示例使用 `async` / `await` 了仅在节点 v 7.6.0 或更高版本中才受支持的示例。  `node -v`从命令行运行以确保你有兼容版本的 Node.js。  

`puppeteer-core` 应熟悉其他浏览器测试框架（如 [WebDriver][WebDriverEdgehtmlMain]）的用户。  创建一个浏览器实例，打开一个页面，然后使用 Puppeteer API 对其进行操作。  在以下代码示例中， `puppeteer-core` 启动 Microsoft Edge \ (Chromium \ ) ，导航到 `https://www.microsoftedgeinsider.com` 并将屏幕截图另存为 `example.png` 。  

复制下面的代码示例并将其另存为 `example.js` 。  

```javascript
const puppeteer = require('puppeteer-core');

(async () => {
  const browser = await puppeteer.launch({
    executablePath: 'C:\\Program Files (x86)\\Microsoft\\Edge Dev\\Application\\msedge.exe'
  });
  const page = await browser.newPage();
  await page.goto('https://www.microsoftedgeinsider.com');
  await page.screenshot({path: 'example.png'});

  await browser.close();
})();
```  

更改 `executablePath` 为指向 Microsoft Edge \ (Chromium \ ) 的安装。  例如，在 macOS 上，" `executablePath` Microsoft Edge" 的 "关于" 应设置为 `/Applications/Microsoft\ Edge\ Canary.app/` 。  若要查找 `executablePath` ，请导航到 `edge://version` 该页面并复制该页面上的 **可执行路径** ，或安装带有以下命令之一的 [edge 路径][npmEdgePaths] 程序包。  

```shell
npm i edge-paths
```  

```shell
yarn add edge-paths
```  
 
下面的代码示例使用 [edge 路径][npmEdgePaths] 程序包以编程方式查找 Microsoft edge \ (Chromium \ ) 在操作系统上的安装路径。

```javascript
const edgePaths = require("edge-paths");

const EDGE_PATH = edgePaths.getEdgePath();
```

最后，设置 `executablePath: EDGE_PATH` `example.js` 。  保存更改。  

> [!NOTE]
> Microsoft Edge \ (EdgeHTML \ ) 不起作用 `puppeteer-core` 。  必须安装 [Microsoft Edge 预览体验成员频道][MicrosoftedgeinsiderDownload] 才能继续关注此示例。  

现在 `example.js` 从命令行运行。  

```shell
node example.js
```  

`puppeteer-core` 启动 Microsoft Edge，导航到 `https://www.microsoftedgeinsider.com` 页面的 800px x 600px 屏幕截图并将其保存。  你可以自定义 [setViewport ( # B1 ][PuppeteerApipagesetviewport]的页面大小。  

:::image type="complex" source="./media/puppeteer-example.png" alt-text="由 example.js 生成的 example.png 文件":::
   图1： `example.png` 生成的文件 `example.js`  
:::image-end:::  

<!--  
> ##### Figure 1  
> The `example.png` file produced by `example.js`  
> ![The example.png file produced by example.js](./media/puppeteer-example.png)  
-->  

这只是由 Puppeteer 和的自动化和测试方案所支持的简单示例 `puppeteer-core` 。  有关 Puppeteer 及其工作原理的详细信息，请参阅 [Puppeteer][|::ref2::|Main]。  

## 与 Microsoft Edge 开发人员工具团队联系  

Microsoft Edge 开发人员团队渴望听到有关使用 Puppeteer、 `puppeteer-core` 和 Microsoft Edge 的反馈。  使用 Microsoft Edge DevTools 或 tweet [@EdgeDevTools][TwitterIntentTweetEdgedevtools]中的 &quot;**发送反馈**" 图标，让 Microsoft edge 团队知道您的想法。  


:::image type="complex" source="./devtools-guide-chromium/media/bing-devtools-send-feedback.msft.png" alt-text="由 example.js 生成的 example.png 文件":::
   图1： `example.png` 生成的文件 `example.js`  
:::image-end:::  

<!--  
> ##### Figure 1  
> The `example.png` file produced by `example.js`  
> ![The example.png file produced by example.js](./media/puppeteer-example.png)  
-->  

这只是由 Puppeteer 和的自动化和测试方案所支持的简单示例 `puppeteer-core` 。  有关 Puppeteer 及其工作原理的详细信息，请参阅 [Puppeteer][|::ref2::|Main]。  

## 与 Microsoft Edge 开发人员工具团队联系  

Microsoft Edge 开发人员团队渴望听到有关使用 Puppeteer、 `puppeteer-core` 和 Microsoft Edge 的反馈。  使用 Microsoft Edge DevTools 或 tweet [@EdgeDevTools][TwitterIntentTweetEdgedevtools]中的 &quot;**发送反馈**"  
[PuppeteerApivscore]: https://pptr.dev/#?product=Puppeteer&version=v2.0.0&show=api-puppeteer-vs-puppeteer-core "puppeteer 与 puppeteer-核心 |Puppeteer"  
[PuppeteerApipagesetviewport]: https://pptr.dev/#?product=Puppeteer&version=v2.0.0&show=api-pagesetviewportviewport "setViewport (视区) |Puppeteer"  

[TwitterIntentTweetEdgedevtools]: https://twitter.com/intent/tweet?text=@EdgeDevTools "@EdgeDevTools 发布 Tweet |Twitter"  

[WikiHeadlessBrowser]: https://en.wikipedia.org/wiki/Headless_browser "无外设浏览器 |科"  
