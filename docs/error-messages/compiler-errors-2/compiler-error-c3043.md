---
title: Erro do compilador C3043 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3043
dev_langs:
- C++
helpviewer_keywords:
- C3043
ms.assetid: 0ef55e63-e82b-48eb-9d44-690950ac34c6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ff64629e5385185f524a4f76d9b959d107b53563
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46041708"
---
# <a name="compiler-error-c3043"></a>Erro do compilador C3043

Diretiva de OpenMP 'critical' não pode ser aninhada em diretiva 'critical' com o mesmo nome

Um [críticos](../../parallel/openmp/reference/critical.md) diretiva não pode ser aninhada em uma `critical` diretiva que usa o mesmo nome.

O exemplo a seguir gera C3043:

```
// C3043.cpp
// compile with: /openmp /c
#include "omp.h"

int main() {
   int n1 = 1, n2 = 2, n3 = 3;

   #pragma omp parallel
   {
      ++n2;

      #pragma omp critical(MyTest)
      {
         ++n2;

         #pragma omp critical(MyTest)   // C3043
         // try the following line instead
         // #pragma omp critical(MyTest2)
         {
            ++n3;
         }
      }
   }
}
```