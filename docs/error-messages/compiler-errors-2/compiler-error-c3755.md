---
title: Erro do compilador C3755 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3755
dev_langs:
- C++
helpviewer_keywords:
- C3755
ms.assetid: 9317b55e-a52e-4b87-b915-5a208d6eda38
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 647f62fa75226fd2c80d1bf6285d76e1c2f8c4be
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46026720"
---
# <a name="compiler-error-c3755"></a>Erro do compilador C3755

'delegate': não é possível definir um delegado

Um [delegado (extensões de componentes C++)](../../windows/delegate-cpp-component-extensions.md) pode ser declarada mas não definida.

## <a name="example"></a>Exemplo

O exemplo a seguir gera C3755.

```
// C3755.cpp
// compile with: /clr /c
delegate void MyDel() {};   // C3755
```

## <a name="example"></a>Exemplo

C3755 também pode ocorrer se você tentar criar um modelo de delegado. O exemplo a seguir gera C3755.

```
// C3755_b.cpp
// compile with: /clr /c
ref struct R {
   template<class T>
   delegate void D(int) {}   // C3755
};
```