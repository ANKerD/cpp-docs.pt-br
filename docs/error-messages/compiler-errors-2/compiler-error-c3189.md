---
title: "Erro do Compilador C3189 | Microsoft Docs"
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
  - "C3189"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3189"
ms.assetid: b254de79-931e-4a59-a9f4-1c690d90ca5e
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erro do Compilador C3189
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'declarator\<\>'abstrata de typeidtype: essa sintaxe é mais suporte, use no lugar de ::typeid  
  
 Um formulário obsoleto de [typeid](../Topic/typeid%20%20\(C++%20Component%20Extensions\).md) foi usado, usa o novo formulário.  
  
 O seguinte exemplo gera C3189:  
  
```  
// C3189.cpp  
// compile with: /clr  
int main() {  
   System::Type^ t  = typeid<System::Object>;   // C3189  
   System::Type^ t2  = System::Object::typeid;   // OK  
}  
```