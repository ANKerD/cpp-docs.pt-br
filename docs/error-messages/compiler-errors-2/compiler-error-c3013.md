---
title: Erro do compilador C3013 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3013
dev_langs:
- C++
helpviewer_keywords:
- C3013
ms.assetid: f896777d-27e6-4b6d-baab-1567317f3374
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b4b605cdf090dea66507696f8ac7e9a00dce11c0
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46049755"
---
# <a name="compiler-error-c3013"></a>Erro do compilador C3013

'cláusula': cláusula deve aparecer apenas uma vez na diretiva de 'diretiva' OpenMP

Uma cláusula apareceu duas vezes na mesma diretiva. Exclua uma ocorrência da cláusula.

O exemplo a seguir gera C3013:

```
// C3013.cpp
// compile with: /openmp
int main() {
   int a, b, c, x, y, z;

   #pragma omp parallel shared(a,b,c) private(x)

   #pragma omp for nowait private(x) nowait   // C3013
   // The previous line generates C3013, with two nowait clauses
   // try the following line instead:
   // #pragma omp for nowait private(x)
   for (a = 0 ; a < 10 ; ++a) {
   }
}
```