---
title: Erro do compilador C3485 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3485
dev_langs:
- C++
helpviewer_keywords:
- C3485
ms.assetid: d67536f9-67a1-4ad9-9a94-d8bbbca3d0dc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: db3eee53f23aa2cdc958b63faed11ead302f4b1e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46060740"
---
# <a name="compiler-error-c3485"></a>Erro do compilador C3485

uma definição de lambda não pode ter cv-qualifiers

Não é possível usar um `const` ou `volatile` qualificador como parte da definição de uma expressão lambda.

### <a name="to-correct-this-error"></a>Para corrigir este erro

- Remover o `const` ou `volatile` qualificador da definição da expressão lambda.

## <a name="example"></a>Exemplo

O exemplo a seguir gera C3485 porque ele usa o `const` qualificador como parte da definição de uma expressão lambda:

```
// C3485.cpp

int main()
{
   auto x = []() const mutable {}; // C3485
}
```

## <a name="see-also"></a>Consulte também

[Expressões Lambda](../../cpp/lambda-expressions-in-cpp.md)