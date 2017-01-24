---
title: "Erro do Compilador C3671 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3671"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3671"
ms.assetid: d684e4ae-87e2-4424-80bb-6f346652c831
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erro do Compilador C3671
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

“function\_1”: a função não substitui “function\_2”  
  
 Ao usar a sintaxe explícita de substituição, o compilador gerencie um erro se uma função não será substituída.  Consulte [Explicit Overrides](../../windows/explicit-overrides-cpp-component-extensions.md) para maiores informações.  
  
## Exemplo  
 O exemplo a seguir produz C3671.  
  
```  
// C3671.cpp  
// compile with: /clr /c  
ref struct S {  
   virtual void f();  
};  
  
ref struct S1 : S {  
   virtual void f(int) new sealed = S::f;   // C3671  
   virtual void f() new sealed = S::f;  
};  
```