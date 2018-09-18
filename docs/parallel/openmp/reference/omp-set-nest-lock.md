---
title: omp_set_nest_lock | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- omp_set_nest_lock
dev_langs:
- C++
helpviewer_keywords:
- omp_set_nest_lock OpenMP function
ms.assetid: b98ed889-ff8e-4217-a3e9-3993ed8699af
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5af33e7223f245325d3b4835a1599034778cd04f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46027694"
---
# <a name="ompsetnestlock"></a>omp_set_nest_lock
Blocos de execução de thread até que um bloqueio esteja disponível.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
void omp_set_nest_lock(  
   omp_nest_lock_t *lock  
);  
```  
  
### <a name="parameters"></a>Parâmetros
  
*lock*<br/>
Uma variável do tipo [omp_nest_lock_t](../../../parallel/openmp/reference/omp-nest-lock-t.md) que foi inicializado com [omp_init_nest_lock](../../../parallel/openmp/reference/omp-init-nest-lock.md).  
  
## <a name="remarks"></a>Comentários  
 Para obter mais informações, consulte [3.2.3 funções omp_set_lock e omp_set_nest_lock](../../../parallel/openmp/3-2-3-omp-set-lock-and-omp-set-nest-lock-functions.md).  
  
## <a name="examples"></a>Exemplos  
 Ver [omp_init_nest_lock](../../../parallel/openmp/reference/omp-init-nest-lock.md) para obter um exemplo de como usar `omp_set_nest_lock`.  
  
## <a name="see-also"></a>Consulte também  
 [Funções](../../../parallel/openmp/reference/openmp-functions.md)