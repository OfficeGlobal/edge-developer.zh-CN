---
description: 确保您的网站上的媒体内容按预期方式工作
title: 自动播放策略-开发人员指南
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/28/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: 边缘、媒体、视频、音频、自动播放
ms.custom: seodec18
ms.openlocfilehash: 39c9bd8e9921167dfc3a9ab1a4cc12b2157f0f6f
ms.sourcegitcommit: 29cbe0f464ba0092e025f502833eb9cc3e02ee89
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "10942058"
---
# 自动播放策略  

[!INCLUDE [deprecation-note](../../includes/legacy-edge-note.md)]  

Microsoft Edge 使客户能够在通过自动播放媒体和声音的网站上个性化浏览首选项，从而最大限度地减少 web 上的干扰并节省带宽。  此外，Microsoft Edge 会自动取消自动播放后台选项卡中的媒体。  

用户可以自定义 [全局](#global-media-autoplay-settings) 自动播放控件和 [每个网站](#per-site-media-autoplay-settings) 的媒体行为，这些控件提供以下选项：  

*   `Allow`  默认情况下，当首次在前台查看选项卡时，将继续播放视频，具体取决于网站的决定。  

*   `Limit`  将 "自动播放" 限制为仅在视频静音时工作，因此用户永远不会因声音而感到惊讶。  一旦用户单击页面上的任意位置，"自动播放" 将重新启用，并将在该选项卡中的该域内继续允许。  

*   `Block`  在用户直接与媒体内容交互之前，防止所有网站上的 sautoplay。  

## 全局媒体自动播放设置  

用户可以在 "**高级设置**  >  **媒体自动播放**" 下控制所有网站的默认自动播放行为。  

:::image type="complex" source="../media/autoplay_global.png" alt-text="全局媒体自动播放设置" lightbox="../media/autoplay_global.png":::
   全局媒体自动播放设置  
:::image-end:::  

## 每个网站的媒体自动播放设置  

用户可以在 "网站信息" 窗格的 " **网站权限** " 部分的每个网站上控制 "自动播放" 行为。  单击地址栏左侧的 "信息" 图标或 "锁定" 图标，然后单击 " **媒体自动播放设置** " 以开始，可找到此设置。  

按网站设置将覆盖全局设置。  例如，如果用户的全局设置设置为 `Allow` "将每个网站设置更改为 `Block` "，则将阻止该网站的自动播放。  

:::image type="complex" source="../media/autoplay_per-site.png" alt-text="全局媒体自动播放设置" lightbox="../media/autoplay_per-site.png":::
   每个网站的媒体自动播放设置  
:::image-end:::  

## Web 开发人员的最佳做法  

下面介绍了如何确保你的网站上托管的媒体具有良好的用户体验：  

*   假设媒体元素的每个用途都需要用户笔势来启动播放 \ (，因为用户可以在任何时间点阻止自动播放 \ ) 并相应地计划。  全局和每网站自动播放策略适用于所有 `<audio>` 和 `<video>` 元素，无论它们在网站上的使用方式  

*   确保媒体控件始终显示在网站媒体和广告内容中。  这将使用户能够在页面上阻止自动播放时重启播放。  

*   评估自动播放如何影响用户在您的网站上的体验，并考虑以最小化不需要的媒体播放的方式使用 "自动播放"。  如果 "自动播放" 是你的体验的重要部分，请考虑使用静音内容启动，并允许用户取消静音。  对于静音内容以自动播放，音频源必须显式静音或不进行设置。  否则，该元素将不会被视为静音。  

*   除非绝对必要，否则使用本机浏览器控件进行媒体播放。  这将确保用户体验的一致性。  如果你改为生成自定义控件，请确保媒体控件始终存在，并且你的控件对 "自动播放" 抑制做出正确反应。  

### Iframe 委派  

中的 "自动播放" `<iframe>` 将从父页面继承自动播放权限，而不管内容来源。  在每个媒体文件由单独的 iframe 托管的播放列表方案中，用户只需为整个播放列表启动一次播放。  

### 在允许自动播放时检测  

你可以通过检查媒体元素上的函数返回的承诺，调整播放控件以在自动播放被阻止时显示正确状态 `play()` ：  

```javascript
var promise = document.querySelector('video').play();

if (promise !== undefined) { 
    promise.catch(_error => { 
        // Autoplay was blocked
        // Show user media controls to manually start playback
    }).then(() => { 
        // Autoplay started
    }); 
}
```  
