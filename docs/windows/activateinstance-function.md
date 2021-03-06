---
title: Função ActivateInstance | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Windows::Foundation::ActivateInstance
- client/ABI::Windows::Foundation::ActivateInstance
dev_langs:
- C++
helpviewer_keywords:
- ActivateInstance function
ms.assetid: 8cfd1dd9-5fda-4cc2-acf8-d40e783b3875
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ebebe0bbceafe82c41ec99b2532c965670776127
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46426387"
---
# <a name="activateinstance-function"></a>Função ActivateInstance

Registra e recupera uma instância de um tipo especificado definido em uma ID de classe especificado.

## <a name="syntax"></a>Sintaxe

```cpp
template<typename T>
inline HRESULT ActivateInstance(
   _In_ HSTRING activatableClassId,
   _Out_ Microsoft::WRL::Details::ComPtrRef<T> instance
);
```

### <a name="parameters"></a>Parâmetros

*T*<br/>
Um tipo para ativar.

*activatableClassId*<br/>
A ID da classe que define o parâmetro *T*.

*instância*<br/>
Quando essa operação for concluída, uma referência a uma instância do *T*.

## <a name="return-value"></a>Valor de retorno

S_OK se bem-sucedido; Caso contrário, um erro HRESULT que indica a causa do erro.

## <a name="requirements"></a>Requisitos

**Cabeçalho:** client.h

**Namespace:** Windows:: Foundation

## <a name="see-also"></a>Consulte também

[Namespace Windows::Foundation](../windows/windows-foundation-namespace.md)