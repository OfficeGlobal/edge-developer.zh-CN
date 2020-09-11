---
description: '通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术 (HTML、CSS 和 JavaScript) '
title: WebView2 Win32 c + + ICoreWebView2SourceChangedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/09/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html、ICoreWebView2SourceChangedEventArgs
ms.openlocfilehash: 7417b4790d327bbd5a415dc1237e0604963598e0
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2020
ms.locfileid: "11011779"
---
# interface ICoreWebView2SourceChangedEventArgs 

```
interface ICoreWebView2SourceChangedEventArgs
  : public IUnknown
```

SourceChanged 事件的事件参数。

## 摘要

 成员                        | 描述
--------------------------------|---------------------------------------------
[get_IsNewDocument](#get_isnewdocument) | 如果要导航到的页面是新文档，则为 True。

## 成员

#### get_IsNewDocument 

如果要导航到的页面是新文档，则为 True。

> 公共 HRESULT [get_IsNewDocument](#get_isnewdocument) (BOOL * IsNewDocument) 
