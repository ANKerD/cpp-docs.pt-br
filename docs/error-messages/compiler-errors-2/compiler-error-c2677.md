---
title: Erro do compilador C2677 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2677
dev_langs:
- C++
helpviewer_keywords:
- C2677
ms.assetid: 76bc0b65-f52a-45a6-b6d6-0555f89da9a8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1cd7e4b3b454d8611c52bbe88041677434492c0f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46030775"
---
# <a name="compiler-error-c2677"></a>Erro do compilador C2677

binário 'operator': Nenhum operador global encontrado que receba o tipo 'type' (ou não há nenhuma conversão aceitável)

Para usar o operador, você deve sobrecarregá-lo para o tipo especificado ou definir uma conversão para um tipo para o qual o operador está definido.

O exemplo a seguir gera C2677:

```
// C2677.cpp
class C {
public:
   C(){}
} c;

class D {
public:
   D(){}
   operator int(){return 0;}
} d;

int main() {
   int i = 1 >> c;   // C2677
   int j = 1 >> d;   // OK operator int() defined
}
```