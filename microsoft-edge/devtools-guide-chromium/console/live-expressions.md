---
description: 如果您发现自己重复在控制台中键入相同的 JavaScript 表达式，请尝试改用实时表达式。
title: 在包含实时表达式的 Real-Time 中观看 JavaScript 表达式值
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/19/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: f6787455863f738d0fa4e014ca8fc318ad83a9cb
ms.sourcegitcommit: 99eee78698dc95b2a3fa638a5b063ef449899cda
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/20/2020
ms.locfileid: "11125228"
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

# 在包含实时表达式的 Real-Time 中观看 JavaScript 表达式值  

如果您发现自己在控制台中重复键入相同的 JavaScript 表达式，您可能会发现创建 **实时表达式**变得更容易。  使用 **实时表达式** ，您只需要键入一个表达式，然后将其固定到您的控制台顶部。  表达式的值几乎实时更新。  

## 创建实时表达式  

1.  [打开控制台][DevToolsConsoleReferenceOpenConsole]。  
1.  选择 " **创建实时表达式** \ (![ 创建实时表达式 ][ImageCreateLiveExpressionIcon] \ ) "。  将显示 " **活动表达式** " 文本框。  
    
    :::image type="complex" source="../media/console-create-live-expression.msft.png" alt-text="在 &quot;活动表达式&quot; 文本框中键入 activeElement" lightbox="../media/console-create-live-expression.msft.png":::
       `document.activeElement`在 "**活动表达式**" 文本框中键入  
    :::image-end:::  
    
1.  选择 `Control` + `Enter` \ (Windows、Linux \ ) 或 `Command` + `Enter` \ (macOS \ ) 保存表达式，或在 "**活动表达式**" 文本框外选择。  

## 与 Microsoft Edge 开发人员工具团队联系  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- image links -->  

[ImageCreateLiveExpressionIcon]: ../media/create-live-expression-icon.msft.png  

<!-- links -->  

[DevToolsConsoleReferenceOpenConsole]: ./reference.md#open-the-console "打开控制台-控制台参考 |Microsoft 文档"  

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/console/live-expressions)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
