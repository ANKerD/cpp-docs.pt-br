---
title: Compilador aviso (nível 1) C4186 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4186
dev_langs:
- C++
helpviewer_keywords:
- C4186
ms.assetid: caf3f7d8-f305-426b-8d4e-2b96f5c269ea
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0bfc722a07d2ddb10e5be8c6d8fde60956b297c8
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46079772"
---
# <a name="compiler-warning-level-1-c4186"></a>Compilador aviso (nível 1) C4186

\#atributo de importação 'attribute' exige argumentos de contagem; ignorado

Um `#import` atributo tem um número incorreto de argumentos.

## <a name="example"></a>Exemplo

```
// C4186.cpp
// compile with: /W1 /c
#import "stdole2.tlb" no_namespace("abc") rename("a","b","c")  // C4186
```

O `no_namespace` atributo não utiliza argumentos. O **Renomear** atributo usa apenas dois argumentos.