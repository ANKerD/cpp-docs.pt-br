---
title: A.12 usando a diretiva atomic | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: d3ba3c87-413d-4efa-8a45-8a7f28ab0164
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 04daed582cfe87f6e4803b30919af3e07037de7f
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46378742"
---
# <a name="a12---using-the-atomic-directive"></a>A.12   Usando a diretiva atomic

O exemplo a seguir evita as condições de corrida (atualizações simultâneas de um elemento de *x* por vários threads) usando o `atomic` diretiva ([seção 2.6.4](../../parallel/openmp/2-6-4-atomic-construct.md) na página 19):

```
#pragma omp parallel for shared(x, y, index, n)
    for (i=0; i<n; i++)
    {
        #pragma omp atomic
            x[index[i]] += work1(i);
        y[i] += work2(i);
    }
```

A vantagem de usar o `atomic` diretiva neste exemplo é que ele permite que as atualizações de dois elementos diferentes de x ocorram em paralelo. Se um `critical` diretiva ([seção 2.6.2](../../parallel/openmp/2-6-2-critical-construct.md) na página 18) foram usadas em vez disso, em seguida, todas as atualizações aos elementos de *x* seria executado em série (embora não em qualquer garantia de ordem).

Observe que o `atomic` diretiva se aplica somente à instrução C ou C++ imediatamente após ele.  Como resultado, os elementos de *y* não são atualizadas automaticamente neste exemplo.