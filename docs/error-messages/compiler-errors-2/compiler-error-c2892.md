---
title: "Erro do Compilador C2892 | Microsoft Docs"
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
  - "C2892"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2892"
ms.assetid: c22a5084-2f50-42c2-a56b-6dfe5442edc9
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erro do Compilador C2892
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

a classe local não terá modelos de membro  
  
 As funções de membro de Templated não são válidos em uma classe que é definida em uma função.  
  
 O seguinte exemplo gera C2892:  
  
```  
// C2892.cpp  
int main() {  
   struct local {  
      template<class T>   // C2892  
      void f() {}  
   };  
}  
```