---
title: Erro do compilador C2374 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2374
dev_langs:
- C++
helpviewer_keywords:
- C2374
ms.assetid: 73b51965-e91c-4e21-9732-f71c1449d22e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ad2b56ed0450e7eb734f5ed13b4cffcc9687c572
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46095125"
---
# <a name="compiler-error-c2374"></a>Erro do compilador C2374

'identifier': redefinição; várias inicializações

O identificador é inicializado mais de uma vez.

O exemplo a seguir gera C2374:

```
// C2374.cpp
// compile with: /c
int i = 0;
int i = 1;   // C2374
int j = 1;   // OK
```