---
title: "Erro do Compilador C2575 | Microsoft Docs"
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
  - "C2575"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2575"
ms.assetid: 9eb45706-37ef-4481-b373-6d193ba13634
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erro do Compilador C2575
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

“identificador”: apenas funções de membro e as bases podem ser virtuais  
  
 Uma função ou uma classe global são declaradas `virtual`.  Isso não é permitido.  
  
 O seguinte exemplo gera C2575:  
  
```  
// C2575.cpp  
// compile with: /c  
virtual void func() {}   // C2575  
  
void func2() {}  
struct A {  
   virtual void func2(){}  
};  
```