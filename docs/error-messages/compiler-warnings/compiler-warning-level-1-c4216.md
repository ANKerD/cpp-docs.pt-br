---
title: Compilador aviso (nível 1) C4216 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4216
dev_langs:
- C++
helpviewer_keywords:
- C4216
ms.assetid: 211079dc-59d0-42a7-801c-2ddab21d7232
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d6f9e53115b7b162fa4c36ad9a3fa227de777bf8
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46042982"
---
# <a name="compiler-warning-level-1-c4216"></a>Compilador aviso (nível 1) C4216

extensão não padrão usada: longo flutuante

As extensões padrão da Microsoft (/Ze) tratam **longo flutuante** como **duplo**. Compatibilidade com ANSI ([/Za](../../build/reference/za-ze-disable-language-extensions.md)) não faz isso. Use **duplas** para manter a compatibilidade. O exemplo a seguir gera C4216:

```
// C4216.cpp
// compile with: /W1
float long a;   // C4216

// use the line below to resolve the warning
// double a;

int main() {
}
```