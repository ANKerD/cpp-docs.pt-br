---
title: Erro do compilador C3874 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3874
dev_langs:
- C++
helpviewer_keywords:
- C3874
ms.assetid: fd55fc05-69a7-4237-b3b7-dca1d5400b4f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 70f6773e65c167b980a4fd9967b910a3f760d58f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46059258"
---
# <a name="compiler-error-c3874"></a>Erro do compilador C3874

tipo de retorno de 'function' deve ser 'int', em vez de 'type'

Uma função não tem o tipo de retorno que era esperado pelo compilador.

O exemplo a seguir gera C3874:

```
// C3874b.cpp
double main()
{   // C3874
}
```