---
title: "Erro do Compilador C3083 | Microsoft Docs"
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
  - "C3083"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3083"
ms.assetid: 05ff791d-52bb-41eb-9511-3ef89d7f4710
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erro do Compilador C3083
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

função “”: o símbolo à esquerda de um “::” deve ser um tipo  
  
 Uma função foi chamada incorretamente.  
  
## Exemplo  
 O exemplo a seguir produz C3083.  
  
```  
// C3083.cpp  
// compile with: /c  
struct N {  
   ~N();  
};  
  
struct N1 {  
   ~N1();  
};  
  
N::N::~N() {}   // C3083  
N1::~N1() {}   // OK  
```