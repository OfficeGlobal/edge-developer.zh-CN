---
description: 如何从 VS 代码调试 Microsoft Edge （Chromium）和 Microsoft Edge （EdgeHTML）
title: 从 VS 代码调试 Microsoft Edge （Chromium）
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/07/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools、vs 代码、visual studio 代码、调试器
ms.openlocfilehash: 58bcbc927505f4c5a1f493349c3e9475cb75e1be
ms.sourcegitcommit: c1b5fdd48d39d874a76c9b8f68309eb1b507fd0b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2020
ms.locfileid: "10695864"
---
# Microsoft Edge 与代码扩展的调试器  

借助[适用于 Microsoft Edge][VisualstudioMarketplaceDebuggerMicrosoftEdge]和代码扩展的调试器，逐行调试你的前端 JavaScript 代码行并 `console.log()` 直接从[Visual Studio 代码][VisualstudioCode]中查看语句！  

:::image type="complex" source="./media/debugger-for-edge.gif" alt-text="适用于工作的调试器与代码扩展":::
   适用于工作的调试器与代码扩展  
:::image-end:::

<!--![Debugger for Edge VS Code extension at work][ImageGifDebuggerEdge]  -->  

## 启动 Microsoft Edge  

导航到活动栏中的 "调试" 视图 \ （ `Ctrl` + `Shift` + `D` 在 Windows 或 `Command` + `Shift` + `D` " **Activity Bar**macOS \" 上）。  如果 VS 代码中没有任何配置，请按 `F5` Windows 或 macOS 或选择绿色的 "**播放**" 按钮。  在下拉列表中选择 "**边缘**"。  你应该会看到 `launch.json` 具有以下配置的文件。  

```json
{
    "version": "0.2.0",
    "configurations": [
        {
            "type": "edge",
            "request": "launch",
            "name": "Launch Edge against localhost",
            "url": "http://localhost:8080",
            "webRoot": "${workspaceFolder}"
        }
    ]
}
```  

如果您按 `F5` Windows 或 macOS 或再次选择绿色的 "**播放**" 按钮，则 VS 代码将启动 Microsoft Edge \ （EdgeHTML \），并且您可以 `8080` 直接从 VS 代码调试在端口上运行的任何 web 项目！  

### Microsoft Edge (Chromium)  

如果想要启动 Microsoft Edge \ （Chromium \），请使用 microsoft edge 的下一版本，而不是 Microsoft Edge \ （EdgeHTML \），只需将属性添加到你的 `version` 现有配置，使用要启动 \ （ `dev` 、或 \）的 Microsoft Edge \ （Chromium \）版本 `beta` `canary` 。 下面的配置将启动 Microsoft Edge \ （Chromium \）的 "不限" 版本。  

```json
{
    "type": "edge",
    "request": "launch",
    "version": "canary",
    "name": "Launch Edge against localhost",
    "url": "http://localhost:8080",
    "webRoot": "${workspaceFolder}"
}
```  

## 附加到 Microsoft Edge  

将 VS 代码附加到 Microsoft Edge \ （Chromium \）。  在终端中，运行以下命令。  

```console
start msedge --remote-debugging-port=9222
```  

将下面的配置添加到你的 `launch.json` 文件。   

```json
{
    "type": "edge",
    "request": "attach",
    "name": "Attach to Edge",
    "port": 9222
}
```  

如果现在运行此配置，则 VS 代码附加到 Microsoft Edge \ （Chromium \），然后开始调试！  

## 与 Microsoft Edge 和代码扩展团队的元素保持联系    

通过在扩展的[GitHub][GithubMicrosoftVscodeEdgeDebug2]存储库中[归档问题][GithubMicrosoftVscodeEdgeDebug2NewIssue]来发送反馈。  请包含调试适配器日志文件，该文件是在具有名称的目录中的每个运行中创建的 `%temp%` `vscode-edge-debug2.txt` 。  将此文件拖动到问题注释中，将其上传到 GitHub。  

为了帮助使 Microsoft Edge 与代码扩展的元素更好，您的发布内容是欢迎的！  在扩展的[GitHub][GithubMicrosoftVscodeEdgeDebug2]存储库中查找所需的所有内容。  


<!-- image links -->  

<!--[ImageGifDebuggerEdge]: ./media/debugger-for-edge.gif "Debugger for Edge VS Code extension in action"  -->  
[ImagePngDebuggerEdge]：/media/debugger-for-edge.png "调试程序 for Edge 与代码扩展在操作中"  

<!--links -->  

[VisualstudioCode]: https://code.visualstudio.com "Visual Studio 代码"  
[VisualStudioCodeDocs]: https://code.visualstudio.com/Docs "文档 |Visual Studio 代码"   

[GithubMicrosoftVscodeEdgeDebug2]: https://github.com/Microsoft/vscode-edge-debug2 "microsoft/vscode-edge-debug2 |GitHub"  
[GithubMicrosoftVscodeEdgeDebug2NewIssue]: https://github.com/Microsoft/vscode-edge-debug2/issues/new "新问题-microsoft/vscode-debug2 |GitHub"  

[VisualstudioMarketplaceDebuggerMicrosoftEdge]: https://marketplace.visualstudio.com/items?itemName=msjsdiag.debugger-for-edge "Microsoft Edge 的调试器 |Visual Studio Marketplace"  