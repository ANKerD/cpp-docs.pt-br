---
title: "Erro do Compilador C2760 | Microsoft Docs"
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
  - "C2760"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2760"
ms.assetid: 585757fd-d519-43f3-94e5-50316ac8b90b
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erro do Compilador C2760
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

erro de sintaxe: “nome1\/nome2\/nome3 esperado” não “name2”  
  
 Um operador de conversão é usado com um operador válido.  
  
 O seguinte exemplo gera C2760:  
  
```  
// C2760.cpp  
class B {};  
class D : public B {};  
  
void f(B* pb) {  
    D* pd1 = static_cast<D*>(pb);  
    D* pd2 = static_cast<D*>=(pb);  // C2760  
    D* pd3 = static_cast<D*=(pb);   // C2760  
}  
```