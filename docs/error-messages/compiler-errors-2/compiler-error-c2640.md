---
title: "Erro do Compilador C2640 | Microsoft Docs"
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
  - "C2640"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2640"
ms.assetid: e4d137ab-ed1d-457c-9eec-b70d97f1b0b4
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erro do Compilador C2640
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

“identificador”: modificador \_\_based ilegal na referência  
  
 O modificador de `__based` pode ser usado somente em ponteiros.  
  
 O seguinte exemplo gera C2640:  
  
```  
// C2640.cpp  
void f(int i) {  
    void *vp;  
    int _based(vp) &vr = I;  // C2640  
}  
```