---
title: Erro do compilador C3507 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3507
dev_langs:
- C++
helpviewer_keywords:
- C3507
ms.assetid: 75f89767-f6f9-40f6-9820-81a49e09abdf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8375f96c0a35e01a2a93866157c0156cf22a4993
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46105098"
---
# <a name="compiler-error-c3507"></a>Erro do compilador C3507

um ProgID pode ter não mais de 39 caracteres 'id'; nem conter pontuações além de '.'; nem começar com um dígito

O [progid](../../windows/progid.md) atributo tem restrições nos valores que pode levar.

O exemplo a seguir gera C3507:

```
// C3507.cpp
[module(name="x")];
[
coclass,
progid("0123456789012345678901234567890123456789"),
uuid("00000000-0000-0000-0000-000000000001") // C3507 expected
]
struct CMyStruct {
};
int main() {
}
```