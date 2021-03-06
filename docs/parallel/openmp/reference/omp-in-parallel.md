---
title: omp_in_parallel | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- omp_in_parallel
dev_langs:
- C++
helpviewer_keywords:
- omp_in_parallel OpenMP function
ms.assetid: 1f01a1b4-78c5-496a-afb7-a43ecdad83d6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7ade0b6199d0b56fc124033aeb595fe3de40ba9f
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46426842"
---
# <a name="ompinparallel"></a>omp_in_parallel

Retorna diferente de zero se for chamado de dentro de uma região paralela.

## <a name="syntax"></a>Sintaxe

```
int omp_in_parallel( );
```

## <a name="remarks"></a>Comentários

Para obter mais informações, consulte [3.1.6 função omp_in_parallel](../../../parallel/openmp/3-1-6-omp-in-parallel-function.md).

## <a name="example"></a>Exemplo

```
// omp_in_parallel.cpp
// compile with: /openmp
#include <stdio.h>
#include <omp.h>

int main( )
{
    omp_set_num_threads(4);
    printf_s("%d\n", omp_in_parallel( ));

    #pragma omp parallel
        #pragma omp master
        {
            printf_s("%d\n", omp_in_parallel( ));
        }
}
```

```Output
0
1
```

## <a name="see-also"></a>Consulte também

[Funções](../../../parallel/openmp/reference/openmp-functions.md)