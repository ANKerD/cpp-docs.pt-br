---
title: Erro do compilador C3498 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3498
dev_langs:
- C++
helpviewer_keywords:
- C3498
ms.assetid: 0a5a7817-0872-4119-83bf-980a19113374
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5bb87abc113e586aa4f3097444df4c5a46a6a92c
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46106761"
---
# <a name="compiler-error-c3498"></a>Erro do compilador C3498

'var': não é possível capturar uma variável que tem um gerenciado ou WinRTtype

Não é possível capturar uma variável que tem um tipo gerenciado ou um tipo de tempo de execução do Windows em um lambda.

### <a name="to-correct-this-error"></a>Para corrigir este erro

- Passe o gerenciado ou variável de tempo de execução do Windows para a lista de parâmetros da expressão lambda.

## <a name="example"></a>Exemplo

O exemplo a seguir gera C3498 como uma variável que tem um tipo gerenciado aparece na lista de captura de uma expressão lambda:

```
// C3498a.cpp
// compile with: /clr
using namespace System;

int main()
{
   String ^ s = "Hello";
   [&s](String ^ r)
      { return String::Concat(s, r); } (", World!"); // C3498
}
```

## <a name="example"></a>Exemplo

O exemplo a seguir resolve C3498, passando a variável gerenciada `s` à lista de parâmetros da expressão lambda:

```
// C3498b.cpp
// compile with: /clr
using namespace System;

int main()
{
   String ^ s = "Hello";
   [](String ^ s, String ^ r)
      { return String::Concat(s, r); } (s, ", World!");
}
```

## <a name="see-also"></a>Consulte também

[Expressões Lambda](../../cpp/lambda-expressions-in-cpp.md)