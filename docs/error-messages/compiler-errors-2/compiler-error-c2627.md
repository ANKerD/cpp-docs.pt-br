---
title: Erro do compilador C2627 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2627
dev_langs:
- C++
helpviewer_keywords:
- C2627
ms.assetid: 7fc6c5ac-c7c9-4f0b-ad52-f52252526458
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a7548e2154144ca502ab581bf804018b80cc0d8d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46072661"
---
# <a name="compiler-error-c2627"></a>Erro do compilador C2627

'function': função membro não permitida em union anônima

Uma [união anônima](../../cpp/unions.md#anonymous_unions) não pode ter funções de membro.

O exemplo a seguir gera C2627:

```
// C2627.cpp
int main() {
   union { void f(){} };   // C2627
   union X { void f(){} };
}
```