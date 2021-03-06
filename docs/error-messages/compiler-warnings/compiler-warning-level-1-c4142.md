---
title: Compilador aviso (nível 1) C4142 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4142
dev_langs:
- C++
helpviewer_keywords:
- C4142
ms.assetid: 1fdfc3dc-60a2-4f00-b133-20e400f9b7a6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 011f71c1d57f03c2be9bac3df67cd0ed90aa8017
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46117381"
---
# <a name="compiler-warning-level-1-c4142"></a>Compilador aviso (nível 1) C4142

redefinição benigna de tipo

Um tipo é redefinido de forma que não tem efeito sobre o código gerado.

Para corrigir verificando as possíveis causas:

- Uma função de membro de uma classe derivada tem um tipo de retorno diferente da função de membro correspondente da classe base.

- Um tipo definido com o `typedef` comando é redefinido com o uso de uma sintaxe diferente.

O exemplo a seguir gera C4142:

```
// C4142.c
// compile with: /W1
float X2;
X2 = 2.0 + 1.0;   // C4142

int main() {
   float X2;
   X2 = 2.0 + 1.0;   // OK
}
```