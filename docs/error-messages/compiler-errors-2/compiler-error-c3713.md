---
title: Erro do compilador C3713 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3713
dev_langs:
- C++
helpviewer_keywords:
- C3713
ms.assetid: 75c6b9b6-955b-49bd-9bc8-ced88b496a1f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8028a82895d9194a44ca844b628e6a0d96ef4811
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46042618"
---
# <a name="compiler-error-c3713"></a>Erro do compilador C3713

'method': um método de manipulador de eventos deve ter os mesmos parâmetros de função como a origem 'method'

Você definiu um método de manipulador de eventos que não usa os mesmos parâmetros como o método de evento de origem. Para corrigir esse erro, dê o método de manipulador de eventos os mesmos parâmetros de método de evento de origem.

O exemplo a seguir gera C3713:

```
// C3713.cpp
// compile with: /c
[event_source(native)]
class CEventSrc {
public:
   __event void event1(int nValue);
   // try the following line instead
   // __event void event1();
};

[event_receiver(native)]
class CEventRec {
public:
   void handler1() {}

   void HookEvents(CEventSrc* pSrc) {
      __hook(&CEventSrc::event1, pSrc, &CEventRec::handler1);   // C3713
   }

   void UnhookEvents(CEventSrc* pSrc) {
      __unhook(&CEventSrc::event1, pSrc, &CEventRec::handler1); // C3713
   }
};
```