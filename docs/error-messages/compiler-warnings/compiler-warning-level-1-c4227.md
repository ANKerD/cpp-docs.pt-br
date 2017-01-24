---
title: "Aviso do compilador (n&#237;vel 1) C4227 | Microsoft Docs"
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
  - "C4227"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4227"
ms.assetid: 78f98374-c00b-4000-aefa-1b1c67b4666b
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Aviso do compilador (n&#237;vel 1) C4227
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

anacronismo usado: os qualificadores na referência são ignorados  
  
 Usar qualificadores como `const` ou `volatile` com referências C\+\+ é uma prática desatualizada.  
  
## Exemplo  
  
```  
// C4227.cpp  
// compile with: /W1 /c  
int j = 0;  
int &const i = j;   // C4227  
```