---
title: "C2636 de erro do compilador | Microsoft Docs"
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
  - "C2636"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2636"
ms.assetid: 379873ec-8d05-49f8-adf1-b067bc07bdb8
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# C2636 de erro do compilador
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier': ponteiro para membro de referência é ilegal  
  
 Um ponteiro para um membro de referência foi declarado.  
  
 O exemplo a seguir gera C2636:  
  
```  
// C2636.cpp  
struct S {};  
int main() {  
   int &S::*prs;   // C2636  
   int S::*prs1;   // OK  
   int *S::*prs2;   // OK  
}  
```