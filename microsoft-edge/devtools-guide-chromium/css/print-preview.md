---
description: 打开 "呈现" 选项卡，然后选择 "模拟 CSS 媒体" > "打印"。
title: '强制 Microsoft Edge DevTools 到打印预览模式 (CSS 打印媒体类型) '
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/19/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: d4e8e06d60461ac4cdcab8686a18a0698d52f6e3
ms.sourcegitcommit: 99eee78698dc95b2a3fa638a5b063ef449899cda
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/20/2020
ms.locfileid: "11125116"
---
<!-- Copyright Kayce Basques 

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       https://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.  -->

# 强制 Microsoft Edge DevTools 到打印预览模式 (CSS 打印媒体类型)   

" [打印媒体" 查询][MDNUsingMediaQueries] 将控制页面打印时的外观。  若要强制页面进入 "打印预览" 模式，请执行以下操作：  

1.  选择 `Control` + `Shift` + `P` \ (Windows、Linux \ ) 或 `Command` + `Shift` + `P` \ (macOS \ ) 打开 "**命令" 菜单**。  
    
    :::image type="complex" source="../media/css-console-command-menu-rendering.msft.png" alt-text="命令菜单" lightbox="../media/css-console-command-menu-rendering.msft.png":::
       **命令菜单**  
    :::image-end:::  
    
1.  键入 `rendering` ，选择 " **显示呈现**"，然后选择 `Enter` 。  
1.  在 " **模拟 CSS 媒体** " 下，选择 " **打印**"。  
    
    :::image type="complex" source="../media/css-elements-styles-qs-rendering-emulate-css-media-print.msft.png" alt-text="命令菜单" lightbox="../media/css-elements-styles-qs-rendering-emulate-css-media-print.msft.png":::
       打印预览模式  
    :::image-end:::  
    
在此处，您可以查看和更改您的 CSS，就像任何其他网页一样。  请参阅 [查看和更改 CSS 入门][DevToolsCSSGetStarted]。  

## 与 Microsoft Edge 开发人员工具团队联系  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[MicrosoftEdgeDevTools]: ../../devtools-guide-chromium.md "Microsoft Edge (Chromium) 开发工具 |Microsoft 文档"  
[DevToolsCSSGetStarted]: ./index.md "开始使用查看和更改 CSS |Microsoft 文档"  

[MDNUsingMediaQueries]: https://developer.mozilla.org/docs/Web/CSS/Media_Queries/Using_media_queries "使用媒体查询 |MDN"  

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/css/print-preview)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
