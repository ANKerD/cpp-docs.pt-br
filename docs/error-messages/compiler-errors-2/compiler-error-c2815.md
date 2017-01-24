---
title: "Erro do Compilador C2815 | Microsoft Docs"
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
  - "C2815"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2815"
ms.assetid: d0256fd6-0721-4c99-b03c-52d96e77a613
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erro do Compilador C2815
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

o operador “excluir”: o primeiro parâmetro formal deve ser “void \*”, mas o “param” foi usado  
  
 Qualquer função definida pelo usuário de [a exclusão do operador](../Topic/operator%20delete%20\(%3Cnew%3E\).md) deve usar um primeiro parâmetro formal do tipo `void *`.  
  
 O seguinte exemplo gera C2815:  
  
```  
// C2815.cpp  
// compile with: /c  
class CMyClass {  
public:  
   void mf1(int *a);  
   void operator delete(CMyClass *);   // C2815  
   void operator delete(void *);   
};  
```