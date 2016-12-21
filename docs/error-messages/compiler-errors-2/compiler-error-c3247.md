---
title: "C3247 de erro do compilador | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3247"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3247"
ms.assetid: f9a2bbb5-3fce-40bf-9fd3-835a5f164dbb
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# C3247 de erro do compilador
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'class1': coclass não pode herdar de outra coclass 'class2'  
  
 Uma classe marcada com o [coclass](../../windows/coclass.md) atributo não pode herdar de outra classe marcada com o `coclass` atributo.  
  
 O exemplo a seguir gera C3247:  
  
```  
// C3247.cpp [module(name="MyLib")]; [coclass] class a { }; [coclass] class b : public a {   // C3247 }; int main() { }  
```