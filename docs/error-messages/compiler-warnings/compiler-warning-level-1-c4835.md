---
title: Compilador aviso (nível 1) C4835 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4835
dev_langs:
- C++
helpviewer_keywords:
- C4835
ms.assetid: d2e44c62-7b0e-4a45-943d-97903e27ed9d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 70492be13d312c5d167990cfa0b6c0d741e1055f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46080097"
---
# <a name="compiler-warning-level-1-c4835"></a>Compilador aviso (nível 1) C4835

'variable': o inicializador para dados exportados não será executado até que o código gerenciado é executado pela primeira vez no host assembly

Ao acessar dados entre os componentes gerenciados, é recomendável que você não usa a importação de C++ nativa e mecanismos de exportação. Em vez disso, declare seus membros de dados dentro de um tipo gerenciado e fazer referência a metadados com `#using` no cliente. Para obter mais informações, confira [Diretiva #using](../../preprocessor/hash-using-directive-cpp.md).

## <a name="example"></a>Exemplo

O exemplo a seguir gera C4835.

```
// C4835.cpp
// compile with: /W1 /clr /LD
int f() { return 1; }
int n = 9;

__declspec(dllexport) int m = f();   // C4835
__declspec(dllexport) int *p = &n;   // C4835
```

## <a name="example"></a>Exemplo

O exemplo a seguir consome o componente criado no exemplo anterior, mostrando que o valor das variáveis não é conforme o esperado.

```
// C4835_b.cpp
// compile with: /clr C4835.lib
#include <stdio.h>
__declspec(dllimport) int m;
__declspec(dllimport) int *p;

int main() {
   printf("%d\n", m);
   printf("%d\n", p);
}
```

```Output
0
268456008
```