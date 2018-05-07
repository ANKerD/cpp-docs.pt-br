---
title: C3483 de erro do compilador | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3483
dev_langs:
- C++
helpviewer_keywords:
- C3483
ms.assetid: 18b3a2c5-dfc9-4661-9653-08a5798474cf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5e2605674ff701f70f7be6ea1b4158c9f8f0c6ad
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3483"></a>C3483 de erro do compilador
'var' já é parte da lista de captura de lambda  
  
 Você passou a mesma variável à lista de captura de uma expressão lambda mais de uma vez.  
  
### <a name="to-correct-this-error"></a>Para corrigir este erro  
  
-   Remova todas as instâncias adicionais da variável na lista de captura.  
  
## <a name="example"></a>Exemplo  
 O exemplo a seguir gera C3483 porque a variável `n` aparece mais de uma vez na lista de captura da expressão lambda:  
  
```  
// C3483.cpp  
  
int main()  
{  
   int m = 6, n = 5;  
   [m,n,n] { return n + m; }(); // C3483  
}  
```  
  
## <a name="see-also"></a>Consulte também  
 [Expressões Lambda](../../cpp/lambda-expressions-in-cpp.md)