---
title: "Erro do Compilador C2234 | Microsoft Docs"
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
  - "C2234"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2234"
ms.assetid: cfa42458-c803-4717-a017-9eca1c0cbfb0
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erro do Compilador C2234
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

“name”: as matrizes das referências são ilegais  
  
 Como os ponteiros para as referências não são permitidos, as matrizes de referências não são possíveis.  
  
 O seguinte exemplo gera C2234:  
  
```  
// C2234.cpp  
int main() {  
   int i = 0, j = 0, k = 0, l = 0;  
   int &array[4] = {i,j,k,l};   // C2234  
   int array2[4] = {i,j,k,l};   // OK  
}  
```