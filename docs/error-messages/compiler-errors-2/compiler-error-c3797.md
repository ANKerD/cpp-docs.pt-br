---
title: Erro do compilador C3797 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3797
dev_langs:
- C++
helpviewer_keywords:
- C3797
ms.assetid: ab27ff34-8c1d-4297-b004-9e39bd3a4f25
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3ac1ded1c95f7e8bea9598e468010c75d8bd917a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46033414"
---
# <a name="compiler-error-c3797"></a>Erro do compilador C3797

'override': declaração de evento não pode possuir especificador de substituição (deve ser colocado nos métodos de adicionar/remover/raise do evento em vez disso)

Você não pode substituir um evento trivial (um evento sem métodos de acessador definido explicitamente) com outro evento trivial. O evento de substituição deve definir seu comportamento com funções do acessador.

Para obter mais informações, consulte [evento](../../windows/event-cpp-component-extensions.md).

## <a name="example"></a>Exemplo

O exemplo a seguir gera C3797.

```
// C3797.cpp
// compile with: /clr /c
delegate void MyDel();

ref class Class1 {
public:
   virtual event MyDel ^ E;
};

ref class Class2 : public Class1 {
public:
   virtual event MyDel ^ E override;   // C3797
};

// OK
ref class Class3 : public Class1 {
public:
   virtual event MyDel ^ E {
      void add(MyDel ^ d) override {}
      void remove(MyDel ^ d) override {}
   }
};
```