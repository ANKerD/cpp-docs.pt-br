---
title: A.30 uso de Reprivatização | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 26529090-6c39-40f2-b806-e12374d6b5f8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 27f9ee3f7605231323c5a176eebf1b07c0a05507
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46378027"
---
# <a name="a30---use-of-reprivatization"></a>A.30   Uso de reprivatização

O exemplo a seguir demonstra a reprivatização de variáveis. Variáveis privadas podem ser marcadas `private` novamente em uma diretiva aninhada. Eles não precisam ser compartilhados na região paralela delimitador.

```
int i, a;
...
#pragma omp parallel private(a)
{
  ...
  #pragma omp parallel for private(a)
  for (i=0; i<10; i++)
     {
       ...
     }
}
```