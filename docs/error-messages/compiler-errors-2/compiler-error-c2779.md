---
title: Erro do compilador C2779 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2779
dev_langs:
- C++
helpviewer_keywords:
- C2779
ms.assetid: 4a00e492-855a-41f3-8a18-5f60ee20c2f2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 43067c780accfea1d55f9fd9c9dbce69fe41a43a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46046778"
---
# <a name="compiler-error-c2779"></a>Erro do compilador C2779

'declaração de ': métodos de propriedade só podem ser associados a membros de dados não estáticos

O `property` atributo estendido incorretamente é aplicado a um membro de dados estáticos.

O exemplo a seguir gera C2779:

```
// C2779.cpp
struct A {
   static __declspec(property(put=PutProp))
   // try the following line instead
   __declspec(property(put=PutProp))
      int prop;   // C2779
   int PutProp(void);
};
```