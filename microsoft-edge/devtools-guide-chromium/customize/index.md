---
description: 自定义 Microsoft Edge DevTools 的方法列表
title: 自定义 Microsoft Edge DevTools
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/19/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: 91f353c6b6c4dea2bc6764a972acf2ad52b1f151
ms.sourcegitcommit: 99eee78698dc95b2a3fa638a5b063ef449899cda
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/20/2020
ms.locfileid: "11125081"
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

# 自定义 Microsoft Edge DevTools  

  

此页面列出了自定义 Microsoft Edge DevTools 的方法。  

## “设置”  

**设置**  > **首选项**包含用于自定义 DevTools 的许多选项。  

若要打开 "设置"，请执行下列操作之一：  

*   `F1`在 DevTools 处于焦点时选择。  
*   打开 **主菜单** ，然后选择 " **设置**"。  
    
    :::image type="complex" source="../media/customize-settings-preferences.msft.png" alt-text="设置" lightbox="../media/customize-settings-preferences.msft.png":::
       **设置**  
    :::image-end:::  
    
## 箱  

**抽屉**包含许多隐藏的功能。  

选择 `Escape` 以打开或关闭 **抽屉**。  

:::image type="complex" source="../media/customize-drawer-open.msft.png" alt-text="设置" lightbox="../media/customize-drawer-open.msft.png":::
   **抽屉**  
:::image-end:::  

选择 " **更多** \ (![ 更多 ][ImageMoreIcon] \ ) " 以打开其他 **抽屉** 选项卡。  

:::image type="complex" source="../media/customize-drawer-open-more-tools.msft.png" alt-text="设置" lightbox="../media/customize-drawer-open-more-tools.msft.png":::
   用于打开 **抽屉** 选项卡的按钮  
:::image-end:::  

## 重新排序面板  

单击并拖动 "面板" 选项卡以更改其排序。  您的自定义 tab 键顺序在 DevTools 会话中保持不变。  

> [!NOTE]
> 默认情况下，" **网络** 面板" 选项卡通常是从左侧起的第四个选项卡。  在下图中，" **网络** " 面板是第一个左侧的面板。  

:::image type="complex" source="../media/customize-network-first-position.msft.png" alt-text="设置" lightbox="../media/customize-network-first-position.msft.png":::
   具有自定义面板选项卡排序的 DevTools 窗口  
:::image-end:::  

## 更改 DevTools 位置  

请参阅 [Microsoft Edge DevTools 放置][DevToolsPlacement]。  

:::image type="complex" source="../media/customize-dev-tools-dock-side.msft.png" alt-text="设置" lightbox="../media/customize-dev-tools-dock-side.msft.png":::
   取消停靠 DevTools  
:::image-end:::  

## 深色主题  

请参阅 [启用深色主题][DarkTheme]。  

:::image type="complex" source="../media/customize-settings-appearance-theme.msft.png" alt-text="设置" lightbox="../media/customize-settings-appearance-theme.msft.png":::
   深色主题  
:::image-end:::  

## 试验  

若要启用 DevTools 试验，请完成以下操作。  

1.  导航到 `edge://flags/#enable-devtools-experiments` 。  
1.  选择 " **启用**"。  
1.  选择页面底部的 " **立即重新启动**"。  

下次打开 DevTools 时，将在 "[设置](#settings)" 中显示名为 "**实验**" 的新页面。  

## 与 Microsoft Edge 开发人员工具团队联系  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- image links -->  

[ImageMoreIcon]: ../media/more-icon.msft.png  

<!-- links -->  

[DevToolsPlacement]: ./placement.md "更改 Microsoft Edge DevTools 位置 |Microsoft 文档"  
[DarkTheme]: ./dark-theme.md "在 Microsoft Edge DevTools 中启用深色主题 |Microsoft 文档"  

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/customize/index)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
