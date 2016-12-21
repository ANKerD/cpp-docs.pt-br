---
title: "Compilador C4645 de aviso (n&#237;vel 3) | Microsoft Docs"
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
  - "C4645"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4645"
ms.assetid: fd7c1ddf-f0d0-4e10-bab9-ccb4c3476298
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Compilador C4645 de aviso (n&#237;vel 3)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

função declarada com \_\_declspec\(noreturn\) tem uma instrução return  
  
 Um [retornar](../Topic/return%20Statement%20in%20Program%20Termination%20\(C++\).md) instrução foi encontrada em uma função que é marcada com o [noreturn](../../cpp/noreturn.md) `__declspec` modificador.  O `return` instrução foi ignorada.  
  
 O exemplo a seguir gera C4645:  
  
```  
// C4645.cpp // compile with:  /W3 void __declspec(noreturn) func() { return;   // C4645, delete this line to resolve } int main() { }  
```