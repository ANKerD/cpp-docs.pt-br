---
title: Erro do compilador C2311 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2311
dev_langs:
- C++
helpviewer_keywords:
- C2311
ms.assetid: 1aff9bd5-ed0b-4db6-bbc0-01ac89850cf2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f19e2a1b41c499605f22575f934b3d4872457011
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46065095"
---
# <a name="compiler-error-c2311"></a>Erro do compilador C2311

'exceções': é capturado por '...' no número de linha

O manipulador catch para o botão de reticências (...) deve ser o último manipulador para um throw.

O exemplo a seguir gera C2311:

```
// C2311.cpp
// compile with: /EHsc
#include <eh.h>
int main() {
   try {
      throw "ooops!";
   }
   catch( ... ) {}
   catch( int ) {}   // C2311  ellipsis handler not last catch
}
```