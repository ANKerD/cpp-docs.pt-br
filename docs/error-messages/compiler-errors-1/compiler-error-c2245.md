---
title: Erro do compilador C2245 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2245
dev_langs:
- C++
helpviewer_keywords:
- C2245
ms.assetid: 08aaeadf-10ec-485a-b2a6-6e775289082b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2df4d79afc9c934abb9296a78c6cb5f0dd4ffde5
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46080019"
---
# <a name="compiler-error-c2245"></a>Erro do compilador C2245

a função de membro inexistente 'function' especificada como friend (assinatura de função de membro não corresponde a nenhuma sobrecarga)

Uma função especificada como amiga não foi encontrada pelo compilador.

O exemplo a seguir gera C2245:

```
// C2245.cpp
// compile with: /c
class B {
   void f(int i);
};

class A {
   int m_i;
   friend void B::f(char);   // C2245
   // try the following line instead
   // friend void B::f(int);
};

void B::f(int i) {
   A a;
   a.m_i = 0;
}
```