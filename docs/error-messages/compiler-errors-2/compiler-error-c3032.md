---
title: Erro do compilador C3032 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3032
dev_langs:
- C++
helpviewer_keywords:
- C3032
ms.assetid: 6a92bd8e-319f-4a99-aef4-a9021f6f9928
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 611867002157928f4bc0ec67f77cc8c49af87e15
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46037886"
---
# <a name="compiler-error-c3032"></a>Erro do compilador C3032

'var': variável em cláusula 'cláusula' não pode possuir tipo incompleto 'type'

Tipos passados para determinados cláusulas devem ser totalmente visíveis para o compilador.

O exemplo a seguir gera C3032:

```
// C3032.cpp
// compile with: /openmp /link vcomps.lib
#include "omp.h"

struct Incomplete;
extern struct Incomplete inc;

int main() {
   int i = 9;
   #pragma omp parallel private(inc)   // C3032
      ;

   #pragma omp parallel private(i)     // OK
      ;

}
```