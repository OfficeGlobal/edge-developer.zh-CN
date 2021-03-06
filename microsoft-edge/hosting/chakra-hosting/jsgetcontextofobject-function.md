---
description: 获取对象所属的脚本上下文。
title: JsGetContextOfObject 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cea6cdcd-790f-455c-af04-026af8ae2eb7
caps.latest.revision: 3
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 4f1b996954e877d9c98ac0caf06f255af629a386
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563132"
---
# JsGetContextOfObject 函数
获取对象所属的脚本上下文。  
  
## 语法  
  
```cpp  
STDAPI_(JsErrorCode) JsGetContextOfObject(  
  _In_ JsValueRef object,  
  _Out_ JsContextRef *context  
);  
```  
  
#### 参数  
 `object`  
 要从中获取上下文的对象。  
  
 `context`  
 对象所属的上下文。  
  
## 返回值  
 `JsNoError`如果操作成功，则为代码，否则为失败代码。  
  
## 备注  
 需要活动脚本上下文。  
  
## 要求  
 **页眉：** jsrt  
  
## 另请参阅  
 [应用 (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)