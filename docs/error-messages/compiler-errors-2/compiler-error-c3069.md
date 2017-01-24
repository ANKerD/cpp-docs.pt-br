---
title: "C3069 de erro do compilador | Microsoft Docs"
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
  - "C3069"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3069"
ms.assetid: ca94291b-2bb4-4e3f-9acf-534234b83513
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# C3069 de erro do compilador
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'operator': não é permitida para o tipo de enumeração  
  
 Um operador não há suporte para enumerações do CLR.  Para obter mais informações, consulte [usando operadores e enumerações](../Topic/Operators%20and%20Enumerations.md).  
  
## Exemplo  
 O exemplo a seguir gera C3069:  
  
```  
// C3069.cpp // compile with: /clr enum struct E { e1 }; enum F { f1 }; int main() { E e = E::e1; bool tf; tf = !e;   // C3069 // supported for native enums F f = f1; tf = !f; }  
```