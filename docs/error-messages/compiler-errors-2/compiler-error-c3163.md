---
title: Erro do compilador C3163 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3163
dev_langs:
- C++
helpviewer_keywords:
- C3163
ms.assetid: 17dcafa3-f416-4e04-a232-f9569218ba75
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0e712a70bdd443d9a6c640853b958f29dac78dbd
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46061962"
---
# <a name="compiler-error-c3163"></a>Erro do compilador C3163

'Criar': atributos inconsistentes com declaração anterior

Os atributos que são aplicados a uma definição em conflito com os atributos que são aplicados a uma declaração.

Uma maneira de resolver C3163 é eliminar atributos na declaração de encaminhamento. Todos os atributos em uma declaração de encaminhamento devem ser menor do que os atributos na definição ou, no máximo, igual a eles.

Uma possível causa do erro C3163 envolve a linguagem de anotação de código do código-fonte Microsoft (SAL). As macros SAL não expanda, a menos que você compila seu projeto usando o **/ANALYZE** sinalizador. Um programa que é compilado corretamente sem /ANALYZE pode lançar C3163 se você tentar recompilá-lo com a opção /Analyze. Para obter mais informações sobre o SAL, consulte [anotações de SAL](../../c-runtime-library/sal-annotations.md).

## <a name="example"></a>Exemplo

O exemplo a seguir gera C3163.

```
// C3163.cpp
// compile with: /clr /c
using namespace System;

[CLSCompliant(true)] void f();
[CLSCompliant(false)] void f() {}   // C3163
// try the following line instead
// [CLSCompliant(true)] void f() {}
```

## <a name="see-also"></a>Consulte também

[Anotações de SAL](../../c-runtime-library/sal-annotations.md)