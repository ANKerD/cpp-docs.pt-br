---
title: Erro do compilador C2930 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2930
dev_langs:
- C++
helpviewer_keywords:
- C2930
ms.assetid: f07eecd1-e5d1-4518-bd89-b1fd2a003a17
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3ca348a1ccf6703152088b3da7b0f858e8bab3c5
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46035286"
---
# <a name="compiler-error-c2930"></a>Erro do compilador C2930

'class': id de classe de tipo é redefinido como um enumerador de 'Identificador de enumeração'

Você não pode usar uma classe genérica ou o modelo como um membro de uma enumeração.

Esse erro pode ser causado se as chaves são correspondidas incorretamente.

O exemplo a seguir gera C2930:

```
// C2930.cpp
// compile with: /c
template<class T>
class x{};
enum SomeEnum { x };   // C2930

class y{};
enum SomeEnum { y };
```

C2930 também podem ocorrer ao usar genéricos:

```
// C2930c.cpp
// compile with: /clr /c
generic<class T>
ref struct GC {};
enum SomeEnum { GC };   // C2930

ref struct GC2 {};
enum SomeEnum2 { GC2 };
```