---
title: Compilador aviso (nível 2) C4146 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4146
dev_langs:
- C++
helpviewer_keywords:
- C4146
ms.assetid: d6c31ab1-3120-40d5-8d80-32b5f7046e32
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 41d21f2be76e67c58599e214df764316dc845e59
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46044620"
---
# <a name="compiler-warning-level-2-c4146"></a>Compilador aviso (nível 2) C4146

operador menos unário aplicado a tipo unsigned, resultado permanece unsigned

Tipos sem sinal podem conter apenas valores não negativos, portanto, a subtração (negação) unária geralmente não faz sentido quando aplicado a um tipo sem sinal. O operando e o resultado são não negativo.

Na prática, isso ocorre quando o programador está tentando expressar o valor mínimo inteiro, que é de -2147483648. Esse valor não pode ser escrito como -2147483648 porque a expressão é processada em dois estágios:

1. O número 2147483648 é avaliado. Como ele é maior que o valor de inteiro máximo de 2147483647, o tipo de 2147483648 não é [int](../../c-language/integer-types.md), mas `unsigned int`.

1. Menos unário é aplicado ao valor, com um resultado sem sinal, que também vem a ser 2147483648.

O tipo sem sinal do resultado pode causar um comportamento inesperado. Se o resultado é usado em uma comparação, uma comparação sem sinal pode ser usada, por exemplo, quando o outro operando for um `int`. Isso explica por que o programa de exemplo a seguir imprime apenas uma linha.

A segunda linha esperada, `1 is greater than the most negative int`, não será impresso porque `((unsigned int)1) > 2147483648` é false.

Você pode evitar C4146 usando INT_MIN de Limits. h, que tem o tipo **assinado int**.

## <a name="example"></a>Exemplo

O exemplo a seguir gera C4146:

```
// C4146.cpp
// compile with: /W2
#include <stdio.h>

void check(int i)
{
    if (i > -2147483648)   // C4146
        printf_s("%d is greater than the most negative int\n", i);
}

int main()
{
    check(-100);
    check(1);
}
```