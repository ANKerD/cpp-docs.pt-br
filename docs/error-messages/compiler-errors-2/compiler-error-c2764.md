---
title: Erro do compilador C2764 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2764
dev_langs:
- C++
helpviewer_keywords:
- C2764
ms.assetid: 3754f5af-e094-4425-be20-d0c9a9b5baec
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3456a9bcca6df1a658600ecf6085bb060f988b3f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46043788"
---
# <a name="compiler-error-c2764"></a>Erro do compilador C2764

'param': parâmetro de modelo não usado ou dedutível em especialização parcial 'especialização'

Um parâmetro de modelo não é usado em uma especialização parcial. Isso torna a especialização parcial inutilizável pois o parâmetro de modelo não pode ser deduzido.

## <a name="example"></a>Exemplo

O exemplo a seguir gera C2764:

```
// C2764.cpp
#include <stdio.h>
template <class T1, class T2>
struct S  {
   int m_i;
};

template <class T1, class T2>
struct S<int, T2*> {   // C2764
// try the following line instead
// struct S<T1(*)(T2), T2*> {
   char m_c;
};

int main() {
   S<int, char> s1;
   S<void (*)(short), short *> s2;
   s2.m_c = 10;
   s1.m_i = s2.m_c;
   printf_s("%d\n", s1.m_i);
}
```