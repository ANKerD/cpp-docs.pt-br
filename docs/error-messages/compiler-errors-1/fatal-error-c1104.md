---
title: Erro fatal C1104 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1104
dev_langs:
- C++
helpviewer_keywords:
- C1104
ms.assetid: 45bd85c4-77d3-4d3c-b167-49c563aefb4d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e624238a1b7616ab84a655839a05cfd6899d38ea
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46048104"
---
# <a name="fatal-error-c1104"></a>Erro fatal C1104

Erro fatal ao importar libid: 'message'

O compilador detectou um problema ao importar uma biblioteca de tipos.  Por exemplo, você não pode especificar uma biblioteca de tipos com libid e também especificar `no_registry`.

Para obter mais informações, consulte [#import diretiva](../../preprocessor/hash-import-directive-cpp.md).

O exemplo a seguir gerará C1104:

```
// C1104.cpp
#import "libid:11111111.1111.1111.1111.111111111111" version("4.0") lcid("9") no_registry auto_search   // C1104
```