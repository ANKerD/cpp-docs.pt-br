---
title: "Erro do Compilador C2531 | Microsoft Docs"
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
  - "C2531"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2531"
ms.assetid: c49afe15-55f8-4dc8-ac01-bf653622a7db
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erro do Compilador C2531
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

“identificador”: referência a um campo de bit ilegal  
  
 As referências a campos de bit não são permitidas.  
  
 O seguinte exemplo gera C2531:  
  
```  
// C2531.cpp  
// compile with: /c  
class P {  
   int &b1 : 10;   // C2531  
   int b2 : 10;   // OK  
};  
```