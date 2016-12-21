---
title: "Erro do Compilador C2754 | Microsoft Docs"
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
  - "C2754"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2754"
ms.assetid: 1cab66c5-da9d-4b81-b7fb-9cdc48ff1ccc
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erro do Compilador C2754
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

“especialização”: uma especialização parcial não pode ter um parâmetro dependente de modelo que não seja do tipo  
  
 Foi feita uma tentativa de especializar parcialmente uma classe do modelo que tem um parâmetro dependente de modelo que não seja do tipo.  Isso não é permitido.  
  
 O seguinte exemplo gera C2754:  
  
```  
// C2754.cpp  
// compile with: /c  
  
template<class T, T t>  
struct A {};  
  
template<class T, int N>  
struct B {};  
  
template<class T> struct A<T,5> {};   // C2754  
template<> struct A<int,5> {};   // OK  
template<class T> struct B<T,5> {};   // OK  
```