---
title: 'Método srwlockexclusivetraits:: Unlock | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::SRWLockExclusiveTraits::Unlock
dev_langs:
- C++
helpviewer_keywords:
- Unlock method
ms.assetid: 7fd6b0fb-8b88-4a43-aa74-0d7fe47a0da6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 84f1ef800154f4acf410d45528c50d86180bad39
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42607882"
---
# <a name="srwlockexclusivetraitsunlock-method"></a>Método SRWLockExclusiveTraits::Unlock

Libera o controle exclusivo do especificado `SRWLock` objeto.

## <a name="syntax"></a>Sintaxe

```cpp
inline static void Unlock(
   _In_ Type srwlock
);
```

### <a name="parameters"></a>Parâmetros

*SRWLOCK*  
Identificador para um `SRWLock` objeto.

## <a name="requirements"></a>Requisitos

**Cabeçalho:** corewrappers. h

**Namespace:** Microsoft::WRL::Wrappers::HandleTraits

## <a name="see-also"></a>Consulte também

[Estrutura SRWLockExclusiveTraits](../windows/srwlockexclusivetraits-structure.md)