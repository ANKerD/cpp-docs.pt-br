---
title: Compilador aviso (nível 1) C4141 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4141
dev_langs:
- C++
helpviewer_keywords:
- C4141
ms.assetid: 6ce8c058-7f4c-41cf-93e7-90a466744656
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e7155aeeb352f626d56f1c04cf05b03584fdc639
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46075837"
---
# <a name="compiler-warning-level-1-c4141"></a>Compilador aviso (nível 1) C4141

'modificador': usado mais de uma vez

## <a name="example"></a>Exemplo

```
// C4141.cpp
// compile with: /W1 /LD
inline inline void func ();   // C4141
```