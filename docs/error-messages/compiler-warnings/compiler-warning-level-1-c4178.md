---
title: Compilador aviso (nível 1) C4178 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4178
dev_langs:
- C++
helpviewer_keywords:
- C4178
ms.assetid: 2c2c8f97-a5c4-47cd-8dd2-beea172613f3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 806be9713bff649dde4031c3d14363b76aa4f563
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46073727"
---
# <a name="compiler-warning-level-1-c4178"></a>Compilador aviso (nível 1) C4178

constante de Case 'constante' muito grande para o tipo da expressão switch

Uma constante de case em uma `switch` expressão, não existe no tipo ao qual ele está atribuído.

## <a name="example"></a>Exemplo

```
// C4178.cpp
// compile with: /W1
int main()
{
    int i;  // maximum size of unsigned long int is 4294967295
    switch( i )
    {
        case 4294967295:   // OK
            break;
        case 4294967296:   // C4178
            break;
    }
}
```