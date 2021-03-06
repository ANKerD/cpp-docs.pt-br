---
title: 3.2.3 funções omp_set_lock e omp_set_nest_lock funções | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: b5323879-f72e-418e-953f-3979fdda17a2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 792b95baef2821bb693d9a90fc228d2b0c508e1f
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46420355"
---
# <a name="323-ompsetlock-and-ompsetnestlock-functions"></a>3.2.3 funções omp_set_lock e omp_set_nest_lock

Cada uma dessas funções bloqueia o thread de execução da função até o bloqueio especificado está disponível e, em seguida, define o bloqueio. Um bloqueio simples estará disponível se ele for desbloqueado. Um bloqueio empilhável está disponível, se ele estiver desbloqueado ou se ele já pertence ao thread executando a função. O formato é o seguinte:

```
#include <omp.h>
void omp_set_lock(omp_lock_t *lock);
void omp_set_nest_lock(omp_nest_lock_t *lock);
```

Para um bloqueio simple, o argumento para o `omp_set_lock` função deve apontar para uma variável inicializada de bloqueio. Propriedade do bloqueio é concedida para o thread de execução da função.

Para um bloqueio empilhável, o argumento para o `omp_set_nest_lock` função deve apontar para uma variável inicializada de bloqueio. A contagem de aninhamento é incrementada e o thread é concedido ou reterá, a propriedade do bloqueio.