---
title: Erro do compilador C3048 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3048
dev_langs:
- C++
helpviewer_keywords:
- C3048
ms.assetid: 48e07091-94d9-471d-befe-7e2507631edd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9d8a0862c0fff7e7ab3caacd7401f92d502c962f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46061715"
---
# <a name="compiler-error-c3048"></a>Erro do compilador C3048

Expressão após '#pragma omp atomic' possui forma inadequada

Uma diretiva atomic foi especificada incorretamente.

O exemplo a seguir gera C3048:

```
// C3048.cpp
// compile with: /openmp vcomps.lib
#include "omp.h"
#include <stdio.h>

int main() {
   int a[10];
   omp_set_num_threads(4);
   #pragma omp parallel
   {
      #pragma omp atomic
      a[0] = 1;   // C3048
      // try the following line instead
      // a[0] += 1;
   }
}
```