---
title: C2761 de erro do compilador | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2761
dev_langs:
- C++
helpviewer_keywords:
- C2761
ms.assetid: 38c79a05-b56d-485b-820f-95e8c0cb926f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 62c505b5219cb76ad83c3b6ece13e7d10f16e555
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2761"></a>C2761 de erro do compilador
'function': redeclaração de função de membro não permitida  
  
 Você não pode declarar novamente uma função de membro. Você pode defini-lo, mas não declará-lo novamente.  
  
## <a name="example"></a>Exemplo  
 O exemplo a seguir gera C2761.  
  
```  
// C2761.cpp  
class a {  
   int t;  
   void test();  
};  
  
void a::a;     // C2761  
void a::test;  // C2761  
  
```  
  
## <a name="example"></a>Exemplo  
 Membros não estáticos de uma classe ou estrutura não podem ser definidos.  O exemplo a seguir gera C2761.  
  
```  
// C2761_b.cpp  
// compile with: /c  
struct C {  
   int s;  
   static int t;  
};  
  
int C::s;   // C2761  
int C::t;   // OK  
```