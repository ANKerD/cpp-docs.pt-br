---
title: Erro do compilador C3369 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3369
dev_langs:
- C++
helpviewer_keywords:
- C3369
ms.assetid: c6ceb9cb-3df9-4334-9a5c-d16db351d476
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b111889c6a4203f5b63a7a644adbc7a51d8a810a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46017997"
---
# <a name="compiler-error-c3369"></a>Erro do compilador C3369

'module name': idl_module já definido

O [idl_module](../../windows/idl-module.md) uso onde você define a DLL pode ocorrer apenas uma vez em um programa.

O exemplo a seguir gera C3369:

```
// C3369.cpp
// compile with: /c
[idl_module(name="name1", dllname="x.dll")]; // C3369
[idl_module(name="name1", dllname="x.dll")];
```