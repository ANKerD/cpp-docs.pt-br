---
title: Erro do compilador C2008 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2008
dev_langs:
- C++
helpviewer_keywords:
- C2008
ms.assetid: e748ccbe-ffd4-4008-aca7-e53c25225209
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a00c2a55d7176beae88f7e5db3045722568bd293
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46051237"
---
# <a name="compiler-error-c2008"></a>Erro do compilador C2008

'character': inesperado na definição de macro

O caractere é exibido imediatamente após o nome da macro. Para resolver o erro, deve haver um espaço após o nome da macro.

O exemplo a seguir gera C2008:

```
// C2008.cpp
#define TEST1"mytest1"    // C2008
```

Solução possível:

```
// C2008b.cpp
// compile with: /c
#define TEST2 "mytest2"
```